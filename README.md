# Pixelfix

Changes the colors of completely transparent pixels in an image to match the color of the nearest non-transparent pixel.

Designed to be a quick drag-and-drop tool:

1. Make your images
2. Select them all and drag them on to the pixelfix executable. The pixelfix executable will overwrite the original images with fixed copies.
3. Make sure there were no errors and close the console window
4. Use or upload your images. Your images should now look fine when resized.

## More info

When saving an image file, most image editors will save completely transparent pixels as black. On some platforms, the resizing algorithm blends transparent pixels with non-transparent pixels, resulting in black edges on resized images. [Here](http://www.adriancourreges.com/blog/2017/05/09/beware-of-transparent-pixels/) is an article showing the difference and discussing techniques to fix the issue.

This script keeps those pixels transparent, but changes their color to match the nearest non-transparent pixel. This means that when the non-transparent and transparent pixels are blended, there should be no color difference.

This script is made into an executable using [the pkg tool](https://www.npmjs.com/package/pkg).

`pkg -o pixelfix -t node10-win-x64,node10-win-x86,node10-macos-x64,node10-linux-x64 .\index.js`