HEADERS=fsupport.h main.h shuffle.h
OBJECTS=fsupport.o main.o shuffle.o
CC=gcc
CFLAGS=-ansi -Wall -pedantic
LFLAGS=

#default target
all:shuffle

#target that links together into a binary executable
shuffle: $(OBJECTS)
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

#delete all files created as part of compilation
.PHONY:clean
clean:
	rm -f shuffle *.o *~
