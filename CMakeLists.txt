cmake_minimum_required(VERSION 3.18)
project(esp32_fft)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
    include(CTest)
endif()

add_library(fftlib INTERFACE)
target_include_directories(fftlib INTERFACE include/)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME AND BUILD_TESTING)
    include(GoogleTest)
    add_subdirectory(test)
    add_subdirectory(extern/googletest)
endif()