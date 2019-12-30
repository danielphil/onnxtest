cmake_minimum_required(VERSION 3.16)

set(CMAKE_OSX_DEPLOYMENT_TARGET "10.14" CACHE STRING "Minimum OS X deployment version")
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(OnnxTest)

set(ONNXRUNTIME_LIB libonnxruntime.1.1.0.dylib)
link_directories(~/Development/onnxruntime/build/Linux/)
include_directories(~/Development/onnxruntime/include/onnxruntime)

#include_directories(src)
file(GLOB SOURCES "src/*.cpp")
file(GLOB HEADERS "src/*.h")

add_executable(prog ${HEADERS} ${SOURCES})
target_link_libraries(prog ${ONNXRUNTIME_LIB})
