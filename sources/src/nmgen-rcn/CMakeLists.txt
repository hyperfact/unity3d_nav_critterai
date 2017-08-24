cmake_minimum_required (VERSION 2.8)

project (cai-nmgen-rcn)

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
add_library(cai-nmgen-rcn SHARED ${NMGEN_SRCS})
set_target_properties(cai-nmgen-rcn PROPERTIES PREFIX "")

# links
target_link_libraries(cai-nmgen-rcn Recast)