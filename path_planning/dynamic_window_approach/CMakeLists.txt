cmake_minimum_required(VERSION 3.9)
project(dynamic_window_approach)

set(CMAKE_CXX_STANDARD 11)

set(OpenCV_DIR /opt/ros/kinetic/share/OpenCV-3.3.1)
find_package(OpenCV REQUIRED)
find_package(PythonLibs 2.7)

include_directories(
        include
        ${OpenCV_INCLUDE_DIRS}
        ${PYTHON_INCLUDE_DIRS}
)

add_executable(dynamic_window_approach
        src/dynamic_window_approach.cpp
        test/main.cpp
)
#target_include_directories(dynamic_window_approach PRIVATE ${PYTHON_INCLUDE_DIRS})
target_link_libraries(dynamic_window_approach
        ${OpenCV_LIBRARIES}
        ${PYTHON_LIBRARIES}
)