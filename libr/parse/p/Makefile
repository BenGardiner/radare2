include ../../config.mk
include ../../util/deps.mk

CFLAGS+=-I../../include -Wall -fPIC ${LDFLAGS_LIB} ${LDFLAGS_LINKPATH}..
# XXX
CFLAGS+=-DLIL_ENDIAN=1
# -D__UNIX__
CFLAGS+=-DCORELIB

foo: all

ALL_TARGETS=
ARCHS=att2intel.mk x86_pseudo.mk mreplace.mk arm_pseudo.mk z80_pseudo.mk ppc_pseudo.mk 6502_pseudo.mk
include $(ARCHS)

all: ${ALL_TARGETS}
	@true

clean:
	-rm -f *.${EXT_SO} *.o ${STATIC_OBJ}

mrproper: clean
	-rm -f *.d */*.d

.PHONY: all clean foo mrproper
