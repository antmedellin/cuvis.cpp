# CUVIS CPP SDK

## Importing Cuvis CPP SDK via CMake 

__In order to import cuvis to your CMake project, Cuvis must be installed. Download the installer for windows or the .deb files for Ubuntu 20.04 [here](https://cloud.cubert-gmbh.de/index.php/s/kKVtx0x2fmYqVgx).__

First, you need to add the directory containing *FindCuvisCpp.cmake* to *CMAKE_MODULE_PATH*. Assuming you added the *cuvis.c* repository as submodule as "${CMAKE_SOURCE_DIR}/cuvis.c" you can add it like so:
```
list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cuvis.cxx/")
```

Then you need to run the *find_package* function:
```
find_package(CuvisCpp REQUIRED)
```

If cuvis is installed to default locations, they are found automatically. Else, locate the cuvis.lib and the directory containing cuvis.h.

Finally, link against *cuvis::cuvis*. In the following example, the tarket *main* is linked against cuvis:
```
add_executable(main main.cpp)
target_link_libraries(main PRIVATE cuvis::cpp)
```

Please note, that linking against cuvis::cpp will enable c++17 on the target. 
