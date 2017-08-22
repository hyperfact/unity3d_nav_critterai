# sources
aux_source_directory(Source DETOUR_SRCS)

# includes
include_directories(Include)

# target
add_library(Detour ${DETOUR_SRCS})
