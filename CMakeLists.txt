cmake_minimum_required(VERSION 3.10)

# Project name and version
project(MuPDF VERSION 1.0 LANGUAGES C CXX)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add include directories
include_directories(include)

# Add source files
file(GLOB_RECURSE SOURCES source/*.c platform/*.c thirdparty/harfbuzz/src/*.c thirdparty/freetype/src/*.c thirdparty/jbig2dec/*.c thirdparty/jpeg/*.c thirdparty/mujs/*.c thirdparty/openjpeg/*.c thirdparty/png/*.c thirdparty/zlib/*.c)

file(GLOB_RECURSE INCLUDES thirdparty/*.h)

include_directories(
        include
        ${INCLUDES}
)

# Add the executable
add_executable(mupdf ${SOURCES})

# Link libraries if any (example: zlib, jpeg, etc.)
# find_package(ZLIB REQUIRED)
# target_link_libraries(mupdf ZLIB::ZLIB)

# Add any additional libraries or dependencies here
# target_link_libraries(mupdf <library_name>)

# Add definitions if needed
# add_definitions(-D<definition>)

# Specify additional compiler options if needed
# set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall -Wextra")
# set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra")