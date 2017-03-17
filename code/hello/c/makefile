all: hello_world.exe

hello_world.exe: hello_world.o
	gcc -g -o hello_world.exe hello_world.o

hello_world.o: hello_world.c
	gcc -c -Wall -g hello_world.c

clean:
	rm hello_world.o hello_world.exe
