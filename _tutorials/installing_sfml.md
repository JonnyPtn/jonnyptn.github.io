---
layout: default
title: Installing SFML
---

There are a few ways to do it.

## Build it from source
This is my preferred way to install SFML. It ensures that you build SFML with the same toolchain you use to build your projects and it's straightforward to do on all platforms:

Clone SFML source code:
```
git clone https://github.com/sfml/sfml
cd sfml
```

Configure CMake:
```
mkdir build && cd build
cmake ..
```

Build
```
cmake --build . --target install
```

## Download pre-built binaries

Download pre-built binaries for your platform [here](https://www.sfml-dev.org/download/sfml/2.5.1/)

## Install from your package manager

SFML is available in a bunch of different package managers:

vcpkg (All platforms)
apt (Linux)
Brew (macOS)

