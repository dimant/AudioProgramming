CC=gcc
CXX=g++
RM=rm -f
CPPFLAGS=-g -I.
LDFLAGS=-g 
LDLIBS=

ODIR=obj

CCSRCS=ieee80.c portsf.c
CPPSRCS=main.cpp
CCOBJS=$(subst .c,.o,$(CCSRCS))
CPPOBJS=$(subst .cpp,.o,$(CPPSRCS))
_OBJS=$(CCOBJS) $(CPPOBJS)
OBJS = $(patsubst %,$(ODIR)/%,$(_OBJS))

$(ODIR)/%.o: %.c
	$(CC) -c -o $@ $< $(CPPFLAGS)

$(ODIR)/%.o: %.cpp
	$(CXX) -c -o $@ $< $(CPPFLAGS)

all: Chapter2

Chapter2: $(OBJS)
	$(CXX) $(LDFLAGS) -o $@ $(OBJS) $(LDLIBS)

depend: .depend

.depend: $(CCSRCS) $(CPPSRCS)
	$(RM) ./.depend
	$(CXX) $(CPPFLAGS) -MM $^>>./.depend;

clean:
	$(RM) $(OBJS)

distclean: clean
	$(RM) .depend

include .depend