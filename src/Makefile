## Makefile

TARGET		= galasm
OBJS		= galasm.o support.o jedec.o localize.o
CFILES		= galasm.c galasm.h jedec.c localize.c support.c
CC		= gcc

CFLAGS		= -Wall -O2
LDFLAGS		=
PYTHON		?= python3

# Architectures to build for, e.g. ARCHS="x86_64 arm64" for a macOS
# universal binary.  Empty builds for the compiler's default architecture.
ARCHS		=
TARGET_ARCH	= $(addprefix -arch ,$(ARCHS))

test: galasm ratspeak.pld
	./galasm ratspeak.pld

all: $(TARGET)

$(TARGET): $(OBJS) $(CFILES)
	gcc $(LDFLAGS) -o $@ $(OBJS)

clean:
	-rm -f $(OBJS)
	-rm -f *.[oa] $(TARGET) Makefile.bak
	-rm -f *.fus *.chp *.jed *.pin

cleantilde:
	/usr/bin/find . -regex ".+~$$" -exec /bin/rm {} \;
 
