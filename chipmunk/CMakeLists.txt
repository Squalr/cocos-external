cmake_minimum_required(VERSION 3.8 FATAL_ERROR)

if(NOT CHIPMUNK_LIBRARY)
    if(LINUX)
        set(CHIPMUNK_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/prebuilt/linux/64-bit/libchipmunk.a")
    if(WINDOWS)
        set(CHIPMUNK_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/prebuilt/win10/win32/chipmunk.lib")
    else()
        message(ERROR "Hey nathan fix this platform!")
    endif()
endif()

# Global is evil, don't do
if(NOT TARGET chipmunk::chipmunk)
    add_library(chipmunk::chipmunk UNKNOWN IMPORTED GLOBAL)
    set_target_properties(chipmunk::chipmunk PROPERTIES
        IMPORTED_LOCATION ${CHIPMUNK_LIBRARY}
        INTERFACE_INCLUDE_DIRECTORIES "${CMAKE_CURRENT_LIST_DIR}/include"
    )
endif()