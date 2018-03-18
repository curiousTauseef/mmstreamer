# Install

## 1. Install dependencies

### 1.1. Needed packages

- build-essential
- libv4l-dev
- libx11-dev
- libxext-dev
- libjpeg8-dev
- libpng16-dev
- zlib1g

**Example on ubuntu 16.04 :**
```
    $ sudo apt update
    $ sudo apt install build-essential
    $ sudo apt install libv4l-dev
    $ sudo apt install libx11-dev
    $ sudo apt install libxext-dev
    $ sudo apt install libjpeg8-dev
    $ sudo apt install libpng16-dev
    $ sudo apt install zlib1g-dev
```

### 1.2. Maybe necessary to build SDL2_ttf (in case SDL2-based drawer is used)
```
Create symbolic link to libGL.so.1

Example on ubuntu 16.04 64 bits:

$ sudo ln -s /usr/lib/x86_64-linux-gnu/mesa/libGL.so.1 /usr/lib/libGL.so
```

## 2. Build / Reset

### 2.1. Build and install mmstreamer
```
$ cd <path_to_mmstreamer_sources>
$ make all install
```

**Note** : <path_to_mmstreamer_sources>/out/ is created. It contains :
```
build/ : build informations
mmstreamer/ :
    |
    --> Application's binary in bin/
    |
    --> .h files in inc/ (to use dynamic libraries)
    |
    --> Dynamic libraries in lib/ (Can be used alone; no need of other modules)
    |
    --> Xml config files in res/

mmstreamer.tar.gz : "mmstreamer/" directory packaged
```

### 2.2. Clean build directory
```
$ cd <path_to_mmstreamer_sources>
$ make clean-all
```
or
```
$ make mrproper-all
```

### 2.3. Clean a particular module
```
$ cd <path_to_mmstreamer_sources>
$ make -f build/Makefile.<xxx> clean-<xxx>
```
or
```
$ make -f build/Makefile.<xxx> mrproper-<xxx>

<xxx> : vid, deps, net, gfx, ... respectively for "Videos", "Dependencies", "Network", "Graphics", ...
```