cmake_minimum_required (VERSION 3.8)


set(PROJECT_NAME CppTemplate)
project(${PROJECT_NAME} VERSION 1.0)


# Add source to this project's executable.
add_executable (${PROJECT_NAME} "src/main.cpp" )

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
