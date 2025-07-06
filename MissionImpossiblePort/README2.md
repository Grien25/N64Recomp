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

## Generating the ELF and Symbol Files

To run the recompiler you need an ELF with matching symbol information. A common
approach is to use an existing disassembly or decompilation setup such as the
[n64decomp](https://github.com/n64decomp) workflow. These projects extract code
and data from a legally obtained ROM and build an ELF that can be used with
tools like **N64: Recompiled**.

1. Set up a decompilation project (search for "n64decomp setup" if you are
   unfamiliar with these tools).
2. Follow the build steps from that project to produce `mi.elf` and a list of
   symbols (often in `symbols.txt` or a `.toml` file).
3. Copy the generated files into this folder and update the paths in
   `mi.toml`.

These files are not included in this repository and must be generated from your
own copy of the game.

This is only a starting point—you may need to adjust the configuration and provide additional tooling depending on the specifics of your ROM and runtime environment.
