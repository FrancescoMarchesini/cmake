cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(hello_cmake)
message("Nome progetto : ${PROJECT_NAME}")

#aggiungo l'eseguibile
add_executable(${PROJECT_NAME} main.cpp)