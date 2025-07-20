cmake_minimum_required(VERSION 3.20)

set(PROJECT_NAME cpp_template_workspace)
project(${PROJECT_NAME} VERSION 1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(cpp_template)
