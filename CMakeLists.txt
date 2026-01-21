cmake_minimum_required(VERSION 3.16)
project(bezier-curve-visualizer C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

find_package(raylib QUIET)

add_executable(${PROJECT_NAME} src/main.c)

if(raylib_FOUND)
    target_link_libraries(${PROJECT_NAME} PRIVATE raylib)
else()
    include(FetchContent)

    FetchContent_Declare(
        raylib
        GIT_REPOSITORY https://github.com/raysan5/raylib.git
        GIT_TAG 5.5
        GIT_SHALLOW TRUE
    )
    FetchContent_MakeAvailable(raylib)

    FetchContent_Declare(
        raygui
        GIT_REPOSITORY https://github.com/raysan5/raygui.git
        GIT_TAG 4.0
        GIT_SHALLOW TRUE
    )
    FetchContent_MakeAvailable(raygui)
    target_link_libraries(${PROJECT_NAME} PRIVATE raylib)
endif()

install(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)
