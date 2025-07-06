# Mission: Impossible Recompilation Example

This folder provides a minimal setup for using **N64: Recompiled** to create a port of *Mission: Impossible*.

## Directory layout

- `MI/` – place your legally obtained `Missionimpossible.z64` ROM here.
- `mi.toml` – example configuration file for the recompiler.

## Usage overview

1. Build the recompiler:
   ```sh
   git submodule update --init --recursive
   mkdir build && cd build
   cmake ..
   cmake --build .
   ```
2. Obtain an ELF with symbol information for Mission: Impossible and place it alongside `mi.toml` (update the paths in the TOML as needed).
3. Run the recompiler:
   ```sh
   ./N64Recomp ../mi.toml
   ```
4. Compile the generated C files together with a runtime such as [N64ModernRuntime](https://github.com/N64Recomp/N64ModernRuntime) to produce a native executable.

This is only a starting point—you may need to adjust the configuration and provide additional tooling depending on the specifics of your ROM and runtime environment.
