CC = mpicc
CFLAGS = -march=native -O3 -Wall -I$(PETSC_DIR)/include
LDFLAGS = -lpetsc -L$(PETSC_DIR)/lib -lm
OS := $(shell uname)
ifeq ($(OS),Linux)
	LDFLAGS += -Wl,-rpath=$(PETSC_DIR)/lib
endif

TARGET = ssprk ts fdweno

all: $(TARGET)

%: %.c
	$(CC) $(CFLAGS) -o $* $< $(LDFLAGS)

clean:
	rm -f *.o $(TARGET)
