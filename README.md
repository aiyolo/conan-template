## About
This repo shows how to use conan to manage dependencies and build project with cmake.

## Setting conan build environment on windows

- install conan with version >=2.0

- generate default conan profile
```
conan profile detect --force
```

- set Ninja as generator in default profile.
just add a `[conf]` section under the botton 
```
[settings]
arch=x86_64
build_type=Release
compiler=msvc
compiler.cppstd=14
compiler.runtime=dynamic
compiler.version=193
os=Windows

[conf]
tools.cmake.cmaketoolchain:generator=Ninja
```

- clone this repo, and open developer Powershell under the project source folder, then run following line to install dependencies
```
conan install . -of build -b missing -s build_type=Debug
```

- configure project

```
cmake --preset conan-debug
```

- build project 

```
cmake --build --preset conan-debug
```

Done! Now you can run the project in `build` folder.