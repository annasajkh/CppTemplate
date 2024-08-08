cmake_minimum_required(VERSION 3.10)
project(CppTemplate VERSION 1.0)

# Generate compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Collect source and header files
file(GLOB_RECURSE INCLUDES ${PROJECT_SOURCE_DIR}/src/*.h)
file(GLOB_RECURSE SOURCES ${PROJECT_SOURCE_DIR}/src/*.cpp)

# Create executable
add_executable(${PROJECT_NAME} ${SOURCES})

# Add include directories (derived from header file locations)
foreach(dir ${INCLUDES})
    get_filename_component(HEADER_DIR ${dir} DIRECTORY)
    list(APPEND INCLUDE_DIRS ${HEADER_DIR})
endforeach()

list(REMOVE_DUPLICATES INCLUDE_DIRS)
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDE_DIRS})