#========================================================================
# IMGUI
#========================================================================
cmake_minimum_required(VERSION 3.27)

project(IMGUI VERSION 1.0 LANGUAGES C CXX)

add_library(IMGUI STATIC)

target_sources(IMGUI PRIVATE
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_demo.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_draw.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_tables.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui_widgets.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/imgui.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_opengl3.cpp"
    "${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_glfw.cpp"
)

target_link_libraries(IMGUI PUBLIC compiler_flags)

target_include_directories(IMGUI PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}" "${CMAKE_CURRENT_SOURCE_DIR}/backends")

