
add_executable(fftproperties fft_properties_test.cpp)
target_link_libraries(fftproperties PRIVATE fftlib gtest gmock gtest_main)
gtest_discover_tests(fftproperties WORKING_DIRECTORY ${PROJECT_DIR} PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "${PROJECT_DIR}")