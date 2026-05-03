[LEGACY] LWJGL - Lightweight Java Game Library
======

> **WARNING**
> 
> This is the repository of the original LWJGL, which is no longer actively maintained. Unless you have released a product that uses LWJGL 2.x, you should probably be looking at [LWJGL 3](https://github.com/LWJGL/lwjgl3).

The Lightweight Java Game Library (LWJGL) is a solution aimed directly at professional and amateur Java programmers alike to enable commercial quality games to be written in Java. 
LWJGL provides developers access to high performance crossplatform libraries such as OpenGL (Open Graphics Library), OpenCL (Open Computing Language) and OpenAL (Open Audio Library) allowing for state of the art 3D games and 3D sound.
Additionally LWJGL provides access to controllers such as Gamepads, Steering wheel and Joysticks.
All in a simple and straight forward API.

Website: [http://legacy.lwjgl.org](http://legacy.lwjgl.org)
Forum: [http://forum.lwjgl.org](http://forum.lwjgl.org)
Bugs/Suggestions: [https://github.com/LWJGL/lwjgl/issues](https://github.com/LWJGL/lwjgl/issues)

Compilation
-----------

LWJGL requires a JDK and Ant installed to compile, as well as your platforms native compiler to compile the JNI.

Run both build targets when changing LWJGL:

* `ant jars` - regenerates sources, compiles Java classes, and updates `libs/lwjgl.jar` and utility jars.
* `ant compile_native` - compiles the platform JNI library and updates `libs/linux/liblwjgl64.so` on 64-bit Linux.

For a clean local release build:

```sh
ant jars
ant compile_native
```

Usage
-----

Grab the client or Minecraft command line you already use and change it to point to this build:

* Point `-Dorg.lwjgl.librarypath` / `-Djava.library.path` at the extracted [natives](https://github.com/BrandowLucas/lwjgl2-4-Linux/releases/download/2.9.6/natives-2.9.6.zip).
* Change the classpath (`-cp`) so it uses this [LWJGL jar](https://github.com/BrandowLucas/lwjgl2-4-Linux/releases/download/2.9.6/lwjgl-2.9.6.jar).

Lunar Client
------------

Apparently Lunar Client blocks loading our own LWJGL jar on its classpath, so there is a very hacky way to load it via patching the Lunar bake cache itself. If anyone is using this patched LWJGL and wants to use it on Lunar Client, open an issue in this repo.
