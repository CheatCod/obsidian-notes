# Window Manager
The WM shields the application from the frame buffer, graphics driver, and any other application window

Each window
- contain a canvas or drawing area for the application
- is independent and has no knowledge of other windows 
- has its own coordinate system

While the window manager owns the application windows, the application owns the content of the application window

WM also provides window related interactive components:
- Move handles, resize handles
- Close button, minimize, etc

