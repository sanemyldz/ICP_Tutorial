cmake_minimum_required(VERSION 3.0.0)
project(pcl_interactive_icp VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(pcl_interactive_icp interactive_icp.cpp)

# PCL
find_package(PCL 1.3 REQUIRED)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
target_link_libraries(pcl_interactive_icp ${PCL_LIBRARIES})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)