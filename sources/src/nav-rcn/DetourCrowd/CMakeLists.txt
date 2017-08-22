# sources
aux_source_directory(Source DETOUR_CROWD_SRCS)

# includes
include_directories(Include)
include_directories(../Detour/Include)

# target
add_library(DetourCrowd ${DETOUR_CROWD_SRCS})