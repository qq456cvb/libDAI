cmake_minimum_required(VERSION 3.13)

project(dai)

set(CMAKE_CXX_STANDARD 17)

file(GLOB SRC_FILES
    ${PROJECT_SOURCE_DIR}/src/*.cpp
)

find_package(Boost REQUIRED)

include_directories(${PROJECT_SOURCE_DIR}/include ${Boost_INCLUDE_DIRS})
add_library(dai
    STATIC
    ${SRC_FILES}
)

target_link_libraries(dai ${Boost_LIBRARIES})