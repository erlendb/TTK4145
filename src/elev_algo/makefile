
EXECUTABLE = ttk4145demoelevator.so

CC = gcc
CFLAGS = -Wall -Wextra -g -std=gnu11 -fPIC -shared
LDFLAGS = -fPIC -shared

SOURCES := $(patsubst ./%, %, $(shell find . -name '*.c'  ! -name '*test*'))
OBJECTS = $(addprefix $(OBJDIR)/, $(SOURCES:.c=.o))


OBJDIR = obj

all: $(EXECUTABLE)

rebuild:	clean all

clean:
	rm -f $(EXECUTABLE)
	rm -rf $(OBJDIR)

$(EXECUTABLE): $(OBJECTS)
	$(CC) $^ -o $@ $(LDFLAGS)

$(OBJDIR)/%.o: %.c
	@mkdir -p $(@D)
	$(CC) -o $@ -c $(CFLAGS) $<


.PHONY: all rebuild clean
