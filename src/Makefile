## Makefile

TARGET		= galasm
OBJS		= galasm.o support.o jedec.o localize.o
CFILES		= galasm.c galasm.h jedec.c localize.c support.c
CC		= gcc

CFLAGS		= -Wall -O2
LDFLAGS		=


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
 
