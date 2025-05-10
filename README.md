My c++ cmake template

# Usage
modify `CMakeUserPresets.json` and change the path of `VCPKG_ROOT` to your installation directory of your vcpkg<br>
refer to https://learn.microsoft.com/en-us/vcpkg/get_started/get-started to setup vcpkg<br>
only do the step one `1 - Set up vcpkg` and the copy the path to vcpkg to `CMakeUserPresets.json` in the `VCPKG_ROOT` field

# Compile
for windows<br>
`cmake --preset=windows`<br>
for linux<br>
`cmake --preset=linux`<br>
and then<br>
`cmake --build build`

# Add New Package
first you add the package<br>
`vcpkg add port fmt`

and then you can install the package locally<br>
`vcpkg install`

and then you can add it in CMakeList.txt
```cmake
find_package(fmt CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE fmt::fmt)
```

you have to put it in between the add_executable like this
```cmake
find_package(fmt CONFIG REQUIRED)

add_executable(${PROJECT_NAME} ${SRCS})

target_link_libraries(${PROJECT_NAME} PRIVATE fmt::fmt)
```

and then you can use it
```cpp
#include <fmt/core.h>

int main()
{
    fmt::print("Hello World!\n");
    return 0;
}
```

Build and run<br>
`mkdir build && cd build`<br>
`cmake ..`<br>
`cmake --build .`<br>
`.\build\ProjectName.exe`