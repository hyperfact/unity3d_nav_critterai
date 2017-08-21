cmake_minimum_required (VERSION 2.8)

project (nmgen-rcn)

add_subdirectory(Recast)

include_directories(Recast/Include)
include_directories(NMGen/Include)

aux_source_directory(NMGen/Include NMGEN_INCS)
aux_source_directory(NMGen/Source NMGEN_SRCS)

add_library(nmgen-rcn SHARED ${NMGEN_SRCS})
target_link_libraries(nmgen-rcn Recast)