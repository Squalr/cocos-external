cmake_minimum_required(VERSION 3.8 FATAL_ERROR)
project(xxtea VERSION 9999 LANGUAGES CXX)

add_library(xxtea STATIC xxtea.cpp)
add_library(xxtea::xxtea ALIAS xxtea)

target_include_directories(xxtea PUBLIC ${PROJECT_SOURCE_DIR})
