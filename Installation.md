# Installing PepeMint

This section provides detailed instructions for installing and configuring the PepeMint software.

## System Requirements

- **OS:** Windows 10/11, macOS 10.15+, Ubuntu 20.04+, Debian 10+
- **Processor:** Minimum 2 cores, 4 cores recommended
- **RAM:** Minimum 4 GB, 8 GB recommended
- **Storage:** At least 100 GB free space (for full node)
- **Internet Connection:** Minimum 5 Mbps, 10+ Mbps recommended

---

## Building from Source

### Dependencies

Before compiling PepeMint, you need to install the following dependencies:

### Ubuntu/Debian

```bash
sudo apt-get update
sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-all-dev libdb-dev libdb++-dev
```

### macOS

```bash
brew install automake berkeley-db4 libtool boost miniupnpc openssl pkg-config python qt
```

### Windows

For Windows, it is recommended to use the MSYS2 environment:

1. Download and install MSYS2 from the [official website](https://www.msys2.org/).
2. Open MSYS2 and install the required packages:

```bash
pacman -Syu
pacman -S base-devel mingw-w64-x86_64-toolchain mingw-w64-x86_64-boost mingw-w64-x86_64-openssl mingw-w64-x86_64-libevent mingw-w64-x86_64-db
```

---

## Compilation

Clone the repository:

```bash
git clone https://github.com/thepepemint/pepemint-source.git
cd pepemint-source
```

Build the project:

```bash
./autogen.sh
./configure
make
```

After successful compilation, the executables will be located in the `src/` directory.

---

## Using Prebuilt Binaries

You can also download prebuilt binary files from:

- The [official website](https://pepemint.me/downloads)
- The [GitHub Releases section](https://github.com/thepepemint/pepemint-source/releases)

This allows you to skip building from source and use ready-to-run binaries.

---

## Verifying the Installation

After installation, verify that PepeMint is working by running:

```bash
./src/pepemintd --version
```

This should display the current version of the PepeMint daemon.

---

## Configuring the Configuration File

Create a `pepemint.conf` file in the PepeMint data directory:

### Default paths:

- **Windows:** `%APPDATA%\PepeMint\`
- **macOS:** `~/Library/Application Support/PepeMint/`
- **Linux:** `~/.pepemint/`

### Example configuration:

```ini
rpcuser=pepemintuser
rpcpassword=YOUR_STRONG_PASSWORD
rpcallowip=127.0.0.1
listen=1
server=1
```

---

## Running the Node

To start the PepeMint node:

```bash
./src/pepemintd -daemon
```

This launches the node in background (daemon) mode and begins syncing with the blockchain.

---

## Next Steps

After successful installation and launch:

- Refer to the [usage guide](usage.md) for command-line usage and wallet instructions.
- Configure your node for PoW mining or PoS staking (depending on use case).
- Join the PepeMint community to stay updated and contribute.
