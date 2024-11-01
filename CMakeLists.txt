cmake_minimum_required(VERSION 3.22)


set(CMAKE_TOOLCHAIN_FILE "${VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake" CACHE STRING "")

set(CMAKE_C_COMPILER "gcc")
set(CMAKE_CXX_COMPILER "g++")

set(PROJECT_NAME CppTemplate)
project(${PROJECT_NAME} VERSION 1.0)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

file(GLOB_RECURSE SRCS "${PROJECT_SOURCE_DIR}/src/*.cpp")
message("Source files found: ${SRCS}")

MACRO(header_directories return_list includes_base_folder extension)
    FILE(GLOB_RECURSE new_list ${includes_base_folder}/*.${extension})
    SET(dir_list)
    FOREACH(file_path ${new_list})
        GET_FILENAME_COMPONENT(dir_path ${file_path} PATH)
        SET(dir_list ${dir_list} ${dir_path})
    ENDFOREACH()
    LIST(REMOVE_DUPLICATES dir_list)
    SET(${return_list} ${dir_list})
ENDMACRO()

header_directories(INCLUDES "${PROJECT_SOURCE_DIR}/include" hpp)
message("Include directories: ${INCLUDES}")

add_executable(${PROJECT_NAME} ${SRCS})
target_include_directories(${PROJECT_NAME} PRIVATE ${INCLUDES})