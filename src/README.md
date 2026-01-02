# Building with CMake

## Dependencies

Install the required development packages:

### Ubuntu/Debian
```bash
sudo apt-get install cmake libjson-c-dev libusb-1.0-0-dev
```

### Fedora/RHEL/CentOS
```bash
sudo dnf install cmake json-c-devel libusb1-devel
```

### Arch Linux
```bash
sudo pacman -S cmake json-c libusb
```

## Build Instructions

```bash
cd /path/to/Ultimarc-linux/src
mkdir build
cd build
cmake ..
make
```

The `umtool` executable will be created in the build directory.

## Installation (Optional)

To install the executable and library system-wide:

```bash
sudo make install
```

This will install:
- `umtool` binary to `/usr/local/bin`
- `libultimarc.a` library to `/usr/local/lib`
- Header files to `/usr/local/include/ultimarc`

## Running

```bash
./umtool --help
```

For more information about configuration and usage, see the main README files in the parent directory.
