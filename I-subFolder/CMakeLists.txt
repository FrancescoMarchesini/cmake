cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(subProjects)
message("Nome progetto : ${PROJECT_NAME}")

#aggiungo le sotto cartelle
add_subdirectory(app/uno)
add_subdirectory(app/due)
add_subdirectory(app/tre)