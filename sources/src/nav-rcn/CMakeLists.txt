cmake_minimum_required (VERSION 2.8)

project (nav-rcn)

add_subdirectory(Detour)
add_subdirectory(DetourCrowd)

include_directories(Detour/Include)
include_directories(DetourCrowd/Include)
include_directories(Nav/Include)

aux_source_directory(Nav/Include NAV_INCS)
aux_source_directory(Nav/Source NAV_SRCS)

add_library(nav-rcn SHARED ${NAV_SRCS})
target_link_libraries (nav-rcn Detour)
target_link_libraries (nav-rcn DetourCrowd)