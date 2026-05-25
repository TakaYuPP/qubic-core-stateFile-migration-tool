This is the migration tool to convert only the state file of Qswap SC.

## How to build and run

Install [CMake](https://cmake.org/download/) (3.15 or newer). From the repository root, create a `build` directory and configure the project:

```bash
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
```

### Windows (Visual Studio 2022)

After `cmake ..`, open `MigrationTool.sln` in Visual Studio 2022, build **Release**, then run:

`build\Release\qubic-stateFile-migration-tool.exe`

(Exact output path may vary depending on the generator.)

### Linux

Install a C++17 compiler (for example `g++` or `clang++`) and build:

```bash
cmake --build . --config Release
./qubic-stateFile-migration-tool
```

The CPU must support **AVX2**, **BMI**, and **LZCNT** (these are enabled automatically for GCC/Clang).

Place `contract0013.215` in the working directory before running the tool. It writes `contract0013.215.new` and optional CSV exports alongside the input file.

### After migration

Check the timestamp and size of the output state file (`contract0013.215.new`).
