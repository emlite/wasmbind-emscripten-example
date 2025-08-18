cmake_minimum_required(VERSION 3.20)
project(wasmbind-example)

add_subdirectory(wasmbind)

add_executable(main src/main.cpp)
target_link_libraries(main PRIVATE webbind::webbind)
set_target_properties(main PROPERTIES LINKER_LANGUAGE CXX SUFFIX .js LINK_FLAGS "-sSINGLE_FILE -sALLOW_MEMORY_GROWTH=1 -sEXPORTED_FUNCTIONS=_main -Wl,--strip-all,--export-dynamic")