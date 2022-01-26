STLVIEW - The simple, pythonic STL viewer
Created by Liam Dempsey (10754465)


ABOUT:
STL View is a simple STL file viewer program written for Python3. This takes
advantage of TKinter's "create_polygon" method to draw triangles to the screen.
By taking a list of points and transforming them with some linear algebra,
a series coodinates can be calculated such that the given object can be drawn to
appear 3D, on a 2D display. Because of this, this program REQUIRES TKinter to be
installed on the system. TKinter is a python window API that comes preinstalled
on *most* packages of Python 3.


LIMITATIONS:
STL files have two types of formats: an ASCII format, and a binary format. This
program supports ONLY the latter of the two options, as this is the common form
seem almost universally.

Furthermore, as Python is an interpreted language and does not natively support
GPU acceleration, the functionality of this program is limited primarily by
performance. On my desktop PC, I experience considerable lag viewing objects
exceeding 2000 faces, however your experience may vary depending on your system.


FEATURES:
Not only does the program support the I/O of STL filetypes, but it also provides
a couple options for viewing them. By clicking and dragging on a location within
the window, the object will rotate with respect to mouse movement. Similarly, by
scrolling, the object can be zoomed in or out respectively.

The program also supports a couple viewing modes: wireframe, filled, shaded*,
and perspective/isometric viewports.

Some STL files have an unusual coordinate system, or are built to extreme
scales. Upon loading a file, STL View will automatically adjust to these
anomalies, by considering the height and width of the object, as well as
its location relative to the origin.

Lastly, the program performs basic error-checking when loading a file. It does
not attempt to fix these errors, however it will warn the user of them, in case
they are apparent when viewing the file.


USAGE:
Run the program like any other Python 3 program, typically: python stlview.py
for Windows, and python3 stlview.py for OSX/Unix.

Optionally, after stlview.py, provide a filename/path of a specific STL file to
view. If no path is specified, a generic cube will be displayed instead.
While the program is running, keybinds are provided to change view modes. With
the viewer window in focus, use any of the following options:

   'w' - Toggle wireframe display (cannot be disabled if fill is disabled)
         (Default: ENABLED)
   'c' - Toggle culling of backward-facing faces
         (Default: DISABLED)
   'f' - Toggle fill mode
         (Default: DISABLED)
   'l' - Toggle face layering, sorted by Z-coordinates (EXPERIMENTAL)
         (Default: DISABLED)
   's' - Toggle basic shading of faces with static light source
         (Default: DISABLED)
   'p' - Swap between perspective/isometric view
         (Default: ISOMETRIC)

Lastly, at any time, the user can press either the middle mouse button or the
right mouse button (dependent on OS and TK package) and the program will output
a small set of debug information to the console. This information includes:
canvas/window size, the object's relative rotation, the objects relative scale,
and how many vertices are currently being rendered.


INCLUDED FILES:
The ZIP file includes: this README file, the Python script 'stlview.py' itself,
and three example STL files. (Though the program will also support user-supplied
files!) 'wolf.stl' is the wolf entity model from the popular game Minecraft,
and king.stl and bishop.stl are both low-poly style chess pieces.
