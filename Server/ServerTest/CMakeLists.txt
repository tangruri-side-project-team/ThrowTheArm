# CMakeList.txt : CMake project for ServerTest, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

link_directories(${LIBMYSQLCLIENT_LIBRARY_DIRS})

# Add source to this project's executable.
add_executable (main "main.cpp" "rest_handle.cpp")

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET main PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.

target_link_libraries(main PRIVATE cpprestsdk::cpprest)
target_include_directories(main PRIVATE ${LIBMYSQLCLIENT_INCLUDE_DIRS})
target_link_libraries(main PRIVATE ${LIBMYSQLCLIENT_LIBRARIES})
