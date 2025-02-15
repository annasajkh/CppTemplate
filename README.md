My c++ cmake template

# Usage
modify `CMakeUserPresets.json` and change the path of `VCPKG_ROOT` to your installation directory of your vcpkg<br>
refer to https://learn.microsoft.com/en-us/vcpkg/get_started/get-started to setup vcpkg

# compile
for windows<br>
`cmake --preset=windows`<br>
for linux<br>
`cmake --preset=linux`<br>
and then<br>
`cmake --build build`
