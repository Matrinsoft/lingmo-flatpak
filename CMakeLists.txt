cmake_minimum_required(VERSION 3.20)

project(lingmo-flatpak VERSION 1.0.0 DESCRIPTION "Lingmo Flatpak" LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt6 REQUIRED COMPONENTS Core DBus)

add_library(lingmo-flatpak SHARED
    src/main.cpp
)
target_compile_definitions(lingmo-flatpak PRIVATE LINGMO_FLATPAK_LIBRARY)

target_link_libraries(lingmo-flatpak PUBLIC
    Qt6::Core
    Qt6::DBus
)

install(TARGETS lingmo-flatpak
    EXPORT lingmo-flatpakTargets
    LIBRARY DESTINATION 
    ARCHIVE DESTINATION 
)

install(DIRECTORY include/lingmo-flatpak
    DESTINATION 
)
