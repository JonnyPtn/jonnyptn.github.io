---
layout: tutorial
title: Getting started with iOS
---

Building SFML for iOS is really straightforward. There is a CMake toolchain file included for iOS, so all you have to do is pass that to cmake (and make sure you're using the Xcode generator!)

```
cmake .. -DCMAKE_TOOLCHAIN_FILE=../cmake/toolchains/iOS.toolchain.cmake -GXcode
```

then build and install it as you would normally

```
cmake --build . --target install
```

The simplest way to use SFML in your project after that is to copy the SFML iOS toolchain file into your project then follow these same steps
