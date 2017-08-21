aux_source_directory(Source RECAST_SRCS)

include_directories(Include)

add_library(Recast ${RECAST_SRCS})