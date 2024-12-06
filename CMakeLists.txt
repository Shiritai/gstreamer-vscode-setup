cmake_minimum_required(VERSION 3.10)
project(MyGStreamerPlugin)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GST REQUIRED gstreamer-1.0)

# If is to produce executable
add_executable(hello hello.cpp)
# If is to produce library
# add_library(hello SHARED hello.cpp)
target_include_directories(hello PRIVATE ${GST_INCLUDE_DIRS})
target_link_libraries(hello PRIVATE ${GST_LIBRARIES})
target_compile_options(hello PRIVATE ${GST_CFLAGS_OTHER})