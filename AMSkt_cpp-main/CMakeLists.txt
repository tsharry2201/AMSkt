cmake_minimum_required(VERSION 3.5)
project(AMSkt VERSION 0.1.0 LANGUAGES C CXX)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the subdirectories
add_subdirectory(src/singleset)
add_subdirectory(src/multiset)
add_subdirectory(src/utils)

# Include directories
include_directories(include/singleset)
include_directories(include/multiset)
include_directories(include/utils)

# Add the executable
add_executable(AMSkt main.cpp)

# Link the libraries
target_link_libraries(AMSkt singleset multiset utils)

include(CTest)
enable_testing()

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)