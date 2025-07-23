SHELL=/bin/sh

CLASS=S
BENCHMARK=cg
BENCHMARKU=CG
PARAMETERS=setparams

include ../config/make.def

COMPILE_CG=$(CC) $(BENCHMARK).cpp -DCLASS_$(CLASS) -o $(BENCHMARK).$(CLASS)
SET_PARAMETERS=$(CC) $(SYSDIR)/$(PARAMETERS).cpp -o $(PARAMETERS) && ./$(PARAMETERS) $(BENCHMARK) $(CLASS)
MOVE_BINARIES=mv $(BENCHMARK).$(CLASS) $(BINDIR) && mv $(PARAMETERS) $(SYSDIR)

$(BENCHMARK):
	$(pwd) $(SET_PARAMETERS) && $(COMPILE_CG) && $(MOVE_BINARIES)

clean:
	- rm -f *.o *~ 
	- rm -f npbparams.hpp core
