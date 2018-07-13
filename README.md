GoWarcraft3
===========
[![Build Status](https://travis-ci.org/nielsAD/gowarcraft3.svg?branch=master)](https://travis-ci.org/nielsAD/gowarcraft3)
[![Build status](https://ci.appveyor.com/api/projects/status/a5cecrpfo0pe14ux/branch/master?svg=true)](https://ci.appveyor.com/project/nielsAD/gowarcraft3)
[![GoDoc](https://godoc.org/github.com/nielsAD/gowarcraft3?status.svg)](https://godoc.org/github.com/nielsAD/gowarcraft3)
[![License: MPL 2.0](https://img.shields.io/badge/License-MPL%202.0-brightgreen.svg)](https://opensource.org/licenses/MPL-2.0)

This library provides a set of go packages and command line utilities that implement Warcraft III protocols and file formats.

Tools
-----

|              Name            | Description |
|------------------------------|-------------|
|      [goop](./cmd/goop)      |Goop (GO OPerator) is a BNCS Channel Operator that can act as a bridge between Battle.net realms and Discord.|
|[bncsclient](./cmd/bncsclient)|A mocked Warcraft III chat client that can be used to connect to BNCS servers.|
|[w3gsclient](./cmd/w3gsclient)|A mocked Warcraft III game client that can be used to add dummy players to games.|
|  [bncsdump](./cmd/bncsdump)  |A tool that decodes and dumps BNCS packets via pcap (on the wire or from a file).|
|  [w3gsdump](./cmd/w3gsdump)  |A tool that decodes and dumps W3GS packets via pcap (on the wire or from a file).|
|   [w3mdump](./cmd/w3mdump)   |A tool that decodes and dumps w3m/w3x files.|

### Download

Official binaries for tools are [available](https://github.com/nielsAD/gowarcraft3/releases/latest). Simply download and run.

_Note: additional dependencies may be required (see [build](#build))._

### Build

```bash
# Linux dependencies
apt-get install --no-install-recommends -y build-essential cmake git golang-go libgmp-dev libbz2-dev zlib1g-dev libpcap-dev

# OSX dependencies
brew install cmake git go gmp bzip2 zlib libpcap

# Windows dependencies (use MSYS2 -- https://www.msys2.org/)
# Install WinPcap in C:\WinPcap (https://www.winpcap.org/devel.htm)
pacman --needed --noconfirm -S git mingw-w64-x86_64-toolchain mingw-w64-x86_64-go mingw-w64-x86_64-cmake

# Download vendor submodules
git submodule update --init

# Run tests
make test

# Build release files in ./bin/
make release
```

Packages
--------

|      Name      | Description |
|----------------|-------------|
|`file`          |Package `file` implements common utilities for handling Warcraft III file formats.|
|`file/blp`      |Package `blp` is a BLIzzard Picture image format decoder.|
|`file/mpq`      |Package `mpq` provides golang bindings to the StormLib library to read MPQ archives.|
|`file/w3m`      |Package `w3m` implements basic information extraction functions for w3m/w3x files.|
|`network`       |Package `network` implements common utilities for higher-level (emulated) Warcraft III network components.|
|`network/bnet`  |Package `bnet` implements a mocked BNCS client that can be used to interact with BNCS servers.|
|`network/dummy` |Package `dummy` implements a mocked Warcraft 3 game client that can be used to add dummy players to lobbies.|
|`network/lan`   |Package `lan` implements a mocked Warcraft 3 LAN client that can be used to discover local games.|
|`network/peer`  |Package `peer` implements a mocked Warcraft 3 client that can be used to manage peer connections in lobbies.|
|`protocol`      |Package `protocol` implements common utilities for Warcraft III network protocols.|
|`protocol/bncs` |Package `bncs` implements the Battle.net chat protocol for Warcraft III.|
|`protocol/w3gs` |Package `w3gs` implements the game protocol for Warcraft III.|

### Download

```bash
go get github.com/nielsAD/gowarcraft3/${PACKAGE_NAME}
```

### Import

```go
import (
    "github.com/nielsAD/gowarcraft3/${PACKAGE_NAME}"
)
```

_Note: additional dependencies may be required (see [build](#build))._

### Documentation

Documentation is available on [godoc.org](https://godoc.org/github.com/nielsAD/gowarcraft3)
