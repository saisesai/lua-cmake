cmake_minimum_required(VERSION 3.0)

project(lua)

set(CMAKE_C_STANDARD 11)
set(CMAKE_WINDOWS_EXPORT_ALL_SYMBOLS ON)

include_directories(include)

set(
        LUA_SRC
        src/lapi.c
        src/lcode.c
        src/lctype.c
        src/ldebug.c
        src/ldo.c
        src/ldump.c
        src/lfunc.c
        src/lgc.c
        src/llex.c
        src/lmem.c
        src/lobject.c
        src/lopcodes.c
        src/lparser.c
        src/lstate.c
        src/lstring.c
        src/ltable.c
        src/ltm.c
        src/lundump.c
        src/lvm.c
        src/lzio.c
        src/lauxlib.c
        src/lbaselib.c
        src/lcorolib.c
        src/ldblib.c
        src/liolib.c
        src/lmathlib.c
        src/loadlib.c
        src/loslib.c
        src/loslib.c
        src/lstrlib.c
        src/ltablib.c
        src/lutf8lib.c
        src/linit.c
)

add_library(
        lua54 SHARED
        ${LUA_SRC}
)

add_library(
        lua54a STATIC
        ${LUA_SRC}
)

add_executable(lua src/lua.c)
target_link_libraries(lua lua54a)

add_executable(luac src/luac.c)
target_link_libraries(luac lua54a)
