Minimum requirements
====================
1. [Git](https://git-scm.com/)
2. [Cmake > version 3.4](https://cmake.org/)
3. Modern C++ compiler
4. [Boost > version 1.58](https://www.boost.org/)

Download
========
## 1. Github

Clone HELICS source code from Github repository
```
git clone https://github.com/GMLC-TDC/HELICS.git
```
The default branch is the ```master``` branch. One can switch to any of the previous releases with
```
git checkout <HELICS-release-tag>
```
The list of available release tags is [here](https://github.com/GMLC-TDC/HELICS/tags).
For example, to switch to the latest release, v2.1.0, you would do
```
git branch v2.1.0
```

## 2. [Brew](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/package_manager.md) (MacOs)

## 3. [Conda](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/package_manager.md) (Windows, MacOS, Linux)

## 4. Precompiled binaries

Installation
============
HELICS can run on different platforms
1. [Windows](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/windows.md)
2. [Linux](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/linux.md)
3. [MacOS](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/mac.md)
4. [Docker](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/docker.md)

HELICS can run with different languages
1. C++
2. C
3. [Python](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/language.md)
4. [Matlab](https://github.com/GMLC-TDC/HELICS/blob/v2.1.0/docs/installation/language.md)

Tips on Installation
====================
HELICS installation instructions should be sufficient for you to get started, but, most likely, you will have some difficulty the first time you try to install HELICS (and its dependencies). Here are some tips that we've collected that should help your installation.
### Environment
1. Add environmental variables to your shell startup file.
2. When linking HELICS with your own application code, it's best to add HELICS libraries to the linker path. On linux, this can be set with the environment variable LD_LIBRARY_PATH. 
```
LD_LIBRARY_PATH=<path-to-helics-libraries>:$LD_LIBRARY_PATH
```
On Mac, you may need to additionally update DYLD_LIBRARY_PATH
```
DYLD_LIBRARY_PATH=<path-to-helics-libraries>:$DYLD_LIBRARY_PATH
```
### Linking
## C shared library
On Windows the linking file is helicsSharedLib.lib and the shared library is helicsSharedLib.dll, also likely required is libzmq-XXXX.dll this will be linked automatically

On Linux they are likely the same file with a .so extension
 
The header for the entire library is helics/chelics.h. The other headers are located in shared_api_library/*.h
 
For the C++98 wrapper the same libraries but the cpp98/helics.hpp header can be used
 
## C++
For linking with the underlying C++ interface.  This has much more strict C++ version requirements and will only run on C++14.  It is recommended to use cmake to do the linking and add a target HELICS::helics-static or HELICS::helics-shared  the appropriate header is helics/helics.hpp
 
An apps library is also available for advanced applications HELICS::helics-apps and helics/helics_apps.hpp header
