+++
title = "Application Structure"
+++

# Application Structure
The main element of Carbide is an application. This is the main struct allowing you to run Carbide. This application struct holds the state of the program, its environment, and allows processing events, and manages focus.

The outermost environment contains values provided by the outside environment, for example the OS. An example of this is the preferred text size, and accent color (To-Be). The environment is considered immutable, and functions using shadowing. This is described in further detail [here](@/docs/general/environment.md).

The main use of the application is to allow managing one or multiple scenes. A scene is an abstraction that holds a set of widgets that for example can be rendered. A classic example of a Scene is a Window. Another example is a WindowGroup, where the group allows spawning and managing multiple of the same window. Scenes are a hierarchy, and a Scene can contain child Scenes. For example this could be a window that requires a sub window, where if the window is closed all the child windows are also closed.

A scene decides how to present its containing widgets, and how to respond to events. A window might render to a desktop window and allow handling mouse and keyboard events. It might decide to render at a constant framerate, whenever the OS requests it, or when receiving events. A pdf, might only care about rendering, and layout.

To run your application, you call `.launch()` on the application struct. This is a blocking call, and will start the event loop behind the scenes and depending on the target (for example wasm), will handle the implementation details of launching the code.