#
# diStorm3 (Linux Port)
#

TARGET	= libdistorm3.so
COBJS	= ../../src/mnemonics.o ../../src/wstring.o ../../src/textdefs.o ../../src/prefix.o ../../src/operands.o ../../src/insts.o ../../src/instructions.o ../../src/distorm.o ../../src/decoder.o
CC	= gcc
CFLAGS	+= -fPIC -O2 -Wall -DSUPPORT_64BIT_OFFSET -DDISTORM_STATIC
LDFLAGS	+= -shared
PREFIX	= /usr/local
DESTDIR	=

all: clib

clean:
	/bin/rm -rf ../../src/*.o ${TARGET} ../../distorm3.a ./../*.o

clib: ${COBJS}
	${CC} ${CFLAGS} ${VERSION} ${COBJS} ${LDFLAGS} -o ${TARGET}
	ar rs ../../distorm3.a ${COBJS}

install: libdistorm3.so
	install -D -s ${TARGET} ${DESTDIR}/${PREFIX}/lib/${TARGET}
	@echo "... running ldconfig might be smart ..."

.c.o:
	${CC} ${CFLAGS} ${VERSION} -c $< -o $@

