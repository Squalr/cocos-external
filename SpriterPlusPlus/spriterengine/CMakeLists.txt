project(SPRITER_ENGINE)

file(GLOB_RECURSE SPRITER_ENGINE_SRC "*.cpp" "*.h")

add_library(spriterengine STATIC
  ${SPRITER_ENGINE_SRC}
)

add_library(spriterengine::spriterengine ALIAS spriterengine)

target_include_directories(spriterengine PUBLIC
    ${PROJECT_SOURCE_DIR}/../../
)

set_target_properties(spriterengine
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
)
