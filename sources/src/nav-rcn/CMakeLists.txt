cmake_minimum_required (VERSION 2.8)

project (nav-rcn)

# for flag -fPIC
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# lib Detour
add_subdirectory(Detour)
# lib DetourCrowd
add_subdirectory(DetourCrowd)

# includes
include_directories(Detour/Include)
include_directories(DetourCrowd/Include)
include_directories(Nav/Include)

# sources
aux_source_directory(Nav/Include NAV_INCS)
aux_source_directory(Nav/Source NAV_SRCS)

# target
add_library(nav-rcn SHARED ${NAV_SRCS})
# links
target_link_libraries (nav-rcn Detour)
target_link_libraries (nav-rcn DetourCrowd)