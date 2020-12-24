cmake_minimum_required(VERSION 3.0)
project(meshquality)

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

add_library(meshquality-static STATIC ${SOURCE_LIST})

add_executable(meshquality ${SRC_DIR}/main.cpp)
target_link_libraries(meshquality
    PRIVATE
    meshquality-static
)
