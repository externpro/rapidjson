if(COMMAND xpFindPkg)
    xpFindPkg(PKGS Threads GTest)
    enable_testing()
    get_target_property(GTEST_INCLUDE_DIR GTest::gtest INTERFACE_INCLUDE_DIRECTORIES)
    include_directories(SYSTEM ${GTEST_INCLUDE_DIR})
    set(TEST_LIBRARIES GTest::gtest GTest::gtest_main)

    # Override C++ standard to C++14 for test targets only
    # (Google Test v1.16.0+ requires C++14)
    set(CMAKE_CXX_STANDARD 14)
    set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
    add_custom_target(tests ALL)
    add_subdirectory(perftest)
    add_subdirectory(unittest)
else()
    find_package(GTestSrc)
endif()

IF(GTESTSRC_FOUND)
    enable_testing()

    if (WIN32 AND (NOT CYGWIN) AND (NOT MINGW))
        set(gtest_disable_pthreads ON)
        set(gtest_force_shared_crt ON)
    endif()

    add_subdirectory(${GTEST_SOURCE_DIR} ${CMAKE_BINARY_DIR}/googletest)
    include_directories(SYSTEM ${GTEST_INCLUDE_DIR})

    set(TEST_LIBRARIES gtest gtest_main)

    add_custom_target(tests ALL)
    add_subdirectory(perftest)
    add_subdirectory(unittest)

ENDIF(GTESTSRC_FOUND)
