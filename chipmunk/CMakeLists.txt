cmake_minimum_required(VERSION 3.8 FATAL_ERROR)

if(NOT CHIPMUNK_LIBRARY)
    if(APPLE)
        set(CHIPMUNK_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/prebuilt/mac/libchipmunk.a")
    elseif(WINDOWS)
        set(CHIPMUNK_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/prebuilt/win10/win32/chipmunk.lib")
    elseif(UNIX)
        set(CHIPMUNK_LIBRARY "${CMAKE_CURRENT_LIST_DIR}/prebuilt/linux/64-bit/libchipmunk.a")
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