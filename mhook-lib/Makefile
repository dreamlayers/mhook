CXX := i686-w64-mingw32-gcc
CXXFLAGS := $(CXXFLAGS) -g -DUNICODE -D_UNICODE -DMINGW_HAS_SECURE_API=1
DISASM_LIB := ../disasm-lib/disasm.a
LIBNAME := mhook.a
OBJS := mhook.o

$(LIBNAME): $(OBJS) $(DISASM_LIB) Makefile
	cp $(DISASM_LIB) $@
	ar rs $@ $(OBJS)

mhook.o: mhook.cpp mhook.h ../disasm-lib/disasm.h ../disasm-lib/misc.h \
 ../disasm-lib/disasm_x86.h Makefile

.PHONY : clean
clean:
	rm -f $(LIBNAME) $(OBJS)
