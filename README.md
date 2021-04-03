# JackBitmapEditor
A convenient program for making it easier to create sprites and animations for the Jack (Hack) platform. 

## Background
Made for use in the course nand2tetris <https://nand2tetris.org>

## Usage
Open JackBitmapEditor.html in a browser and get creative.

## Demo
coming soon...

## Features
Details on specific features of the program.

### Shift Buttons
Moves the enire drawing one pixel in the direction specified. Keeps track of the amount shifted in each direction to include a buffer that erases the parts of previous frames
in which the sprite has moved out of. To remove this buffer effect, use 'Clear Shift.'

### Invert
Switches all white pixels to black and vice-versa.

### Inverted Mode
For drawing with white on a black background. This mode expects the background to be black, erases by making pixels black, and interprets the drawing as the white pixels on the canvas

### Canvas Size
Change the number of pixels in each row (width) and column (height). Pixel size refers to the size of the squares on the canvas, and should be decreased as necessary for very large canvas sizes.

### Margin Type
On 'Fit to Drawing,' code will only be generated for the parts of the canvas that include the drawing. On 'Rectangular,' the code will be generated for the bitmap made by the 
smallest rectangle enclosing the rectangle. On 'Full Canvas,' code is generated for every pixel on the canvas, no matter how much space the drawing takes up.

### Base Address
The Hack screen is made up of 256 rows of 32 words, each of wich is a 16-bit number that corresponds with 16 pixels. Location in the Jack code refers to the word that the drawing should start on in the screen. On 'Top Left' mode, the location (base address) referes to the top left corner of the drawing, and code in this mode matches that of previous versions of the BitmapEditor.html. Use 'Bottom Left' if you find it easier to specify screen coordinate locations in that format. 

## Contributers
Golan Parashi, Ignacio del Valle Alles, and Erik Umble (Shimon Schocken and Noam Nisan developed the Jack programming language).

## License
GNU General Public
Free to share, edit, and redistribute as long as you do so without charge.
