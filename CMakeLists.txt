cmake_minimum_required(VERSION 3.20)
project(wasmbind-example)

include(FetchContent)

FetchContent_Declare(
    wasmbind
    GIT_REPOSITORY https://github.com/emlite/wasmbind.git
    GIT_TAG main
    GIT_SHALLOW True
)

FetchContent_MakeAvailable(wasmbind)

add_executable(main src/main.cpp)
target_link_libraries(main PRIVATE webbind::webbind)
set_target_properties(main PROPERTIES LINKER_LANGUAGE CXX SUFFIX .js LINK_FLAGS "-sSINGLE_FILE -sALLOW_MEMORY_GROWTH=1 -sEXPORTED_RUNTIME_METHODS=wasmTable,UTF8ToString,lengthBytesUTF8,stringToUTF8 -sEXPORTED_FUNCTIONS=_malloc,_main -Wl,--strip-all")