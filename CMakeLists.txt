cmake_minimum_required(VERSION 3.5)

project(updog)
include_directories(include)

find_package(Curses REQUIRED)
include_directories(${CURSES_INCLUDE_DIR})

add_executable(updog src/utils.c  src/client.c src/main.c src/server.c)

target_include_directories(updog PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(updog PUBLIC pthread ${CURSES_LIBRARY})
