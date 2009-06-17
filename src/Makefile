# Makefile
# Change ~/usr/ to your install location, e.g., /usr/
# Change boost-1_36 to your version
# Change -gcc41-mt to yours. ls ~/usr/lib
# $ make check
# to check you have boost libraries

CC = g++
LINK = g++
INSTALL = install
CFLAGS = `pkg-config --cflags opencv` -I /usr/include/boost -I.
LFLAGS = `pkg-config --libs opencv` -L /usr/lib -lboost_system-mt -lboost_filesystem-mt
all: imageclipper

imageclipper.o: imageclipper.cpp
	$(CC) $(CFLAGS) -o $@ -c $^

imageclipper: imageclipper.o
	$(LINK) -o $@ $^ $(LFLAGS)

check:
	ls -d /usr/include/boost
	ls /usr/lib/libboost_system-mt.a
	ls /usr/lib/libboost_filesystem-mt.a

clean:
	rm -f imageclipper *.o

new:clean all

install:
	cp imageclipper ~/bin/
