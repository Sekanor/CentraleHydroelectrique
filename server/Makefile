CC = g++
CFLAGS = -ansi \
		 -pedantic \
		 -g \
		 -std=c++11 \
		 -pthread \
		 -Wall \
		 -Werror \
		 

BIN = bin
SRC = src
INCLUDES = includes
EXE = server
OFILES = $(BIN)/main.o \
		 $(BIN)/Server.o \
		 $(BIN)/TCPServer.o \
		 $(BIN)/FileReader.o \
		 $(BIN)/HTTPServer.o \
		 $(BIN)/TCPModule.o \
		 $(BIN)/Catalog.o \
		 $(BIN)/DataModule.o \

all: $(EXE)

clean:
	rm -rf $(BIN)/* $(EXE)

$(EXE): $(OFILES)
	$(CC) $(CFLAGS) -o $(EXE) $(OFILES)

$(BIN)/Catalog.o: $(INCLUDES)/Catalog.h $(SRC)/Catalog.cpp $(INCLUDES)/TCPServer.h
	$(CC) $(CFLAGS) -o $(BIN)/Catalog.o -c $(SRC)/Catalog.cpp

$(BIN)/DataModule.o: $(INCLUDES)/DataModule.h $(SRC)/DataModule.cpp $(INCLUDES)/DataModule.h
	$(CC) $(CFLAGS) -o $(BIN)/DataModule.o -c $(SRC)/DataModule.cpp

$(BIN)/FileReader.o: $(INCLUDES)/FileReader.h $(SRC)/FileReader.cpp
	$(CC) $(CFLAGS) -o $(BIN)/FileReader.o -c $(SRC)/FileReader.cpp

$(BIN)/HTTPServer.o: $(INCLUDES)/HTTPServer.h $(SRC)/HTTPServer.cpp $(INCLUDES)/Server.h $(INCLUDES)/FileReader.h $(INCLUDES)/Catalog.h \
				     $(INCLUDES)/TCPModule.h $(INCLUDES)/DataModule.h
	$(CC) $(CFLAGS) -o $(BIN)/HTTPServer.o -c $(SRC)/HTTPServer.cpp

$(BIN)/main.o: $(SRC)/main.cpp $(INCLUDES)/HTTPServer.h $(INCLUDES)/TCPServer.h
	$(CC) $(CFLAGS) -o $(BIN)/main.o -c $(SRC)/main.cpp

$(BIN)/TCPServer.o: $(INCLUDES)/TCPServer.h $(SRC)/TCPServer.cpp $(INCLUDES)/Server.h
	$(CC) $(CFLAGS) -o $(BIN)/TCPServer.o -c $(SRC)/TCPServer.cpp

$(BIN)/Server.o: $(INCLUDES)/Server.h $(SRC)/Server.cpp
	$(CC) $(CFLAGS) -o $(BIN)/Server.o -c $(SRC)/Server.cpp

$(BIN)/TCPModule.o: $(INCLUDES)/TCPModule.h $(SRC)/TCPModule.cpp
	$(CC) $(CFLAGS) -o $(BIN)/TCPModule.o -c $(SRC)/TCPModule.cpp
