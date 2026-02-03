.PHONY: all clean

CFLAGS = -fPIC -Wall -Wextra
LDFLAGS = -shared -ldl

all: libforksrv.so libforksrv.a

libforksrv.so: libforksrv.c
	-@$(CC) $(CFLAGS) $^ $(LDFLAGS) -o $@  

libforksrv.a: libforksrv.c
	-@$(CC) $(CFLAGS) $^ -DSTATIC -c -o $@ 

clean:
	rm -f libforksrv.so libforksrv.a

