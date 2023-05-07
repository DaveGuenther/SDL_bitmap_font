# SDL_bitmap_font
This is a header only library for SDL build on other header only libraries that allow you to create and use bitmap fonts.  I put it together because I was looking for a way to use bitmap fonts using SDL2 but without relying on the SDL2_Image dependency in my own projects.  After getting it substantially working, I've made the source public in case others may want to use it.

A small header only library that uses allows you to load long bitmap fonts (PNG file with companion CSV file that 
details font information).  This library depends on several other header only libraries so that SDL2_image binaries are
not required to run.  At this time all fonts created must be <i>mono-spaced</i>.

## Dependencies:
- libSDL2         http://www.libsdl.org
- stb_image.h     https://github.com/nothings/stb  (Author: Sean Barrett)
- SDL_stbimage.h  https://github.com/DanielGibson/Snippets/  (Author: Daniel Gibson)

I've included the header only libraries from the two authors above in this repo just so that the example code I've written can compile and run.  Visit their github repositories for updated code.

## Installation and Configuration:
In my own projects I store stb_image.h, SDL_image.h and SDL_bitmap_font.h in a 3rd_party subdirectory of my src/ directory:

src/<br>
&nbsp;&nbsp;&nbsp;&nbsp;main.cpp<br>
&nbsp;&nbsp;&nbsp;&nbsp;3rd_party/<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;stb_image.h<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SDL_stbimage.h<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SDL_bitmap_font.h<br>

Requirements of stb_image and SDL_stbimage pass through to this library as well, namely you must include the following line once (and only once) in your source code, ideally in your root source file (like main.cpp):

<code>#define SDL_STBIMAGE_IMPLEMENTATION</code><br>

Then you can include SDL_bitmap_font.h where you plan to use it
<code>#include "SDL_bitmap_font.h"</code>

## Creating Fonts
In order to provide maximum flexibility to the user, fonts are defined as a PNG file with the height of the maximum typeset glyph height

<p align="center"><img src="https://github.com/DaveGuenther/SDL_bitmap_font/blob/main/doc/Bitmap_Layout.png">
  <br><i>Bitmap Font Image Layout</i>
</p>
<br>




