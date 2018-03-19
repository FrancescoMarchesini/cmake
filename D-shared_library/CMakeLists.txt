cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(hello_dynamic_libs)
message("Nome progetto : ${PROJECT_NAME}")


###############################################
#Creazione libreria Statica
###############################################

#genero la lib dinamica dal codice sorgente desiderato
add_library(${PROJECT_NAME} SHARED
	src/hello.cpp
)

#creazione di un nome fittizio read only per praticitò di utilizzo
add_library(hello::library ALIAS  ${PROJECT_NAME})

#PUBLIC: include la librarie per il target specifcato e qualsiasi link della lib 
target_include_directories(${PROJECT_NAME}
	PUBLIC
		${PROJECT_SOURCE_DIR}/include}
)

###############################################
#Creazione Eseguibile
###############################################

#aggiungo i sorgenti al progetto
set(SOURCES
	src/main.cpp
)
message("aggiunto i seguenti sorgenti : ${SOURCES} ")

#aggiungo l'eseguibile
add_executable(hello_binary_dynamic ${SOURCES})

#includo la cartella che verra anche visualizzata nel progetto
message("project_source_dir : ${PROJECT_SOURCE_DIR}")
target_include_directories(hello_binary_dynamic
	PRIVATE
		hello:library}
)
