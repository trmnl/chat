CC=gcc
DBGFLAG=-ggdb 
CFLAGS=-std=c99 $(DBGFLAG) -Wall
LDLIBS=-lreadline -lncurses -lpthread 
LDFLAGS=$(DBGFLAG) 

SOURCES=client.c ../common/chat.c

OBJECTS=$(SOURCES:.c=.o)

TARGET=client


.PHONY : clean run erase

all: $(TARGET)

$(TARGET): $(OBJECTS)
	$(CC) -o $(TARGET) $(LDFLAGS) $(LDLIBS) $(OBJECTS)

%.o: %.c
	$(CC) -c -o $@ $< $(CFLAGS)

.depend: depend 


depend: $(SOURCES)
	ctags -R
	rm -f ./.depend
	$(CC) $(CFLAGS) -MM $^>>./.depend;
include .depend

erase:
	rm $(TARGET)
clean:
	rm $(OBJECTS)
