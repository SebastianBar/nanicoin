NaniCoin is a kawaii cryptomonea focused on providing a nice and beautiful way of... Doing cryptostuff. Gives you anonymity via untraceable and unlinkable nanitransactions.

## Building NaniCoin

### On *nix

Dependencies: GCC 4.7.3 or later, CMake 2.8.6 or later, and Boost 1.58 or later (avoid 1.66 for now).

You may download them from:

* http://gcc.gnu.org/
* http://www.cmake.org/
* http://www.boost.org/
* Alternatively, it may be possible to install them using a package manager.

To build, change to a directory where this file is located, and run `make`. The resulting executables can be found in `build/release/src`.

**Advanced options:**

* Parallel build: run `make -j<number of threads>` instead of `make`.
* Debug build: run `make build-debug`.
* Test suite: run `make test-release` to run tests in addition to building. Running `make test-debug` will do the same to the debug version.
* Building with Clang: it may be possible to use Clang instead of GCC, but this may not work everywhere. To build, run `export CC=clang CXX=clang++` before running `make`.

### On Windows
Dependencies: MSVC 2013 or later, CMake 2.8.6 or later, and Boost 1.58 or later (avoid 1.66 for now). You may download them from:

* http://www.microsoft.com/
* http://www.cmake.org/
* http://www.boost.org/

To build, change to a directory where this file is located, and run these commands: 
```
mkdir build
cd build
cmake -G "Visual Studio 14 Win64" ..
```

If you are building on an older processor without AVX support, add the following options to cmake:
```
-DWITH_AVX2=0
```

You may find it helpful to explicitly include Boost library paths:
```
cmake -G -G "Visual Studio 14 Win64" -DBOOST_ROOT="C:\boost_1_65_1_built" -DBOOST_INCLUDEDIR="C:/boost_1_65_1_built/lib32-msvc-14.0" -DBOOST_LIBRARYDIR="C:\boost_1_65_1_built\libs" ..
 ```

And then Build from within MS Visual Studio, or using MSBuild:
```
msbuild NaniCoin.sln /p:Configuration=Release /m
 ```
