---
alias: []
---
# Pimpl: Pointer to Implementation
❌✔️✅📗

We want to be able to hide private members of a class to the client.

Consider the `XWindows` example
```ad-example
`xwindows.h`:
~~~c

#ifndef __WINDOW_H__
#define __WINDOW_H__
#include <X11/Xlib.h>
#include <string>

class Xwindow {
    Display *d;
    Window w;
    int s;
    GC gc;
    unsigned long colours[10];
  public:
    Xwindow(int width=500, int height=500);  // Displays the window.
    ~Xwindow();                              // Destroys the window.
    Xwindow(const Xwindow&) = delete; // Disallow copy and assignment
    Xwindow &operator=(const Xwindow&) = delete;

    static const int MAX_NUM_COLOURS; // Available colours.
    enum class Colour {White=0, Black, Red, Green, Blue}; 

    // Draws a rectangle
    void fillRectangle(int x, int y, int width, int height, 
        Xwindow::Colour colour=Colour::Black);

    // Draws a string
    void drawString(int x, int y, std::string msg);
};

#endif
~~~
```

If we change any of the private fields, all files referencing this header file need to be recompiled, thus creating inefficiency.

We can wrap all the private fields in a new struct, and have a pointer to it.

`xwindows.h`:
```c
#ifndef __WINDOW_H__
#define __WINDOW_H__
#include <X11/Xlib.h>
#include <string>

class Xwindow {
	XWindowImpl * pImpl; // pointer to the implementation
  public:
    Xwindow(int width=500, int height=500);  // Displays the window.
    ~Xwindow();                              // Destroys the window.
    Xwindow(const Xwindow&) = delete; // Disallow copy and assignment
    Xwindow &operator=(const Xwindow&) = delete;

    static const int MAX_NUM_COLOURS; // Available colours.
    enum class Colour {White=0, Black, Red, Green, Blue}; 

    // Draws a rectangle
    void fillRectangle(int x, int y, int width, int height, 
        Xwindow::Colour colour=Colour::Black);

    // Draws a string
    void drawString(int x, int y, std::string msg);
};

#endif
```

`xwindows.cc`:
```c
#include <>...
struct XWindowImpl {
    Display *d;
    Window w;
    int s;
    GC gc;
    unsigned long colours[10];
};
...
```
Relate: [[]]