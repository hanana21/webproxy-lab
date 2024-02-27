# Makefile for Proxy Lab 
#
# You may modify this file any way you like (except for the handin
# rule). You instructor will type "make" on your specific Makefile to
# build your proxy from sources.

CC = gcc
CFLAGS = -g -Wall
LDFLAGS = -lpthread

all: echo_client echo_server

csapp.o: csapp.c csapp.h
	$(CC) $(CFLAGS) -c csapp.c

echo_client.o: echo_client.c csapp.h
	$(CC) $(CFLAGS) -c echo_client.c

echo_client: echo_client.o csapp.o
	$(CC) $(CFLAGS) echo_client.o csapp.o -o echo_client $(LDFLAGS)

echo_server.o: echo_server.c csapp.h
	$(CC) $(CFLAGS) -c echo_server.c

echo_server: echo_server.o csapp.o
	$(CC) $(CFLAGS) echo_server.o csapp.o -o echo_server $(LDFLAGS)

# Creates a tarball in ../proxylab-handin.tar that you can then
# hand in. DO NOT MODIFY THIS!
handin:
	(make clean; cd ..; tar cvf $(USER)-proxylab-handin.tar proxylab-handout --exclude tiny --exclude nop-server.py --exclude proxy --exclude driver.sh --exclude port-for-user.pl --exclude free-port.sh --exclude ".*")

clean:
	rm -f *~ *.o echo_client core *.tar *.zip *.gzip *.bzip *.gz
	rm -f *~ *.o echo_server core *.tar *.zip *.gzip *.bzip *.gz

