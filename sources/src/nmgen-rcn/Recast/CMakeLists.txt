# sources
aux_source_directory(Source RECAST_SRCS)

# includes
include_directories(Include)

# target
add_library(Recast ${RECAST_SRCS})