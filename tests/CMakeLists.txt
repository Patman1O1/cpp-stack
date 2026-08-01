#-----------------------------------------------------------------------------------------------------------------------
# Google Test
#-----------------------------------------------------------------------------------------------------------------------
include(GoogleTest)
enable_testing()

#-----------------------------------------------------------------------------------------------------------------------
# Target: cpp_stack_test
# Alias: collections::cpp_stack_test
# Type: Executable
# Dependencies: GTest::gtest_main, GTest::gmock_main, collections::cpp_stack_headers
#-----------------------------------------------------------------------------------------------------------------------
# Target definition
add_executable(cpp_stack_test)

# Target alias
add_executable(collections::cpp_stack_test ALIAS cpp_stack_test)

# Target sources
target_sources(cpp_stack_test
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/cpp_stack_test.cpp
)

# Target dependencies
target_link_libraries(cpp_stack_test
    PRIVATE
        collections::cpp_stack_headers
        GTest::gtest_main
        GTest::gmock_main
)

# Test discovery
gtest_discover_tests(cpp_stack_test)