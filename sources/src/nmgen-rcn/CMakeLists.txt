cmake_minimum_required (VERSION 2.8)

project (nmgen-rcn)

# flag for -fPIC
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# lib Recast
add_subdirectory(Recast)

# includes
include_directories(Recast/Include)
include_directories(NMGen/Include)

# sources
aux_source_directory(NMGen/Include NMGEN_INCS)
aux_source_directory(NMGen/Source NMGEN_SRCS)

# target
add_library(nmgen-rcn SHARED ${NMGEN_SRCS})
# links
target_link_libraries(nmgen-rcn Recast)