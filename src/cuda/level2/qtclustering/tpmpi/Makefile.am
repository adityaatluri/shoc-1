include $(top_builddir)/config/config.mk
include $(top_builddir)/config/targets.mk

# How to find source files
VPATH = $(srcdir)/..:$(srcdir)/../../../common:$(srcdir)/../../../../common

# Which compiler to use to build and link
CXX = ${MPICXX}
CXXLD = ${MPICXX}

AM_LDFLAGS = $(CUDA_LDFLAGS)
AM_CPPFLAGS = $(CUDA_INC) $(MPI_CPPFLAGS) -I$(top_srcdir)/src/mpi/common

# What is the destination for programs built from this directory?
tpcudadir = $(bindir)/TP/CUDA

# What programs should be installed to that destination?
tpcuda_PROGRAMS = QTC

# How to build those programs?
QTC_SOURCES = comm.cpp \
				libdata.cpp \
                main.cpp
QTC_LDADD = QTC.o $(CUDA_LIBS) $(LIBS)

