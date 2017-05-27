# hello-world
Hello there
// Schimba culoare cand se suprapun 2 obiecte

#include "MainWindow.h"
#include "Game.h"

Game::Game( MainWindow& wnd )
	:
	wnd( wnd ),
	gfx( wnd )
{
}

void Game::Go()
{
	gfx.BeginFrame();	
	UpdateModel();
	ComposeFrame();
	gfx.EndFrame();
}

void Game::UpdateModel()
{
	if (wnd.kbd.KeyIsPressed(VK_RIGHT))
	{
		x_mob = x_mob + 1;
	}

	if (wnd.kbd.KeyIsPressed(VK_LEFT))
	{
		x_mob = x_mob - 1;
	}

	if (wnd.kbd.KeyIsPressed(VK_DOWN))
	{
		y_mob = y_mob + 1;
	}


	if (wnd.kbd.KeyIsPressed(VK_UP))
	{
		y_mob = y_mob - 1;
	}

	const int left_mob = x_mob - 5;
	const int right_mob = x_mob + 5;
	const int top_mob = y_mob - 5;
	const int bot_mob = y_mob + 5;

	const int left_fix = x_fix - 5;
	const int right_fix = x_fix + 5;
	const int top_fix = y_fix - 5;
	const int bot_fix = y_fix + 5;

	if (left_mob < right_fix &&
		right_mob > left_fix &&
		top_mob < bot_fix    &&
		bot_mob > top_fix)
	{
		intersectare = true;
	}
	else
	{
		intersectare = false;
	}
}

void Game::ComposeFrame()
{
	const int r_fix = 0;
	const int g_fix = 255;
	const int b_fix = 0;

		gfx.PutPixel(-5 + x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-5 + x_fix, -4 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-5 + x_fix, -3 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-4 + x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-3 + x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-5 + x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-5 + x_fix, 4 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-5 + x_fix, 3 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-4 + x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(-3 + x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, -4 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, -3 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(4 +  x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(3 +  x_fix, -5 + y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, 4 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(5 +  x_fix, 3 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(4 +  x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);
		gfx.PutPixel(3 +  x_fix, 5 +  y_fix, r_fix, g_fix, b_fix);

		int r_mob, g_mob, b_mob;

		if (intersectare)
		{
			r_mob = 255;
			g_mob = 0;
			b_mob = 0;
		}
		else
		{
			r_mob = 255;
			g_mob = 255;
			b_mob = 255;
		}
	
		gfx.PutPixel(-5 + x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-5 + x_mob, -4 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-5 + x_mob, -3 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-4 + x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-3 + x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-5 + x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-5 + x_mob, 4 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-5 + x_mob, 3 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-4 + x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(-3 + x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, -4 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, -3 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(4 +  x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(3 +  x_mob, -5 + y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, 4 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(5 +  x_mob, 3 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(4 +  x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
		gfx.PutPixel(3 +  x_mob, 5 +  y_mob, r_mob, g_mob, b_mob);
}						  				
