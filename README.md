# Soul at the seaside

## Clone

To clone project repository use this commands

```
git clone https://github.com/luckybet100/soul_at_the_seaside.git
git submodule init
git submodule update
```

## Build

We use CMake as a build system, so to build this repo use this commands:

```
mkdir build
cd build
cmake ..
make
ctest // (optional command to run tests)
./soul_at_the_seaside
```

You can use Ninja to spped up builds (build directory should be empty before generating ninja build scripts):

```
mkdir build
cd build
cmake -G ninja ..
ninja
ninja test // (optional command to run tests)
./soul_at_the_seaside
```