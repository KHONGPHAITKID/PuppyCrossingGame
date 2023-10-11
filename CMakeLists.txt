# Specify the minimum required CMake version
cmake_minimum_required(VERSION 3.5)

# Project configuration
project(my_raylib_game C)
set(CMAKE_C_STANDARD 99)

# Include Raylib via FetchContent
include(FetchContent)

# Set up Raylib options
set(FETCHCONTENT_QUIET FALSE)
set(BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(BUILD_GAMES OFF CACHE BOOL "" FORCE)

FetchContent_Declare(
    raylib
    GIT_REPOSITORY "https://github.com/raysan5/raylib.git"
    GIT_TAG "master"
    GIT_PROGRESS TRUE
)

FetchContent_MakeAvailable(raylib)

# Source files and include directories
file(GLOB_RECURSE PROJECT_SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_LIST_DIR}/sources/*.c")
set(PROJECT_INCLUDE "${CMAKE_CURRENT_LIST_DIR}/sources/")

# Declare the executable
add_executable(${PROJECT_NAME})
target_sources(${PROJECT_NAME} PRIVATE ${PROJECT_SOURCES})
target_include_directories(${PROJECT_NAME} PRIVATE ${PROJECT_INCLUDE})
target_link_libraries(${PROJECT_NAME} PRIVATE raylib)

# Define the asset path based on build type
if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    set(ASSETS_PATH "${CMAKE_CURRENT_SOURCE_DIR}/../assets/")
else()
    set(ASSETS_PATH "../assets/")
endif()

target_compile_definitions(${PROJECT_NAME} PUBLIC ASSETS_PATH="${ASSETS_PATH}")
