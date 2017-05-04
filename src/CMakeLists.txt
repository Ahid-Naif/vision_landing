cmake_minimum_required (VERSION 3.2)
project (track_targets)
add_executable(track_targets track_targets.cpp)

set(cpp_compile_flags "-std=gnu++11")
add_definitions(${cpp_compile_flags})

find_package(OpenCV REQUIRED)

find_package(aruco REQUIRED)

find_package(realsense REQUIRED)

include_directories(${aruco_INCLUDE_DIRS} ${OpenCV_INCLUDE_DIRS} ${realsense_INCLUDE_DIR})
target_link_libraries(track_targets ${aruco_LIBS} ${OpenCV_LIBS} ${realsense_LIBRARY})

install(PROGRAMS track_targets DESTINATION ${CMAKE_CURRENT_SOURCE_DIR}/..)
