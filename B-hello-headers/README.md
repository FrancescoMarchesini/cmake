Inclusione degli Headers 

Divisione del progetto con cartella file sorgenti e headers

Varibili Cmake posso essere classificate sotto due tipologie

_SOURCE_DIR Varibili e _BINARY_DIR_ Variabili

SOURCE_DIR Varibili:
Queste Variabili contengono i path per il i vari codici sorgenti del programma.Come si nota ognuna
di questi varibili punta ad una directory che contiene un file CMakeLists.txt

CMAKE_SOURCE_DIR: 	cartella root del progetto ovverro dove risede il Top-level CMAKELIsts
CMAKE_CURRENT_SOURCE_DIR: in caso di abbiano piu cmake top level questa varibile determina quello corrente
PROJECT_SOURCE_DIR: Nel caso in cui il CMakeLists tp-level non coincide con la cartella root del progetto
projectName_SOURCE_DIR: settato il nome del progetto all'interno del file cmake è possibile tramite il nome stesso
ottenere il path assoluto alla cartella

_BINARY_DIR_ Variabili
Queste varibili rappresentano la gerarchia della cartelle sorgente nella fase di building
e quindi

CMAKE_BINARY_DIR: cartella sorgente dal quale verra lancioto il comando cmake e verra genereato l'aberro corrispondente
CMAKE_CURRENT_BINARY_DIR
PROJECT_BINARY_DIR
projectName_BINARY_DIR