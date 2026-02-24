cmake_minimum_required(VERSION 3.10)
project(LibZPAQFranz VERSION 1.0.0 LANGUAGES CXX)

add_library(LibZPAQFranz STATIC 
    src/Compressor.cpp
    src/ZPAQReader.cpp
    src/ZPAQWriter.cpp
)

if(MSVC)
  # include_directories(
  #   external/pthread-win32
  # )
  add_subdirectory(external/pthread-win32)
  target_link_libraries(LibZPAQFranz PRIVATE pthread)
  target_include_directories(LibZPAQFranz PRIVATE external/pthread-win32)

  target_include_directories(LibZPAQFranz PRIVATE external/unistd_h)
endif()

target_include_directories(LibZPAQFranz PUBLIC 
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)