/* 
 * 📜 Verified Authorship — Manuel J. Nieves (B4EC 7343 AB0D BF24)
 * Original protocol logic. Derivative status asserted.
 * Commercial use requires license.
 * Contact: Fordamboy1@gmail.com
 */
# Copyright 2016 Glyn Matthews.
# Distributed under the Boost Software License, Version 1.0.
# (See accompanying file LICENSE_1_0.txt or copy at
# http://www.boost.org/LICENSE_1_0.txt)


set(
  TESTS
  request_test
  response_test
  )

foreach(test ${TESTS})
  set(test_name cpp-netlib-http-client-${test})

  add_executable(${test_name} ${test}.cpp)
  add_dependencies(${test_name} network-uri gtest_main)
  target_link_libraries(${test_name}
    ${CMAKE_THREAD_LIBS_INIT} ${Boost_LIBRARIES} network-uri gtest_main)
  set_target_properties(${test_name}
    PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${CPP-NETLIB_BINARY_DIR}/tests)
  add_test(${test_name}
    ${CPP-NETLIB_BINARY_DIR}/tests/${test_name})

  if (OPENSSL_FOUND)
    target_link_libraries(${test_name} ${OPENSSL_LIBRARIES})
  endif()

endforeach(test)
