#Make
MAKE = make
# Compiler setting
CC = gcc
CXX = g++

include ${SNACK_BASE}/make_sys/system.mk

INCLUDE_FLAGS = -I${INCLUDE_BASE} -I${SNACK_PATTERN} -I${INCLUDE_CASE} 

CFLAGS = $(CC_DEBUG) $(INCLUDE_FLAGS)

.SUFFIXS:
.SUFFIXS: .cc
.cc.o:
	$(CC) -c $(CFLAGS) -o $@ $<

# Linkder setting
LINK = g++
LDFLAGS = 

SHARED_LDFLAGS = -shared

SRC = coroutine.cc  \
	  co.cc

OBJ = $(subst .cc,.o, $(SRC))

TARGET = co
TARGET_LIB = 

ALL: $(OBJ)

EXE: $(OBJ) main.o ../../case_base.o ../../case_mgr.o
	$(LINK) $(LDFLAGS) $(OBJ) ../../case_base.o ../../case_mgr.o main.o -o $(TARGET)

CLEAN:
	rm -f *.o
	rm -f $(TARGET)
