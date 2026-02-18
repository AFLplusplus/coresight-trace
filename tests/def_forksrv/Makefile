CC = gcc
CFLAGS = -Wall -fPIC -g -O0  
APP = main
FORKSRVPATH = ../../libforksrv/libforksrv.a 

all: $(APP)

$(APP): main.c  
	$(CC) $(CFLAGS) -o $(APP) -static main.c $(FORKSRVPATH)
 
trace: $(APP)
	sudo CS_DEFER_FORKSRV=1 ../../cs-trace --decoding=edge -- ./$(APP)

fuzz: $(APP)
	sudo CS_DEFER_FORKSRV=1 ../../../../afl-fuzz -A -i in -o out -- ./$(APP)
test: $(APP) trace clean

clean:
	rm -f $(APP) *.o cstrace.bin decoderargs.txt

.PHONY: all clean test fuzz trace