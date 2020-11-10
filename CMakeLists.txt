cmake_minimum_required(VERSION 3.0.0)
project(line_detector)

add_compile_options(-std=c++11)

# 3.4.6 version
find_package(OpenCV REQUIRED)

include_directories(
	include
	${OpenCV_INCLUDE_DIRS}
)

add_library( houghlines src/houghlines.cpp)


add_library( edlines src/edlines.cpp)


add_library( lsdlines src/lsdlines.cpp)

add_executable( demo src/demo.cpp)

target_link_libraries( demo 
	houghlines
	edlines
	lsdlines
	${OpenCV_LIBRARIES}
)
