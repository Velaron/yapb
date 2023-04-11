cmake_minimum_required(VERSION 3.1)
project(yapb CXX)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(YAPB_LIB yapb)

file(GLOB_RECURSE YAPB_SRC "src/*.cpp")

include_directories("inc")
include_directories("ext")
include_directories("ext/crlib")

if(NOT WIN32)
   add_compile_options(-mtune=generic -fno-threadsafe-statics)
endif()
#add_definitions(-DLINUX -D_LINUX -DPOSIX -fms-extensions)

add_library(${YAPB_LIB} SHARED ${YAPB_SRC})

if(WIN32)
   target_link_libraries(${YAPB_LIB} ws2_32)
else()
   target_link_libraries(${YAPB_LIB} dl)
endif()
