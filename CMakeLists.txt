project(audiodecoder.gsf)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(kodi REQUIRED)

include(ExternalProject)

include_directories(${KODI_INCLUDE_DIR}
                    ${PROJECT_SOURCE_DIR}/lib/psflib
                    ${PROJECT_SOURCE_DIR}/lib/viogsf)

add_subdirectory(lib/psflib)
add_subdirectory(lib/viogsf)

set(GSF_SOURCES src/GSFCodec.cpp)

set(DEPLIBS viogsf psflib)

build_addon(audiodecoder.gsf GSF DEPLIBS)

include(CPack)
