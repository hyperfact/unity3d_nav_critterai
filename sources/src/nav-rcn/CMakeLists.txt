cmake_minimum_required (VERSION 2.8)

project (cai-nav-rcn)

# for flag -fPIC
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# lib Detour
add_subdirectory(Detour)
# lib DetourCrowd
add_subdirectory(DetourCrowd)

# includes
include_directories(Detour/Include)
include_directories(DetourCrowd/Include)
include_directories(Nav/Include)

# sources
aux_source_directory(Nav/Include NAV_INCS)
aux_source_directory(Nav/Source NAV_SRCS)

# target

if (APPLE)
    if (IOS)
        # for iphone
        # set(CMAKE_OSX_ARCHITECTURES "$(ARCHS_STANDARD)")
        add_library(cai-nav-rcn STATIC ${NAV_SRCS})
        set(CMAKE_XCODE_ATTRIBUTE_IPHONEOS_DEPLOYMENT_TARGET "9.0")
    else (IOS)
        # for macOS
        # set(CMAKE_OSX_ARCHITECTURES "$(ARCHS_STANDARD_64_BIT)")
        add_library(cai-nav-rcn MODULE ${NAV_SRCS})
        set_target_properties (cai-nav-rcn PROPERTIES BUNDLE TRUE )
    endif(IOS)
else (APPLE)
    add_library(cai-nav-rcn SHARED ${NAV_SRCS})
endif(APPLE)

# set_target_properties(cai-nav-rcn PROPERTIES PREFIX "")

# links
target_link_libraries (cai-nav-rcn Detour)
target_link_libraries (cai-nav-rcn DetourCrowd)