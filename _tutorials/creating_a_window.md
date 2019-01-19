---
layout: default
title: Creating A Window
---

The first thing you'll probably want to do is open a window. In SFML this is very straightforward, you just create a window object

```cpp
sf::Window window({800,600}, "My first window");
```

However if you do that and nothing else, the window will close as soon as it goes out of scope. You need to keep your program alive while the window is open, and this will form the basis of your main loop

```cpp
while(window.isOpen())
{
    // Do stuff
}
```

This still won't create a complete program though. As we aren't handling any of the window events from the OS, it will think the process has died and in most cases will show some sort of warning to the user. To solve this we need to always make sure we are processing events. it's typical to do this first in your main loop

```cpp
while(window.isOpen())
{
    while(window.pollEvent(event))
    {
        // Handle events
    }
    // Do stuff
}
```

To finish things off, there's one very important event we have to handle, which is `sf::Event::Closed'. This is the event which is sent when the user tries to close the window (usually by clicking the close button). When this event is received we must close the window. So inside the event polling, we do something like this

```cpp
if (event.type == sf::Event::Closed)
{
    window.close();
}
```
