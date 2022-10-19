cmake_minimum_required(VERSION 3.0)

project(imgui)

set(CMAKE_CXX_FLAGS "-O3")

find_package(SDL2 REQUIRED)
find_package(OpenGL REQUIRED)

# Linux
set(SRC
    src/imgui.cpp
    src/imgui_draw.cpp
    src/imgui_widgets.cpp
    src/imgui_tables.cpp
    src/imgui_demo.cpp
    src/backends/imgui_impl_opengl3.cpp
    src/backends/imgui_impl_sdl.cpp
#    src/backends/imgui_impl_sdlrenderer.cpp
)

# Windows
#set(SRC
    #src/imgui.cpp
    #src/imgui_draw.cpp
    #src/imgui_widgets.cpp
    #src/imgui_tables.cpp
    #src/imgui_demo.cpp
    #src/backends/imgui_impl_dx11.cpp
    #src/backends/imgui_impl_osx.mm
    #src/backends/imgui_impl_opengl3.cpp
    #src/backends/imgui_impl_win32.cpp
    #src/backends/imgui_impl_wgpu.cpp
    #src/backends/imgui_impl_allegro5.cpp
    #src/backends/imgui_impl_dx9.cpp
    #src/backends/imgui_impl_opengl2.cpp
    #src/backends/imgui_impl_sdl.cpp
    #src/backends/imgui_impl_sdlrenderer.cpp
    #src/backends/imgui_impl_glut.cpp
    #src/backends/imgui_impl_dx10.cpp
    #src/backends/imgui_impl_metal.mm
    #src/backends/imgui_impl_android.cpp
    #src/backends/imgui_impl_vulkan.cpp
    #src/backends/imgui_impl_dx12.cpp
    #src/backends/imgui_impl_glfw.cpp
#)
# Mac
#set(SRC
    #src/imgui.cpp
    #src/imgui_draw.cpp
    #src/imgui_widgets.cpp
    #src/imgui_tables.cpp
    #src/imgui_demo.cpp
    #src/backends/imgui_impl_dx11.cpp
    #src/backends/imgui_impl_osx.mm
    #src/backends/imgui_impl_opengl3.cpp
    #src/backends/imgui_impl_win32.cpp
    #src/backends/imgui_impl_wgpu.cpp
    #src/backends/imgui_impl_allegro5.cpp
    #src/backends/imgui_impl_dx9.cpp
    #src/backends/imgui_impl_opengl2.cpp
    #src/backends/imgui_impl_sdl.cpp
    #src/backends/imgui_impl_sdlrenderer.cpp
    #src/backends/imgui_impl_glut.cpp
    #src/backends/imgui_impl_dx10.cpp
    #src/backends/imgui_impl_metal.mm
    #src/backends/imgui_impl_android.cpp
    #src/backends/imgui_impl_vulkan.cpp
    #src/backends/imgui_impl_dx12.cpp
    #src/backends/imgui_impl_glfw.cpp
#)

add_library(imgui STATIC ${SRC})


target_include_directories(imgui PRIVATE ${SDL2_INCLUDE_DIRS} ${OPENGL_INCLUDE_DIR})
target_link_libraries(imgui glad SDL2::Main OpenGL::OpenGL ${CMAKE_DL_LIBS})


target_include_directories(imgui PUBLIC include)
