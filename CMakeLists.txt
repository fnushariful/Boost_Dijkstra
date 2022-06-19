cmake_minimum_required(VERSION 3.21)
project(CGAL_Dijkstra)

set(CMAKE_CXX_STANDARD 17)

include_directories(/opt/homebrew/include)
include_directories(/opt/homebrew/Cellar)
include_directories(/opt/homebrew/Cellar/boost/1.76.0/include/boost)

find_package(CGAL)
find_package(Qt6Core REQUIRED)
find_package(Qt6Widgets REQUIRED)
find_package(Qt6Quick REQUIRED)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "-O3 -fexceptions -stdlib=libc++ -Xpreprocessor -fopenmp -frounding-math -Wall -Wextra -Wno-unused")
set(CMAKE_BUILD_TYPE "Debug")


link_directories(/opt/homebrew/lib/)
link_directories(/opt/homebrew/Cellar/)
link_directories(/opt/homebrew/Cellar/boost/1.76.0/include/boost)

add_executable(CGAL_Dijkstra main.cpp)

target_link_libraries(CGAL_Dijkstra libgmp.a)
target_link_libraries(CGAL_Dijkstra libmpfr.a)
target_link_libraries(CGAL_Dijkstra libomp.a)
target_link_libraries(CGAL_Dijkstra Qt6::Core)
target_link_libraries(CGAL_Dijkstra Qt6::Widgets)
target_link_libraries(CGAL_Dijkstra CGAL)
