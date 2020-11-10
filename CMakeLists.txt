cmake_minimum_required(VERSION 3.0)

project(soul_at_the_seaside)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -g")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Ofast")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Werror")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

enable_testing()

IF (APPLE)
    set(CMAKE_EXE_LINKER_FLAGS "-framework Foundation -framework AVFoundation -framework CoreVideo -framework CoreMedia -w")
ENDIF()

add_subdirectory(libcam)

include_directories(libcam/include)

set(SOURCE_FILES src/main.cpp)
add_executable(soul_at_the_seaside ${SOURCE_FILES})
target_link_libraries(soul_at_the_seaside libcam)