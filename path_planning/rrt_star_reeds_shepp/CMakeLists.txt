cmake_minimum_required(VERSION 3.9)
project(rrt_star_reeds_shepp)

set(CMAKE_CXX_STANDARD 11)

if (EXISTS "FindOpenCV.cmake")
    message("find systerm opencv fail, use local.")
else (EXISTS "FindOpenCV.cmake")
    set(OpenCV_DIR /opt/ros/kinetic/share/OpenCV-3.3.1)
endif (EXISTS "FindOpenCV.cmake")

find_package(OpenCV REQUIRED)
find_package(PythonLibs 2.7)

include_directories(
        include
        ${OpenCV_INCLUDE_DIRS}
        ${PYTHON_INCLUDE_DIRS}
)

add_executable(rrt_star_reeds_shepp
        src/reeds_shepp_path_planning.cpp
        src/rrt_star_reeds_shepp.cpp
        test/main.cpp
        )

target_link_libraries(rrt_star_reeds_shepp
        ${OpenCV_LIBRARIES}
        ${PYTHON_LIBRARIES}
        )