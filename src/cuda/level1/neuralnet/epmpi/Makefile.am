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
epcudadir = $(bindir)/EP/CUDA

# What programs should be installed to that destination?
epcuda_PROGRAMS = NeuralNet

# How to build those programs?
NeuralNet_SOURCES = main.cpp
NeuralNet_LDADD = NeuralNet.o $(CUDA_LIBS) $(LIBS) -lcublas

