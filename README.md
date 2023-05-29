# Rayed BQN
Rayed BQN is a library made to write windowed applications using the [BQN programming language](https://mlochbaum.github.io/BQN/).
It inter-ops with [Raylib](https://github.com/raysan5/raylib), but changes a lot of the functions to be more in-lined with BQN's syntax.

Breaking changes to any feature in raylib.bqn should be expected for now, as this library is very young and experimental. 
raylib.ffi is only for bindings and therefore shouldn't change, so you can probably rely on those, but no guarantees.

# Getting started
Make a config file named "config.txt" at `./rayed_bqn/config.txt`. Each line of this file has one colon, with a keyword before the colon to indicate the config and after colon is a value to set that config to. If there are two lines with same config, then the bottom most line is picked.

The only values supported for now is the path to binary.

The binary being one of the following raylib.ddl/libraylib.so/etc.
examples are below:
```txt
raylibPath:raylib/lib/raylib.dll
```
```txt
raylibPath:raylib/lib/libraylib.so
```

To actually get the binary, follow the steps below:
## Windows
First download [Raylib](https://github.com/raysan5/raylib/releases/) with release `raylib-4.5.0_win64_mingw-w64` and place it inside this project, at the same level as tests, rayffi.bqn and raylib.bqn and rename the raylib folder to "raylib".

## Linux
Build [raylib](https://github.com/raysan5/raylib/) from source, and place the binaries generated from compiling into the folder ./raylib/lib.
You build raylib by first cloning 

## Mac
I have never tested mac, but it could be similar to Linux.


# Tested Raylib versions:

## Windows
  "raylib-4.5.0_win64_mingw-w64" on Windows 10, using CBQN version [cbqn-cygwin-gcc-mintty-standalone-x86_64](https://github.com/actalley/WinBQN/releases/tag/v0.0.8-alpha)
  
## Linux
  Raylib version 4.5.0 built from source on Pop!_OS.
  Raylib version 4.5.0 built from source on Ubuntu 22.04.2 LTS.
## Mac
  None yet

# Extra info
The most important file in ./raylib/lib/ is the binary file, which could be located at:
./rayed-bqn/raylib/lib/(BINARY).

The name of this binary file differs from OS to OS,

On Windows: raylib.dll.

On macOS: libraylib.dylib (I think)

On Linux: libraylib.so

# Ideologies
Having as little magic as possible, magic meaning magic numbers and global values (available to the user) changing outside user's control.

Mutations localized in namespaces like "button" are fine.
# Credits
Lots of thanks to [@dzaima](https://github.com/dzaima) for helping with FFI.

I owe credit to [@nulldatamap](https://gist.github.com/nulldatamap) for showing a lovely [example](https://gist.github.com/nulldatamap/30b10389bf91d6f25bb262da9c9e9709) to get me started with using FFI for BQN, and for making it easy to start with making this library.
