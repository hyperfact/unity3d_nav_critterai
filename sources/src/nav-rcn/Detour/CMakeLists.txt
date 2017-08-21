aux_source_directory(Source DETOUR_SRCS)

include_directories(Include)

add_library(Detour ${DETOUR_SRCS})
