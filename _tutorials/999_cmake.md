---
layout: tutorial
title: Getting started with CMake
---

# Project setup
If you plan on building your project for more than one platform (or even with more than one compiler or IDE) It's extremely beneficial to invest in a project generator. My weapon of choice here is CMake.

To get started, first install cmake, then create a new text file in the root of your project called `CMakeLists.txt`.

The first thing to add is this line, which sets the minimum version of cmake your project requires (It's usually best to just set this to the version you start off with)

```
cmake_minimum_required(VERSION 3.12)
```

Next, you declare your project name:

```
project(MyProject)
```

Then to add an executable to your project, you just call `add_executable` with a name and the source files for it. e.g. if you just have a main file:

```
add_executable(MyProject main.cpp)
```

At this point you've got the bare minimum required for a cmake project.

# Configuring

Now the project is setup, you just need to generate the project files. This just involves running cmake and passing it the path to the CMakeLists.txt file you just created. By default it will generate all the project files in the directory you run it in, so it's best to run it from a separate directory to your source. Often this is just a subdirectory in your project, so once you've opened a terminal in your project root, you can run something like this:

```
mkdir build && cd build
cmake ..
```
And this should produce a bunch of project files in the "build" folder of your project. Cmake is pretty smart, and will find the best default compiler/toolchain for your environment (usually MSVC on windows, xcode on macOS, etc.)

# Building

The great thing about cmake is the configure and build process is the same on all platforms, so once you've configured the project successfully as above, you just need to run the build command to build your project:

```
cmake --build .
```

The last parameter here is the path to the build folder which I'm assuming you're still in after configuring. If you've moved then this path will be different.
