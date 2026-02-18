.PHONY: all clean

CFLAGS = -fPIC -Wall -Wextra
LDFLAGS = -shared -ldl
CROSS-COMPILER = arm-linux-gnueabi-gcc

all: libforksrv.so libforksrv.a

libforksrv.so: libforksrv.c
	-@$(CC) $(CFLAGS) $^ $(LDFLAGS) -o $@  

libforksrv.a: libforksrv.c
	-@$(CC) $(CFLAGS) $^ -DSTATIC -c -o $@ 

libforksrv32.a: libforksrv.c
	-@$(CROSS-COMPILER) $(CFLAGS) $^ -DSTATIC -c -o $@ 

clean:
	rm -f libforksrv.so libforksrv.a libforksrv32.a

