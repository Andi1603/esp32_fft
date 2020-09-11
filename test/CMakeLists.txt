add_subdirectory("${PROJECT_SOURCE_DIR}/extern/googletest" "extern/googletest")

set_target_properties(gtest gtest_main gmock gmock_main PROPERTIES FOLDER "extern/googletest")

macro(package_add_test TESTNAME) 
    add_executable(${TESTNAME} ${ARGN})
    target_link_libraries(${TESTNAME} PRIVATE fftlib gtest gmock gtest_main)
    gtest_discover_tests(${TESTNAME} WORKING_DIRECTORY ${PROJECT_DIR} PROPERTIES VS_DEBUGGER_WORKING_DIRECTORY "${PROJECT_DIR}")
    set_target_properties(${TESTNAME} PROPERTIES FOLDER "tests")
endmacro()

package_add_test(fftPropertiesTest fft_properties_test.cpp)