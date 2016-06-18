CC = gcc #selfbuild
#CC=arm-linux-gnueabi-gcc #crossbuild
CFLAGS= -g -Wall
VERSION=1.0.2
INSTALL_DIR=/usr/local/lib/

SRC_NAME=libserialfunc
LIB_NAME=libSerialFunc

all:$(LIB_NAME).o ${LIB_NAME}.so

${LIB_NAME}.o:	
	${CC} ${SRC_NAME}.c -c -fPIC -o ${LIB_NAME}.o

${LIB_NAME}.so:
	${CC} -shared -O2 -Wl,-soname,${LIB_NAME}.so -o ${LIB_NAME}.so.${VERSION} ${LIB_NAME}.o

install:
	cp ${LIB_NAME}.so.${VERSION} ${INSTALL_DIR}
	ldconfig

uninstall:
	rm ${INSTALL_DIR}/${LIB_NAME}.so.*
	ldconfig

clean:
	rm -f *.o *.so *.so.*
