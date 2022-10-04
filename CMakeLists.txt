cmake_minimum_required(VERSION 2.8.12)
project(yapb)

set(YAPB_LIB yapb)

file(GLOB_RECURSE YAPB_SRC "src/*.cpp")

include_directories("inc")
include_directories("ext")
include_directories("ext/crlib")

#add_definitions(-DLINUX -D_LINUX -DPOSIX -fms-extensions)

add_library(${YAPB_LIB} SHARED ${YAPB_SRC})

target_link_libraries(${YAPB_LIB} ws2_32)