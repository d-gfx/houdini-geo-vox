cmake_minimum_required( VERSION 3.6 )
project( HoudiniGeoVoxToPoints )

#list( APPEND CMAKE_PREFIX_PATH "$ENV{HFS}/toolkit/cmake" )
list( APPEND CMAKE_PREFIX_PATH "C:/Program Files/Side Effects Software/Houdini 17.5.173/toolkit/cmake" )
find_package( Houdini REQUIRED )

set( library_name GEO_VoxToPoints )
add_library(${library_name} SHARED
	GEO_VoxToPoints.C
	GEO_VoxToPoints.h
)

target_link_libraries( ${library_name} Houdini )

# Configure several common target properties, such as its output directory.
houdini_configure_target( ${library_name} )
