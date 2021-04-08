cmake_minimum_required(VERSION 2.8.12)
project(yapb)

set(YAPB_LIB yapb)

file(GLOB_RECURSE YAPB_SRC "source/*.cpp")

include_directories("include")
include_directories("include/engine")

add_definitions(-DLINUX -D_LINUX -DPOSIX -fms-extensions)

add_library(${YAPB_LIB} SHARED ${YAPB_SRC})