# Simple CMake Configuration

This guide is to help setup a very basic CMake project for C++ projects.

## Prerequisites

- **CMake**
- **C++ Compiler** (e.g., g++, clang++, MSVC)

## Instructions

### 1. Setup Project

Create project directory:

```bash
mkdir my_project
```

Navigate into project:

```bash
cd my_project
```

### 3. Write `CMakeLists.txt`

Create `CMakeLists.txt` in the root of the project:

```bash
touch CmakeLists.txt
```

Modify and save `CMakeLists.txt` with this content:

```cmake
cmake_minimum_required(VERSION 3.13)

project(prog
  LANGUAGES CXX
  VERSION 0.1
)

add_executable(prog main.cpp)
```

### 4. Write `main.cpp`

Create `main.cpp` in the root of the project:

```bash
touch main.cpp
```

Modify and save `main.cpp` with this content:

```c++
#include <iostream>

int main() {
  std::cout << "Hello, World!\n";
  return 0;
}
```

### 5. Create `build` Directory

Create the `build` directory in the root of the project:

```bash
mkdir build
```

### 6. Build using `cmake`

Navigate into the `build` directory:

```bash
cd build
```

Generate build system files:

```bash
cmake ..
```

Build the project:

```bash
cmake --build .
```

### 7. Run `prog`

You should be able to see a `prog` binary. Try running it:

```bash
./prog
```

And should display:

`Hello, World!`
