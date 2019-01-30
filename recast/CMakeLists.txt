cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(recast VERSION 9999 LANGUAGES C CXX)

add_library(${PROJECT_NAME} STATIC
    DebugUtils/DebugDraw.cpp
    DebugUtils/DetourDebugDraw.cpp
    Detour/DetourAlloc.cpp
    Detour/DetourCommon.cpp
    Detour/DetourNavMesh.cpp
    Detour/DetourNavMeshBuilder.cpp
    Detour/DetourNavMeshQuery.cpp
    Detour/DetourNode.cpp
    DetourCrowd/DetourCrowd.cpp
    DetourCrowd/DetourLocalBoundary.cpp
    DetourCrowd/DetourObstacleAvoidance.cpp
    DetourCrowd/DetourPathCorridor.cpp
    DetourCrowd/DetourPathQueue.cpp
    DetourCrowd/DetourProximityGrid.cpp
    DetourTileCache/DetourTileCache.cpp
    DetourTileCache/DetourTileCacheBuilder.cpp
    fastlz/fastlz.c
)

add_library(${PROJECT_NAME}::${PROJECT_NAME} ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME} PUBLIC
    ${PROJECT_SOURCE_DIR}/../
)
