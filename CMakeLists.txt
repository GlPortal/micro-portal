# The newest available version
cmake_minimum_required(VERSION 3.28)
project(jumpers)
# The newest available standard
set(CMAKE_CXX_STANDARD 20)
# Warnings when if clause contains unset variable
cmake_policy(SET CMP0072 NEW)
# Vulkan
find_package(Vulkan REQUIRED)
# We want all our source code neatly in a subdirectory
set(SOURCE_DIR ${PROJECT_SOURCE_DIR}/source)
# We want to automatically add every new cpp file
file(GLOB_RECURSE SOURCE_FILES ${SOURCE_DIR}/*.cpp)

add_executable(jumpers ${SOURCE_FILES})

target_link_libraries(jumpers Vulkan::Vulkan)
