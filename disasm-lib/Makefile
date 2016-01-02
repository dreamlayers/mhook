CC := i686-w64-mingw32-gcc
CFLAGS := $(CFLAGS) -g -DUNICODE -D_UNICODE
LIBNAME := disasm.a
OBJS := cpu.o disasm.o disasm_x86.o misc.o

$(LIBNAME): $(OBJS) Makefile
	rm -f $@
	ar rs $@ $(OBJS)

cpu.o: cpu.c cpu.h misc.h Makefile
disasm.o: disasm.c disasm.h misc.h disasm_x86.h Makefile
disasm_x86.o: disasm_x86.c disasm.h misc.h disasm_x86.h cpu.h \
 disasm_x86_tables.h Makefile
misc.o: misc.c misc.h Makefile

.PHONY : clean
clean:
	rm -f $(LIBNAME) $(OBJS)
