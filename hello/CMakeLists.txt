#versione minima di cmake
cmake_minimum_required(VERSION 2.8)

#nome del progetto
project(hello)

#settare la directory di output e crearla
#varibili globali del cmake

#CMAKE_BINARY_DIR : cartella root dell'albero del progetto, puo cooincidere
#con CMAKE_SOURCE_DIR ovvero dove si trova il file cmake
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)

#EXECUTABLE_OUTPUT_PATH: la dir dove cmake metterà i file di output
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})

#LIBRARY_OUTPUT_PATH: dove verranno messe le librerie
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

#includi all'interno del progetto la cartella corrente ovvero il path
include_directories("${PROJECT_SOURCE_DIR}")

#creo l'esecutibile
add_executable(hello ${PROJECT_SOURCE_DIR}/main.cpp)
