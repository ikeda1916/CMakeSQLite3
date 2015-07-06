cmake_minimum_required(VERSION 2.8)
project(sqlite3)

find_package(Threads)

add_library(sqlite3 SHARED sqlite3.c)

target_link_libraries(sqlite3 ${CMAKE_THREAD_LIBS_INIT})

if(NOT WIN32)
  target_link_libraries(sqlite3 ${CMAKE_DL_LIBS})
endif()
