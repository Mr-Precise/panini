# panini

Panini is a visual tool for creating perspective views from panoramic and wide angle photographs. More than a pano viewer, more than a view camera, with features of both. For Linux/Unix, Win32, and Mac systems with OpenGL 2.0+.

## Installation
See [INSTALL](INSTALL.md).
## Dependencies

* Qt5 (qtbase5-dev, libqt5opengl5-dev)
* zlib (zlib1g-dev)
* cmake
## Get source code

```
git clone https://github.com/lazarus-pkgs/panini
cd panini
```

## Compile

``` 
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles" ..
make
```
