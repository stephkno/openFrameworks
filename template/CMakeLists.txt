
cmake_minimum_required(VERSION 3.13) # target_link_options

set(CMAKE_PROJECT_NAME template)
project(${CMAKE_PROJECT_NAME})
set(CMAKE_CXX_FLAGS "-std=c++20")

# setup openframeworks paths
set(OF_DIR "/path/to/openFrameworks")
set(OF_ADDON_DIR "${OF_DIR}/addons")
set(OF_LIBS_ROOT_DIR "${OF_DIR}/libs")
set(OF_SRC_DIR "${OF_DIR}/libs/openFrameworks/")

# add sources from template application
include_directories(src)

add_executable(${CMAKE_PROJECT_NAME} 
  ${CMAKE_CURRENT_SOURCE_DIR}/src/main.cpp 
  ${CMAKE_CURRENT_SOURCE_DIR}/src/ofApp.cpp 
)

# call into openframeworks cmakelists
include(${OF_DIR}/CMakeLists.txt)

# call into addons cmakelists
include(${OF_ADDON_DIR}/ofxImGui/CMakeLists.txt)
include(${OF_ADDON_DIR}/ofxAssimpModelLoader/CMakeLists.txt)

# link library to project
target_link_libraries(${CMAKE_PROJECT_NAME} openFrameworks)