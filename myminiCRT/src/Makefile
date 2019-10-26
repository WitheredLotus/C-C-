OBJS = entry.o malloc.o stdio.o string.o printf.o
CFLAGS =  -g -m32 -fno-builtin -nostdlib -fno-stack-protector 
OBJS_DIR = ../obj

LIB_DIR = ../lib
BIN_DIR = ../bin

LDFLAGS = -m elf_i386 -static -e mini_crt_entry

all: test.c $(OBJS)
	gcc -c $(CFLAGS) test.c -o $(OBJS_DIR)/test.o
	ar -rs $(LIB_DIR)/minicrt.a $(OBJS_DIR)/*.o
	ld $(LDFLAGS) $(OBJS_DIR)/entry.o $(OBJS_DIR)/test.o $(LIB_DIR)/minicrt.a -o $(BIN_DIR)/test 
clean:
	rm $(OBJS_DIR)/*.o  $(BIN_DIR)/test $(LIB_DIR)/minicrt.a

$(OBJS):%.o:%.c
	gcc -c $(CFLAGS) $< -o $(OBJS_DIR)/$@