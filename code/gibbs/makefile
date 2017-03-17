# A sample Makefile
# This Makefile demonstrates and explains 
# Make Macros, Macro Expansions,
# Rules, Targets, Dependencies, Commands, Goals
# Artificial Targets, Pattern Rule, Dependency Rule.


# define the c compiler
CC = gcc

# define any compile-time flags
CFLAGS = -static -O4 -Wall -g

#define and directories containing header files other than /pi/include
INCLUDES = -I/home/pi/gsl/include

# define library paths in addition to /pi/lib
LFLAGS = -L/home/pi/gsl/lib

# define any linkable libraries
LIBS = -lgsl -lgslcblas -lm

# Comments start with a # and go to the end of the line.
SRCS = gibbs.c

# define the C object files
OBJS = $(SRCS:.c=.o)
 
# define the executable file
MAIN = $(SRCS:.c=.exe)

# The rule for "all" is used to incrementally build your system.
# It does this by expressing a dependency on the results of that system,
# which in turn have their own rules and dependencies.
all: $(MAIN)
	@echo Compling the gibbs example

# Here is a Rule that uses some built-in Make Macros in its command:
# $@ expands to the rule's target, in this case "test_me.exe".
# $^ expands to the rule's dependencies, in this case the three files
# main.o, test1.o, and  test2.o.
$(MAIN): $(OBJS)
	$(CC) $(CFLAGS) $(INCLUDES) -o $(MAIN) $(OBJS) $(LFLAGS) $(LIBS)

clean:
	$(RM) *.o *~ $(MAIN)

