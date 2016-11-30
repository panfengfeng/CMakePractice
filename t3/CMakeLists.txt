PROJECT(hello)
cmake_minimum_required(VERSION 3.5)
include_directories(${PROJECT_SOURCE_DIR}/include)

# Main library source code

set(SOURCES 
        src/hello.cpp)
add_library(hellolib${ARTIFACT_SUFFIX} STATIC ${SOURCES})
target_link_libraries(hellolib${ARTIFACT_SUFFIX})

add_library(hello${ARTIFACT_SUFFIX} SHARED ${SOURCES})
target_link_libraries(hello${ARTIFACT_SUFFIX})

# Test

set(BENCHMARK
        benchmark/bench.cpp)
add_executable(bench ${BENCHMARK})
