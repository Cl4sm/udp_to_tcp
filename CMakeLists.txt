cmake_minimum_required (VERSION 2.6)
project (udp_to_tcp)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# Socket
add_library(udp_to_tcp SHARED src/udp_to_tcp.c)
target_link_libraries(udp_to_tcp dl pthread)

# Tests
add_executable(test_udp_server test/udp_server.c)
add_executable(test_udp_client test/udp_client.c)



