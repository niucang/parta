HEADERS=fsupport.h main.h alternate.h
OBJECTS=fsupport.o main.o alternate.o
CC=gcc
CFLAGS=-ansi -Wall -pedantic
LFLAGS=

#default compilation target
all:alternate

#link together the main executable
alternate: $(OBJECTS)
	$(CC) $(LFLAGS) $^ -o $@

#compile each source file
%.o:%.c $(HEADERS)
	$(CC) $(CFLAGS) -c $<

#compilation target for debugging: 
debug:CFLAGS+=-g
debug: clean all

#compilation target for address sanitisation: 
sanitize:CFLAGS+=-g -fsanitize=address
sanitize:LFLAGS+=-fsanitize=address
sanitize: clean all

.PHONY:clean
clean:
	rm -f alternate *.o *~
