all: k810fn

CC=gcc
CXX=g++
COBJS=hid.o
CPPOBJS=k810fn.o
OBJS=$(COBJS) $(CPPOBJS)
CFLAGS+=-I../include/ -Wall -g -c
LIBS=-framework IOKit -framework CoreFoundation


k810fn: $(OBJS)
	g++ -Wall -g $^ $(LIBS) -o k810fn

$(COBJS): %.o: %.c
	$(CC) $(CFLAGS) $< -o $@

$(CPPOBJS): %.o: %.cpp
	$(CXX) $(CFLAGS) $< -o $@

clean:
	rm -f *.o k810fn $(CPPOBJS)

.PHONY: clean
