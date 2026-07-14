# Run cmake to create some makefiles?
cmake_minimum_required(VERSION 3.23)
project(omorfi-cpp VERSION 0.0.0)
add_executable(omorfi-lookup)
add_library(omorfi SHARED
    src/omorfi.cc
)
target_sources(omorfi-lookup
    PRIVATE
       src/omorfi-lookup.cc
)
target_sources(omorfi
    PRIVATE
        src/omorfi.cc
    PUBLIC
        src/omorfi.hh
)
target_link_libraries(omorfi hfst)
target_link_libraries(omorfi-lookup omorfi)
