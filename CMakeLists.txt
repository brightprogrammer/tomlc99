cmake_minimum_required(VERSION 3.25)
project(tomlc99 VERSION 1.0 LANGUAGES C)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)

include_directories(${PROJECT_SOURCE_DIR})
add_library(tomlc99 toml.c)

# Specify install rules
install(TARGETS tomlc99
    EXPORT tomlc99Targets
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(FILES toml.h DESTINATION include)

# Install the .pc file
install(FILES ${PROJECT_SOURCE_DIR}/libtoml.pc
    DESTINATION lib/pkgconfig/
)
