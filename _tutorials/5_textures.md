---
layout: tutorial
title: Textures
---

Now you're drawing simple coloured shapes, but you probably want better graphics than that, which is where textures come in. `sf::Texture` can load most popular image formats, and are then easily applied to most of SFMLs drawable objects, using `sf::Sprite` as an example:

```cpp
sf::Sprite sprite;
sf::Texture texture;
texture.loadFromFile("MyTexture.png");
sprite.setTexture(texture);
```

By default this will show all of the image file you've loaded, which may not be what you want, so you can also specify a texture rect. This code will make the sprite show an 8 pixel square area of the texture, with the top left of that square at the position `(16, 16)`

```cpp
sf::Rect textureRect = {16, 16, 8, 8}
sprite.setTextureRect(textureRect)
```

Texture are destroyed when the object goes out of scope, so if your texture isn't showing, make sure the object still exists.