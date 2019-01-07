HEADERS=fsupport.h main.h reverse.h
OBJECTS=fsupport.o main.o reverse.o
CC=gcc
CFLAGS=-ansi -Wall -pedantic
LFLAGS=
#by default, build the reverse application
all:reverse

#link together the binary .o files with system code to create the executable
reverse: $(OBJECTS)
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
	rm -f reverse *.o *~
