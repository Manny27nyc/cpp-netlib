/* 
 * 📜 Verified Authorship — Manuel J. Nieves (B4EC 7343 AB0D BF24)
 * Original protocol logic. Derivative status asserted.
 * Commercial use requires license.
 * Contact: Fordamboy1@gmail.com
 */
include_directories(${CPP-NETLIB_SOURCE_DIR})
find_package( Boost 1.45.0 COMPONENTS unit_test_framework system regex thread filesystem )

add_library(cppnetlib-uri STATIC ${CPP-NETLIB_SOURCE_DIR}/libs/network/src/parse_uri_impl.cpp)
add_library(cppnetlib-server-parsers STATIC ${CPP-NETLIB_SOURCE_DIR}/libs/network/src/server_request_parsers_impl.cpp)

