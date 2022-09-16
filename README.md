# panini

Panini is a visual tool for creating perspective views from panoramic and wide angle photographs. More than a pano viewer, more than a view camera, with features of both. For Linux/Unix, Win32, and Mac systems with OpenGL 2.0+.

## Dependencies

* Qt5 (qtbase5-dev, libqt5opengl5-dev)
* zlib (zlib1g-dev)
* cmake
## Get source code

```
git clone https://github.com/Mr-Precise/panini
cd panini
```

## Compile

``` 
mkdir build && cd build
cmake -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles" ..
make
```
