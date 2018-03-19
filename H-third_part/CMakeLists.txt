cmake_minimum_required(VERSION 3.0)
message("Utilizzo CMAKE versione : ${CMAKE_VERSION}")

#aggiunta nome progettto tramite il quale accedere a varie funnzioni
project(thrid_part)
message("Nome progetto : ${PROJECT_NAME}")

#importo la libreria
find_package(Boost 1.46.1 REQUIRED COMPONENTS filesystem system)

#check is boost è installato
if(Boost_FOUND)
	message("Boost trovato")
else()
	message(FATAL_ERROR "non trovo boost")
endif()

message("header boost ${boost_INCLUDE_DIRS}")
message("system lib   ${boost_SYSTEM_LBRARY}")
message("filesystem   ${boost_FILESYSTEM_LIBRARY}")

#aggiungo l'eseguibile
add_executable(${PROJECT_NAME} main.cpp)

#aggiungo al target le librerie necessarie
target_link_libraries(${PROJECT_NAME}
	PRIVATE:
		Boost::filesystem
)