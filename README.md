# JackBitmapEditor
A convenient program for making it easier to create sprites and animations for the Jack (Hack) platform. 

## Version
2.6 (added localStorage to save drawing even if tab is closed)

## Background
Made for use in the course nand2tetris <https://nand2tetris.org>

## Usage
Open JackBitmapEditor.html in a browser and get creative.

## Demo
[![Video Demo](https://img.youtube.com/vi/a9NakmoimJI/0.jpg)](https://www.youtube.com/watch?v=a9NakmoimJI)

## Features
Details on specific features of the program.

##### Shift Buttons
Moves the enire drawing one pixel in the direction specified. Keeps track of the amount shifted in each direction to include a buffer that erases the parts of previous frames
in which the sprite has moved out of. To remove this buffer effect, use 'Clear Shift.' The code generated to erase previous frame parts only considered absolute shift (5 shifts up and 2 shifts down is equivalent to 3 shifts up); if this seems counterintuitive or unhelpful, let me know and I will consider changing the behavior. 

##### Invert
Switches all white pixels to black and vice-versa.

##### Inverted Mode
For drawing with white on a black background. This mode expects the background to be black, erases by making pixels black, and interprets the drawing as the white pixels on the canvas

##### Obvious Word Edges
The Hack screen is implemented as a chunk of RAM, where each address stores a 16 bit number corresponding with the state of 16 pixels on the screen. The JackBitmapEditor uses red lines to represent the left edge of each of these 16 pixels groups (the placement of these groups depends on whether the mode is on 'Full Canvas' or 'Fit to Drawing'/'Rectanglar'). Use this checkbox to make these lines thick and red, rather than just red.

##### Canvas Size
Change the number of pixels in each row (width) and column (height). Pixel size refers to the size of the squares on the canvas, and should be decreased as necessary for very large canvas sizes.

##### Margin Type
You can choose the amount of the canvas that gets included in the generated code. On 'Fit to Drawing,' code will only be generated for the parts of the canvas that include the drawing. On 'Rectangular,' the code will be generated for the bitmap made by the 
smallest rectangle enclosing the rectangle. On 'Full Canvas,' code is generated for every pixel on the canvas, no matter how much space the drawing takes up. (Note that in
determaining where the drawing is, black pixels are interpreted as drawing normally, while white pixels are considered the drawing on inverted mode).

##### # Horizontal Shifts per Animation Frame (not on 'Full Canvas' mode)
If you plan on creating an animation by copying the code and shifting once horizontally between each frame, leave this on one. If you instead use the shift buttons x times between frames, set this to x. This field influences two things: the rate at which the subroutine name changes as you shift (if the corresponding checkbox is checked), and the "memory" of where the drawing was, which is used to generate code that erases residue of the drawing after it has shifted out of a 16 pixel word. 

##### Base Address
The Hack screen is made up of 256 rows of 32 words, each of wich is a 16-bit number that corresponds with 16 pixels. Location in the Jack code refers to the word that the drawing should start on in the screen. On 'Top Left' mode, the location (base address) referes to the top left corner of the drawing, and code in this mode matches that of previous versions of the BitmapEditor.html. Use 'Bottom Left' if you find it easier to specify screen coordinate locations in that format. 

##### Hack Assembly
By generating code directly in assembly, the result can be significantly more efficient than the Jack code that gets compiled into assembly (can be roughly 50-70% less machine instructions for certain drawings, but is always at least as efficient as the Jack code). This feature is useful for those who are programming in assembly, or wanting extreamly time-critical graphics (in which case, the programmer may need to compile their source code, add the graphics functions, and adapt the program to call the graphics functions according to the specification).

## Contributers
Golan Parashi, Ignacio del Valle Alles, Erik Umble, and Dino Krivić (Shimon Schocken and Noam Nisan developed the Jack programming language).
If you think of any improvements, feel free to submit an issue or a pull request.

## License
GNU General Public
Free to share, edit, and redistribute as long as you do so without charge.
