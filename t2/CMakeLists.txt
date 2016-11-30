PROJECT(HELLO)
cmake_minimum_required(VERSION 2.8)
include_directories(${PROJECT_SOURCE_DIR}/include)
set(SOURCES
	src/hello.cpp)
add_library(hello SHARED ${SOURCES})
target_link_libraries(hello)

add_library(hello_static STATIC ${SOURCES})
SET_TARGET_PROPERTIES(hello_static PROPERTIES OUTPUT_NAME "hello")
target_link_libraries(hello)
