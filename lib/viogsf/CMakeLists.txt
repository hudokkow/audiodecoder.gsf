project(viogsf)

enable_language(CXX)

cmake_minimum_required(VERSION 2.6)

set(SOURCES vbam/apu/Multi_Buffer.cpp
            vbam/apu/Gb_Oscs.cpp
            vbam/apu/Effects_Buffer.cpp
            vbam/apu/Gb_Apu.cpp
            vbam/apu/Blip_Buffer.cpp
            vbam/gba/bios.cpp
            vbam/gba/GBA.cpp
            vbam/gba/GBA-thumb.cpp
            vbam/gba/GBA-arm.cpp
            vbam/gba/Sound.cpp)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fPIC")

add_library(viogsf STATIC ${SOURCES})
