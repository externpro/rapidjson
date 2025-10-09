if(COMMAND xpFindPkg)
    xpFindPkg(PKGS googletest)
    enable_testing()
    get_target_property(GTEST_INCLUDE_DIR xpro::gtest INTERFACE_INCLUDE_DIRECTORIES)
    include_directories(SYSTEM ${GTEST_INCLUDE_DIR})
    set(TEST_LIBRARIES xpro::gtest xpro::gtest_main)
    if(FALSE) # doesn't build with googletest-v1.16.0.1
        add_custom_target(tests ALL)
        add_subdirectory(perftest)
        add_subdirectory(unittest)
    endif()
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
