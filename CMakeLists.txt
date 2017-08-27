cmake_minimum_required( VERSION 3.2 )

project( nanovg
         LANGUAGES C CXX
)

set( CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14" )
set( CMAKE_CXX_STANDARD 14 )
set( CMAKE_CXX_STANDARD_REQUIRED ON )

set( VERSION_MAJOR "1" )
set( VERSION_MINOR "0" )
set( VERSION_PATCH "0" )
set( VERSION ${VERSION_MAJOR}.${VERSION_MINOR}.${VERSION_PATCH} )

add_subdirectory( nanovgLib )
add_subdirectory( example )
