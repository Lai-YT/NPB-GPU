SHELL=/bin/sh
BENCHMARK=is
BENCHMARKU=IS

include ../config/make.def

OBJS = is.o ${COMMON}/c_print_results.o ${COMMON}/c_${RAND}.o \
       ${COMMON}/c_timers.o ${COMMON}/c_wtime.o

include ../sys/make.common

${PROGRAM}: config ${OBJS} ${PROGRAM}_surface
	${CLINK} ${CLINKFLAGS} -o ${PROGRAM} ${OBJS} ${C_LIB}
${PROGRAM}_surface: config ${OBJS} is_surface.o
	${CLINK} ${CLINKFLAGS} -o $@ ${OBJS} ${C_LIB}

is.o:		is.cu npbparams.hpp
	${CCOMPILE} is.cu
is_surface.o:	is_surface.cu npbparams.hpp
	${CCOMPILE} is_surface.cu

clean:
	- rm -f *.o *~ 
	- rm -f npbparams.hpp core
