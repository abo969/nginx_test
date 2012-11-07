CXX = gcc
CXXFLAGS += -g -Wall -Wextra

NGX_ROOT = /home/abo/nginx-1.0.4
#NGX_ROOT = /usr/src/nginx-1.0.4

TARGETS = ngx_hash_t_test
TARGETS_C_FILE = $(TARGETS).c

CLEANUP = rm -f $(TARGETS) *.o

all: $(TARGETS)

clean:
	$(CLEANUP)

CORE_INCS = -I. \
		-I$(NGX_ROOT)/src/core \
		-I$(NGX_ROOT)/src/event \
		-I$(NGX_ROOT)/src/event/modules \
		-I$(NGX_ROOT)/src/os/unix \
		-I$(NGX_ROOT)/objs \

#LIBS = -lcrypt -lpcre -lcrypto -lz

NGX_PALLOC = $(NGX_ROOT)/objs/src/core/ngx_palloc.o
NGX_STRING = $(NGX_ROOT)/objs/src/core/ngx_string.o
NGX_ALLOC = $(NGX_ROOT)/objs/src/os/unix/ngx_alloc.o
NGX_ARRAY = $(NGX_ROOT)/objs/src/core/ngx_array.o
NGX_HASH = $(NGX_ROOT)/objs/src/core/ngx_hash.o

$(TARGETS): $(TARGETS_C_FILE)
	$(CXX) $(CXXFLAGS) $(CORE_INCS) $(NGX_PALLOC) $(NGX_STRING) $(NGX_ALLOC) $(NGX_ARRAY) $(NGX_HASH) $^ -o $@ #$(LIBS)
