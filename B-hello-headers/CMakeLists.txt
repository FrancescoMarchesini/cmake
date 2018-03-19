cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(hello_headers)
message("Nome progetto : ${PROJECT_NAME}")

#aggiungo i sorgenti al progetto
set(SOURCES
	src/main.cpp
	src/Hello.cpp
)
message("aggiunto i seguenti sorgenti : ${SOURCES}")

#aggiungo l'eseguibile
add_executable(${PROJECT_NAME} ${SOURCES})

#includo la cartella che verra anche visualizzata nel progetto
message("project_source_dir : ${PROJECT_SOURCE_DIR}")
target_include_directories(${PROJECT_NAME}
	PRIVATE
		${PROJECT_SOURCE_DIR}/include
)
