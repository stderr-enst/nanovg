# Set the includes for the library

find_package( glfw3 )
find_package( OpenGL )

include_directories(
    ${OPENGL_INCLUDE_DIR}
    ${nanovgLib_SOURCE_DIR}/include
)

file( GLOB EXAMPLE_SRC
    src/example_fbo.c
    src/example_gl2.c
    src/example_gl3.c
    src/example_gles2.c
    src/example_gles3.c
)

foreach( example ${EXAMPLE_SRC} )
    string( REPLACE ".c" "" examplepath ${example} )
    get_filename_component( examplename ${examplepath} NAME )
    add_executable( ${examplename}
        ${example} src/perf.c src/demo.c
    )
    target_link_libraries( ${examplename}
        m
        nanovgLib
        glfw
        ${OPENGL_gl_LIBRARY}
    )
endforeach( example ${EXAMPLE_SRC} )

# copy fonts and images
file( COPY
    ${CMAKE_CURRENT_SOURCE_DIR}/images
    ${CMAKE_CURRENT_SOURCE_DIR}/fonts
    DESTINATION ${CMAKE_CURRENT_BINARY_DIR}
)
