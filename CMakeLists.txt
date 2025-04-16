cmake_minimum_required(VERSION 3.19)
set(CMAKE_EXPORT_COMPILER_COMMANDS TRUE)

project("sdb" LANGUAGES CXX)

find_package(PkgConfig REQUIRED)
pkg_check_modules(libedit REQUIRED IMPORTED_TARGET libedit)

include(CTest)

add_subdirectory("src")
add_subdirectory("tools")

if(BUILD_TESTING)
  find_package(Catch2 CONFIG REQUIRED)
  add_subdirectory("test")
endif()
