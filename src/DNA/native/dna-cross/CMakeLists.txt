project(dna-cross)
cmake_minimum_required (VERSION 2.8)

set (CMAKE_C_COMPILER clang)
set (CMAKE_CXX_COMPILER clang)
set (CMAKE_INSTALL_PREFIX ${CMAKE_CURRENT_SOURCE_DIR}/../../Blazor.Host/wwwroot/_framework)
set (CMAKE_C_FLAGS "-Wno-pointer-sign")
set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -Oz")
set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -s NO_EXIT_RUNTIME=1")
set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -s RESERVED_FUNCTION_POINTERS=20")
set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -s ASSERTIONS=1")
set (CMAKE_C_FLAGS "${CMAKE_CXX_FLAGS} -D_DEBUG -DDEBUG_PRINT")

file(GLOB SOURCES ../src/*.c)

add_executable(${PROJECT_NAME} ${SOURCES})
target_link_libraries(${PROJECT_NAME} m dl)
