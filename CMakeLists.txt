cmake_minimum_required(VERSION 3.11.3)

set(CMAKE_CXX_STANDARD 17)

project(Membot)

if (CMAKE_HOST_WIN32)

  set(wxWidgets_ROOT_DIR "C:/msys64/mingw64/wxWidgets")

  set(wxWidgets_LIB_DIR "C:/msys64/mingw64/wxWidgets/lib/gcc_x64_lib")

endif()

find_package(wxWidgets COMPONENTS core base REQUIRED)
include(${wxWidgets_USE_FILE})

file(GLOB project_SRCS src/*.cpp)

add_executable(membot ${project_SRCS})
target_link_libraries(membot ${wxWidgets_LIBRARIES})
target_include_directories(membot PRIVATE ${wxWidgets_INCLUDE_DIRS})
