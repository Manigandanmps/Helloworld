cmake_minimum_required(VERSION 3.0)
project(helloworld)

set(SRC_DIR code/src)
set(HDR_DIR code/include)

set(
    DIRS
    ${SRC_DIR}
    ${HDR_DIR}
)

include_directories(${DIRS})

set(
    SRCS
    ${SRC_DIR}/test.cpp
)

set(
    HDRS
    ${HDR_DIR}/test.hpp
)

set(
    SOURCE_LIST
    ${SRCS}
    ${HDRS}
)

add_library(helloworld-static STATIC ${SOURCE_LIST})

add_executable(helloworld ${SRC_DIR}/main.cpp)
target_link_libraries(helloworld
    PRIVATE
    helloworld-static
)
