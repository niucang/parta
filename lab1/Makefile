###############################################################################
# COSC1076 - Advanced Programming Techniques                                  #
# Assessed lab 1 - debugging                                                  #
# Created by Paul Miller                                                      #
#                                                                             #
# Makefile for the assessed lab. Simply type 'make' (no quotes) to compile    #
# this project.                                                               #
###############################################################################

# The head files for this project
HEADERS=reader.h writer.h shared.h swapper.h
# The object files that need to be built for this project
OBJECTS=reader.o writer.o swapper.o
# The compiler we are using 
CC=gcc
# The compiler flags
CFLAGS=-ansi -Wall -pedantic
# The linker flags
LFLAGS=

# The default target is always first in the file - it just calls the 'poker' 
# target
all:swapper

# This target calls the linker. It links together all the object files that 
# have been compiled along with any libraries that you have included.
swapper: $(OBJECTS)
	$(CC) $(LFLAGS) $(OBJECTS) -o swapper

# compiles each .c file into a .o file
%.o:%.c $(HEADERS)
	$(CC) $(CFLAGS) -c $<

#compilation target for debugging: 
debug:CFLAGS+=-g
debug: clean all

#compilation target for address sanitisation: 
sanitize:CFLAGS+=-g -fsanitize=address
sanitize:LFLAGS+=-fsanitize=address
sanitize: clean all

# the clean target - deletes the object files and the executable
.PHONY:clean
clean:
	rm -f *.o swapper
