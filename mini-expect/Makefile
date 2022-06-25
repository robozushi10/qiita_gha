PROGRAM=mini_expect

SRCS= mini_exp_main.c       \
	  mini_exp_command.c 	\
	  mini_exp_inst.c 		\
	  mini_exp_mem.c

HDRS=mini_exp_command.h 	\
	 mini_exp_futex.h 		\
	 mini_exp_inst.h 		\
	 mini_exp_mem.h 		\
	 mini_exp_std.h

OBJS=$(SRCS:%.c=%.o)
GCNOOBJS=$(SRCS:%.c=%.gcno)
GCDAOBJS=$(SRCS:%.c=%.gcda)
GCOVOBJS=$(SRCS:%.c=%.c.gcov)
CC=gcc
ifeq ($(COV), gcov)
  CFLAGS=-Wall -g -fprofile-arcs -ftest-coverage 
else
  CFLAGS=-Wall -g
endif
LDFLAGS=-lutil -lpthread
$(PROGRAM):$(OBJS) $(HDRS)
	$(CC) $(CFLAGS) -o $(PROGRAM) $(OBJS) $(LDLIBS) $(LDFLAGS)

.PHONY: clean
clean:
	rm -f $(OBJS) $(PROGRAM) $(GCNOOBJS) $(GCDAOBJS) $(GCOVOBJS)
	rm -f *.info *.log
	rm -rf OUTPUT

