cmake_minimum_required(VERSION 3.10)
project(LibZPAQFranz VERSION 1.0.0 LANGUAGES CXX)

add_library(LibZPAQFranz STATIC 
    src/Compressor.cpp
    src/ZPAQReader.cpp
    src/ZPAQWriter.cpp
)

target_include_directories(LibZPAQFranz PUBLIC 
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)