<img src="https://upload.wikimedia.org/wikipedia/commons/e/e9/Opengl-logo.svg" width='300' style='display: block; margin: auto;'>

# OpenGL project template

### Compiling the project:
Install a c/c++ compiler and cmake. Then run the following commands in this projects root directory:
```
cmake -S . -B build
cmake --build build --config DEBUG --target all
```
Program will be compiled into the newly-created *'build'* directory.

---

### Windows notes:
On windows you should use the [MSVC compiler](https://visualstudio.microsoft.com/pl/downloads/#build-tools-for-visual-studio-2026) and run the commands through *'Developer PowerShell for VS'*.