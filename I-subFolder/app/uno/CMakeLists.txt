project(uno)
message("Progetto: ${PROJECT_NAME}")

add_executable(${PROJECT_NAME} main.cpp)

#link della lib static da progetto due
#link solo degli headers dal progetto tre
target_link_libraries(${PROJECT_NAME}
	sub::lib1
	sub::lib2
)