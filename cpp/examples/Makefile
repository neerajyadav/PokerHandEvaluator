CC=gcc
CXX=g++
TOPDIR=..
INCLUDE=${TOPDIR}/include
SRC=${TOPDIR}/src
CFLAGS+=-std=c99
CXXFLAG+=-std=c++11

all: c_example cpp_example omaha_example

c_example: c_example.c ../libpheval.a
	${CC} ${CFLAGS} -I${INCLUDE} $^ -o $@

cpp_example: cpp_example.cc ../libpheval.a
	${CXX} ${CFLAGS} ${CXXFLAG} -I${INCLUDE} $^ -o $@

omaha_example: omaha_example.cc ../libphevalomaha.a
	${CXX} ${CFLAGS} ${CXXFLAG} -I${INCLUDE} $^ -o $@

../libpheval.a:
	$(MAKE) -C ../;

../libphevalomaha.a:
	$(MAKE) -C ../ libphevalomaha.a

%.o: %.cc
	${CXX} -c ${CXXFLAG} -I${INCLUDE} $< -o $@

%.o: %.c
	${CC} -c ${CFLAGS} -I${INCLUDE} $< -o $@

clean:
	rm -f *.o c_example cpp_example omaha_example
