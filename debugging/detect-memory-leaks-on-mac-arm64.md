# Detect Memory Leaks on MacOS ARM64

## Overview

Unfortunately, **valgrind** isn't currently supported on ARM64 based systems. An alternative is a built-in CLI tool called **leaks**.

## Example

### 1. Create a memoryleak.cpp file

```c++
// memoryleak.cpp

#include <string>

int main(int argc, char *argv[]) {
  for (int i = 0; i < std::stoi(argv[1]); ++i) {
    int *memory = new int;
    // delete memory; // OOps, we're not deleting our memory!
  }
  return 0;
}
```

### 2. Compile using Clang

```bash
clang++ -g memoryleak.cpp -o prog
```

### 3. Run **leaks** Against **prog**

```bash
leaks --atExit --list -- ./prog 3
```

### Bonus: Display malloc stack logging

```bash
export MallocStackLogging=1
```

### Resources

- [YouTube Video](https://www.youtube.com/watch?v=bhhDRm926qA)
