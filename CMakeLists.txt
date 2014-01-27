project(bootstrap-dht)
cmake_minimum_required(VERSION 2.8)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/Modules/")

set(BOOST_MAJOR_VERSION 1)
set(BOOST_MINOR_VERSION 53)
set(BOOST_PATCH_VERSION 0)

find_package(Boost ${BOOST_MAJOR_VERSION}.${BOOST_MINOR_VERSION}.${BOOST_PATCH_VERSION} COMPONENTS system REQUIRED)

include_directories(${Boost_INCLUDE_DIR})

aux_source_directory(. SRC_LIST)
add_definitions(-std=c++11)
add_executable(${PROJECT_NAME} ${SRC_LIST})

target_link_libraries(${PROJECT_NAME} ${Boost_LIBRARIES})