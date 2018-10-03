project(RAPIDJSON)

file(GLOB_RECURSE RAPIDJSON_SRC "*.cpp" "*.h")

add_library(rapidjson STATIC
  ${RAPIDJSON_SRC}
)

target_include_directories(rapidjson PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}/../>
  $<BUILD_INTERFACE:${CMAKE_CURRENT_LIST_DIR}>
)

set_target_properties(rapidjson
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)
