# Command-not-found for neoterm

This repo contains sources for the command-not-found utility used in neoterm.
Apart from the sources for the binary (`command-not-found.cpp`), it also
contains a script to generate lists of commands for the various official
repositories:

- [main repo](https://github.com/juic3b0x/neoterm-packages/tree/dev/packages)
- [root repo](https://github.com/juic3b0x/neoterm-packages/tree/dev/root-packages)
- [x11 repo](https://github.com/juic3b0x/neoterm-packages/tree/dev/x11-packages)

## Building command-not-found

To build the package, `cmake` and a c++ compiler (for example `g++` or `clang++`)
needs to be installed.
Apart from `cmake` and a C++ compiler, `nodejs` is also needed in order to
generate list of commands.
To do an out of source build, run these commands from the command-not-found
directory:

```sh
mkdir build && cd build
cmake ..
make
```

This will generate command lists by running `./generate-db.js`, and create
a command-not-found binary which can be tested directly.
To then install the program, run:

```sh
make install
```

This installs command-not-found to `CMAKE_INSTALL_PREFIX/libexec/neoterm`, which
is where command-not-found resides in neoterm.

## Updating the command lists

In order to update the command lists, just a rebuild of command-not-found
is to be done by bumping the `NEOTERM_PKG_REVISION` in build recipe of
command-not-found.
