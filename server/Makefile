SRCS  = src/main.cpp
SRCS += src/server.cpp
SRCS += src/client.cpp
SRCS += src/chess.cpp
SRCS += src/util.cpp

OBJS=$(SRCS:.cpp=.o)

CXX=clang++
CPPFLAGS =-w -Wall -std=c++11 -fpermissive
# CPPFLAGS +=-D DEBUG

all: $(OBJS)
	$(CXX) -o bin/main $(OBJS)  -lm $(CPPFLAGS)

util.o: src/util.h src/util.cpp

chess.o: src/chess.h src/chess.cpp

client.o: src/client.h src/client.cpp util.o

server.o: src/status.h src/server.h src/server.cpp client.o chess.o util.o

main.o: server.o

simple-client: 
	$(CXX) src/simple-client.cpp -o bin/simple-client $(CPPFLAGS)

clean:
	-rm -f $(OBJS)
	-rm -f bin/main bin/simple-client
