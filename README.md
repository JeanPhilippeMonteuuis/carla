Hello World

## Ubuntu 20.04

### Changes

#### update clang version
Use clang-10 in the following files:
- `BuildOSM2ODR.sh`
- `BuildPythonAPI.sh`
- `Setup.sh`
- `Prerequisites.Dockerfile`

### update link to XERCESC repo
In `Setup.sh`, look for `XERCESC_REPO`.
Replace the old url with a new url: `XERCESC_REPO=https://archive.apache.org/dist/xerces/c/3/sources/xerces-c-${XERCESC_VERSION}.tar.gz`

### specify client and server classes
See [Link](https://github.com/carla-simulator/carla/issues/2416).
In `test_streaming.cpp`, update the following line
- Line 63 and 96, replace `Client<tcp::Client>` by `carla::streaming::low_level::Client<tcp::Client>`
- Line 58 and 93, replace `Server<tcp::Server>` by `carla::streaming::low_level::Server<tcp::Server> `