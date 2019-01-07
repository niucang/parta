HEADERS=fsupport.h phone.h
OBJECTS=fsupport.o phonebk_strtok.o
CC=gcc
CFLAGS=-ansi -Wall -pedantic
LFLAGS=
#by default call the phonebk target
all:phonebk
#link the phonebk target together to an executable
phonebk: fsupport.o phonebk_strtok.o
	$(CC) $(LFLAGS) $^ -o phonebk

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

#delete files created as part of compilation
.PHONY:clean
clean:
	rm -f phonebk *.o
zip:	
	zip -r assessedlabs22014 *.c *.h Makefile 
