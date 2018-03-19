cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(cmake_install)
message("Nome progetto : ${PROJECT_NAME}")


###############################################
#Creazione libreria Dynamica
###############################################

#genero la lib dinamica dal codice sorgente desiderato
add_library(${PROJECT_NAME} SHARED
	src/hello.cpp
)

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
add_executable(cmake_install_bin ${SOURCES})

#includo la cartella che verra anche visualizzata nel progetto
message("project_source_dir : ${PROJECT_SOURCE_DIR}")
target_include_directories(cmake_install_bin
	PRIVATE
		${PROJECT_NAME}}
)

###############################################
#Installazione 
###############################################

#installazione file binario
install(TARGETS cmake_install_bin
	DESTINATION bin
)

#installazione librerie
install(TARGETS ${PROJECT_NAME}
	LIBRARY DESTINATION lib
)

#installazione headers
install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/
	DESTIONATION include
)

#configurazioni
install(FILES test.conf
	DESTIONATION etc
)
