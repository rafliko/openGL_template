<img src="https://upload.wikimedia.org/wikipedia/commons/e/e9/Opengl-logo.svg" width='300' style='display: block; margin: auto;'>

# OpenGL project template

### Compiling the project:
Run the following commands in projects root directory:
```
cmake -S . -B build -G Ninja
cmake --build build --config DEBUG --target all
```
The compiled program should be in the build directory.

---

### Windows notes:
Install [cmake](https://cmake.org/), [msvc](https://visualstudio.microsoft.com/pl/downloads/#build-tools-for-visual-studio-2026), [vcpkg](https://github.com/microsoft/vcpkg) and glfw3 (through vcpkg).\
Run the commands through *"Developer PowerShell for VS 18"* and add the following argument to the cmake configuration command:
```
# WARNING: Change the path to your vcpkg installation
-DCMAKE_TOOLCHAIN_FILE=path/to/vcpkg/scripts/buildsystems/vcpkg.cmake
```

---

### Linux notes:
Install cmake, gcc and glfw3.

---

### MacOS notes:
Install cmake and glfw3 through [homebrew](https://brew.sh/).
