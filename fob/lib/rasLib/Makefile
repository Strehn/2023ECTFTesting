CFLAGS = -Wall -Os -c
LDFLAGS = -g
CC = gcc
LIBS_PATH = -L.
LDLIBS = $(LIBS_PATH) -lrsa -lm

test: test.o librsa.a rsa.h

librsa.a: rsa.o
	ar rc librsa.a rsa.o
	ranlib librsa.a

rsa.o: rsa.c rsa.h
	$(CC) $(CFLAGS) -o $@ $<
	
sha256.o: sha256.c sha256.h
	$(CC) $(CFLAGS) -o $@ $<

aes.o : aes.c aes.h
	echo [CC] $@ $(CFLAGS)
	$(CC) $(CFLAGS) -o $@ $<

.PHONY: clean, all

clean:
	rm -f *.o a.out rsa.o rsa librsa.a

all: clean rsa
