cmake_minimum_required(VERSION 3.26)
project(smile_guy)

set(CMAKE_CXX_STANDARD 17)

add_executable(smile_guy main.cpp)

find_package(SDL2 CONFIG REQUIRED)
target_link_libraries(smile_guy
        PRIVATE
        $<TARGET_NAME_IF_EXISTS:SDL2::SDL2main>
        $<IF:$<TARGET_EXISTS:SDL2::SDL2>,SDL2::SDL2,SDL2::SDL2-static>
)




