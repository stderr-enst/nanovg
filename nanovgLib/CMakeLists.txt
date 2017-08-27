# Set the includes for the library

project(nanovgLib)

include_directories(
    include
)

set( LIB_HEADERS
    include/nanovg.h include/nanovg_gl.h include/nanovg_gl_utils.h
)
set( LIB_SOURCES
    src/nanovg.c
)

add_library( nanovgLib STATIC
    ${LIB_SOURCES} ${LIB_HEADERS}
)

set_target_properties( nanovgLib PROPERTIES
    VERSION ${VERSION}
    LINKER_LANGUAGE C
)

