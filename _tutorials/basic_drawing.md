---
layout: default
title: Basic drawing
---

Now you have a working SFML window, it's time to draw something. In the previous example we just created a basic SFML window, which doesn't support drawing SFML objects (but can be used with other rendering backends if you so choose). To draw with SFML, we need to create an `sf::RenderWindow` object instead. Thankfully this is just as simple:

```cpp
sf::Window window({800,800}, "My first RenderWindow");
```

Now we can start drawing! SFML has built in support for drawing simple coloured shapes, and most tutorials start by drawing the famous green circle. So let's start by creating an `sf::CircleShape` object, big enough to fill the window. We also set the fill colour to green

```cpp
auto size = window.getSize();
sf::CircleShape circle(size.x / 2.f);
circle.setFillColor(sf::Color::Green);
```

Now we've created the shape object, we have to draw it. All drawing in SFML should follow the same cycle: *clear* the window, *draw* all the objects then *display* those objects in the window. So to draw our circle, we simply need to do this in our main loop while the window is open

```cpp
window.clear();
window.draw(circle);
window.display();
```


