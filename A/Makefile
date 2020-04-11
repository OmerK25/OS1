.DEFAULT_GOAL := all
CC=gcc
FLAGS=-Wall -g
LIBFLAGS=-Wall -g -shared

all: subtask1.1 subtask1.2 subtask1.3

subtask1.1: main1_1.o hello_Ariel.o
	$(CC) $(FLAGS) -o subtask1.1 main1_1.o hello_Ariel.o

subtask1.2: main1_2.o mylib
	$(CC) $(FLAGS) -o subtask1.2 main1_2.o ./libmylib.so

subtask1.3: main1_3.o
	$(CC) $(FLAGS) -o $@ main1_3.o -ldl

mylib: hello_Ariel.o
	$(CC) $(LIBFLAGS) -o libmylib.so hello_Ariel.o

main1_1.o: main1_1.c hello_Ariel.h
	$(CC) $(FLAGS) -c main1_1.c

main1_2.o: main1_2.c hello_Ariel.h
	$(CC) $(FLAGS) -c main1_2.c

main1_3.o: main1_3.c hello_Ariel.h
	$(CC) $(FLAGS) -c main1_3.c

hello_Ariel.o: hello_Ariel.c hello_Ariel.h
	$(CC) $(FLAGS) -c -fPIC hello_Ariel.c


.PHONY: clean all

clean:
	rm -f subtask1.1 subtask1.2 subtask1.3 *.o *.so