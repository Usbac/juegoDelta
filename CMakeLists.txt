# Define sources and executable
set(EXECUTABLE_NAME "Delta")
add_executable(${EXECUTABLE_NAME} main.cpp Bullet.cpp Bullet.h Entity.cpp Entity.h Player.cpp Player.h)

cmake_minimum_required(VERSION 2.6)
set(CMAKE_CXX_STANDARD 11)
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -g -std=gnu++0x")

# Detect and add SFML
set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules" ${CMAKE_MODULE_PATH})
find_package(SFML 2 REQUIRED system window graphics network audio)
if(SFML_FOUND)
    include_directories(${SFML_INCLUDE_DIR})
    target_link_libraries(${EXECUTABLE_NAME} ${SFML_LIBRARIES})
endif()

