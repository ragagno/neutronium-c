cmake_minimum_required(VERSION 3.22)

project(Neutronium VERSION 1.0.0 LANGUAGES C)

set(CMAKE_C_STANDARD 23)

set(EXTENSION_H h)
set(EXTENSION_C c)

if(MSVC)
    add_compile_options(/W4 /WX)
else()
    add_compile_options(-Wall -Wextra -Werror)
endif()

file(GLOB_RECURSE NEUTRONIUM_FILES "sources/*.${EXTENSION_C}")

add_executable(neutronium ${NEUTRONIUM_FILES})
target_include_directories(neutronium PUBLIC "include")
