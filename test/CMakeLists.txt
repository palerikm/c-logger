set(tests
    logger_console_test
    logger_file_test
    logger_loglevel_test
    logger_multi_test
    loggerconf_test
)

include_directories(
    ${PROJECT_SOURCE_DIR}/src
    ${PROJECT_SOURCE_DIR}/test
)
#set(test_libraries
#    ${PROJECT_NAME}_static
#)

foreach(test IN LISTS tests)
    add_executable(${test} ${test}.c)
    target_link_libraries(${test} ${LIB_NAME})
    add_test(NAME ${test}
             COMMAND ${test}
             WORKING_DIRECTORY ${PROJECT_SOURCE_DIR}/test)
endforeach()
