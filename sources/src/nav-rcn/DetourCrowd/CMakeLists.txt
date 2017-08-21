aux_source_directory(Source DETOUR_CROWD_SRCS)

include_directories(Include)
include_directories(../Detour/Include)

add_library(DetourCrowd ${DETOUR_CROWD_SRCS})