cmake_minimum_required(VERSION 3.17...3.18)
project(esp32_fft)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME)
    set_property(GLOBAL PROPERTY USE_FOLDERS ON)
    include(CTest)
    include(GoogleTest)
endif()

add_library(fftlib INTERFACE)
target_include_directories(fftlib INTERFACE include/)

if(CMAKE_PROJECT_NAME STREQUAL PROJECT_NAME AND BUILD_TESTING)
    add_subdirectory(test)
endif()