# My c++ cmake template

### Compiling Debug
```shell
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
cmake --build . --parallel 1000 --config Debug
```

### Compiling Release
```shell
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release ..
cmake --build . --parallel 1000 --config Release
```
