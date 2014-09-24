Display Server
--------------

- A display server handles all display events from the Keyboard, Mouse and hands
    these events to client applications (the applications which respond to such
    events).
- X11 and Wayland are two major display servers with their own communication protocol.
- A **display manager** starts the Display Server and authenticates the user.

Windowing System
----------------

- A windowing system implements the WIMP (windows, icons, menu, pointer) paradigm.
- It handles the drawing of windows and their relative arrangment (tiling, overlap).
- **Widget Kits**: The different widgets are drawn from some widget kit like Qt, GTK+.
- **Windowing Systme**: X11 and Wayland are considered to be windowing systems.
    - X11 does not handle windowing but passes it onto a **Window manager**.
    - Wayland handles windowing itself.

Desktop Environment
-------------------

- A desktop environement helps realize the desktop metaphor.
- It contains all GUI elements and a consistent UI.
- GNOME and KDE are two popular Desktop Environments.

