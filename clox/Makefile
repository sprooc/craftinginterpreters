# Directory to store object files
OBJDIR = build

# Find all .c source files in the current directory
SRC = $(wildcard *.c)

# Generate corresponding .o file paths in the OBJDIR folder
OBJ = $(SRC:%.c=$(OBJDIR)/%.o)

# Compiler and compilation flags
CC = gcc
CFLAGS = -Wall -g -O2

TARGET = clox

# Default target: build the final executable
all: $(TARGET)

# Link all object files to create the final executable
$(TARGET): $(OBJ)
	$(CC) $(CFLAGS) -o $@ $^

# Compile .c files to .o files, placing them in the OBJDIR folder.
# The pipe symbol (|) indicates that OBJDIR is an order-only prerequisite.
$(OBJDIR)/%.o: %.c | $(OBJDIR)
	$(CC) $(CFLAGS) -c $< -o $@

# Create the object directory if it doesn't exist
$(OBJDIR):
	mkdir -p $(OBJDIR)

# Clean up generated files
clean:
	rm -rf $(OBJDIR) $(TARGET)

run:
	./clox src.lox

.PHONY: all clean
