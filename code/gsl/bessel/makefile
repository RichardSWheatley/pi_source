# A sample Makefile
# This Makefile demonstrates and explains 
# Make Macros, Macro Expansions,
# Rules, Targets, Dependencies, Commands, Goals
# Artificial Targets, Pattern Rule, Dependency Rule.


# define the c compiler
CC = gcc

# define any compile-time flags
CFLAGS = -static -Wall -g

#define and directories containing header files other than /pi/include
INCLUDES = -I/home/pi/gsl/include

# define library paths in addition to /pi/lib
LFLAGS = -L/home/pi/gsl/lib

# define any linkable libraries
LIBS = -lgsl -lgslcblas -lm

# Comments start with a # and go to the end of the line.
SRCS = gsl_bessel.c


# define the C object files
OBJS = $(SRCS:.c=.o)

# define the executable file
MAIN = $(SRCS:.c=.exe)

.PHONY: depend clean

# The rule for "all" is used to incrementally build your system.
# It does this by expressing a dependency on the results of that system,
# which in turn have their own rules and dependencies.
all: $(MAIN)
	@echo Compling the gsl_spmatrix example

# Here is a Rule that uses some built-in Make Macros in its command:
# $@ expands to the rule's target, in this case "test_me.exe".
# $^ expands to the rule's dependencies, in this case the three files
# main.o, test1.o, and  test2.o.
$(MAIN): $(OBJS)
	$(CC) $(CFLAGS) $(INCLUES) -o $(MAIN) $(OBJS) $(LFLAGS) $(LIBS)

# Here is a Pattern Rule, often used for compile-line.
# It says how to create a file with a .o suffix, given a file with a .cpp suffix.
# The rule's command uses some built-in Make Macros:
# $@ for the pattern-matched target
# $< for the pattern-matched dependency
.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

clean:
	$(RM) *.o *~ $(MAIN)

depend: $(SRCS)
	makedepend $(INCLUDES) $^

# DO NOT DELETE THIS LINE -- make depend need it

