function(create_test test_name)
    add_executable(${test_name} ${test_name}.cpp)
    target_link_libraries(${test_name} PRIVATE floatx gtest_main)
    file(RELATIVE_PATH REL_BINARY_DIR
         ${PROJECT_BINARY_DIR} ${CMAKE_CURRENT_BINARY_DIR})
    add_test(NAME ${REL_BINARY_DIR}/${test_name} COMMAND ${test_name})
endfunction(create_test)

create_test(add_000)
create_test(sub_000)
create_test(mul_000)
create_test(div_000)
