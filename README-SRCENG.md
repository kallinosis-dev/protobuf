CONFIG:
- Static Library
- No ZLib support

CMake stuff:
```
option(protobuf_INSTALL "Install protobuf binaries and files" OFF)
option(protobuf_BUILD_TESTS "Build tests" OFF)
option(protobuf_BUILD_CONFORMANCE "Build conformance tests" OFF)
option(protobuf_BUILD_EXAMPLES "Build examples" OFF)
option(protobuf_BUILD_PROTOBUF_BINARIES "Build protobuf libraries and protoc compiler" ON)
option(protobuf_BUILD_PROTOC_BINARIES "Build libprotoc and protoc compiler" ON)
option(protobuf_BUILD_LIBPROTOC "Build libprotoc" OFF)
option(protobuf_DISABLE_RTTI "Remove runtime type information in the binaries" OFF)
option(protobuf_TEST_XML_OUTDIR "Output directory for XML logs from tests." "")
option(protobuf_ALLOW_CCACHE "Adjust build flags to allow for ccache support." OFF)
option(protobuf_BUILD_SHARED_LIBS "Build Shared Libraries" OFF)
protobuf_MSVC_STATIC_RUNTIME # Default VPC option
option(protobuf_WITH_ZLIB "Build with zlib support" OFF)

set(protobuf_BUILD_LIBPROTOC ON)
set(protobuf_SHARED_OR_STATIC "STATIC")

include_directories(
  ${ZLIB_INCLUDE_DIRECTORIES}
  ${protobuf_BINARY_DIR}
  ${protobuf_SOURCE_DIR}/src)

  include(${protobuf_SOURCE_DIR}/cmake/utf8_range.cmake)
  include(${protobuf_SOURCE_DIR}/cmake/libprotobuf-lite.cmake)
  include(${protobuf_SOURCE_DIR}/cmake/libprotobuf.cmake)
    include(${protobuf_SOURCE_DIR}/cmake/libprotoc.cmake)
    include(${protobuf_SOURCE_DIR}/cmake/protoc.cmake)
```

Excluded:
- `./version.rc`