# CMakeList.txt : Top-level CMake project file, do global configuration
# and include sub-projects here.
#
cmake_minimum_required (VERSION 3.9)

project ("ServerTest")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -std=c17")

include(FindPkgConfig)
pkg_check_modules(LIBMYSQLCLIENT REQUIRED mysqlclient)

find_package(cpprestsdk REQUIRED)
find_package(PkgConfig)

# Include sub-projects.
add_subdirectory ("ServerTest")
