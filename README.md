My c++ cmake template

# Usage
modify `CMakeUserPresets.json` and change the path of `VCPKG_ROOT` to your installation directory of your vcpkg<br>
refer to https://learn.microsoft.com/en-us/vcpkg/get_started/get-started to setup vcpkg<br>
only do the step one `1 - Set up vcpkg` and the copy the path to vcpkg to `CMakeUserPresets.json` in the `VCPKG_ROOT` field

# compile
for windows<br>
`cmake --preset=windows`<br>
for linux<br>
`cmake --preset=linux`<br>
and then<br>
`cmake --build build`
