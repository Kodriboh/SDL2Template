# SDL2 Mingw64

SDL2 Template for running with Mingw64 bit compiler.

## Build
<pre>mingw32-make -f .\Makefile</pre>

## How To Install SDL

1. Acquire the official SDL2 image from the SDL git repository via their [website](https://www.libsdl.org/).

2. Acquire SDL_image 2.0 from the official SDL_image repository via their [website](https://wiki.libsdl.org/SDL2_image/FrontPage)

Note: The download you are after is the `mingw.tar.gz` this contains both 32 and 64 bit versions.

3. Unzip both folders to a safe location.

4. Move the bin, include, and lib from SDL_image to your unzipped SDL folder of
the same version (if you are using 32 bit move it to the 32 bit folder which contains the same folders for SDL, or if you are using 64 bit do the same for the latter).

5. Create a project folder.

6. Create an `include/sdl` folder.

7. Move all of the header files from your SDL2 folder to the project `include/SDL2` folder.

8. Copy the lib folder to the root of your project.

9. Move your .dll fils from your SDL2 bin folder to the root of your project.

10. Create `src/main.cpp`

11. include `SDL.h`

12. Add SDL to your workspace PATH if using VSCode

13. Write a basic program to check SDL is installed correctly.

Note: SDL does not work correctly without having the CMD arguments
passed into main. I recommend testing with the following program:

```

#include <SDL.h>
#include <iostream>

int main(int argc, char *argv[]) {

	std::cout << "SDL Works" << std::endl;
	std::cin.get();

	return 0;
}

```

If this runs successfully you can also try:

```
#include <SDL.h>
#include <iostream>

int main(int argc, char *argv[]) {

	if (SDL_Init(SDL_INIT_VIDEO) < 0) {
		std::cout << "SDL Init Failed!" << std::endl;
		return 1;
	}

	std::cout << "SDL Init succeeded!" << std::endl;

	SDL_Quit();

	return 0;
}
```

This will ensure SDL is callable and initialising correctly.

14. Build your project and run the `exe`:

```
> mingw32-make -f .\Makefile
```
