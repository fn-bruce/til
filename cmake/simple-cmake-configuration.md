# Simple CMake Configuration

This guide is to help setup a very basic CMake project for C++ projects.

## Prerequisites

- **CMake**
- **C++ Compiler** (e.g., g++, clang++, MSVC)

## Instructions

### 1. Setup Project

Create project directory:

```sh
mkdir my_project
```

Navigate into project:

```sh
cd my_project
```

### 3. Write `CMakeLists.txt`

Create `CMakeLists.txt` in the root of the project:

```sh
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

```sh
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

```sh
mkdir build
```

### 6. Build using `cmake`

Navigate into the `build` directory:

```sh
cd build
```

Generate build system files:

```sh
cmake ..
```

Build the project:

```sh
cmake --build .
```

### 7. Run `prog`

You should be able to see a `prog` binary. Try running it:

```sh
./prog
```

And should display:

`Hello, World!`
