include $(top_builddir)/config/config.mk
include $(top_builddir)/config/targets.mk

# How to find source files
VPATH = $(srcdir)/..:$(srcdir)/../../common

# Which compiler to use to link
CXX = ${MPICXX}
CXXLD = ${MPICXX}

AM_LDFLAGS = $(HIP_LDFLAGS)
AM_CPPFLAGS = $(HIP_INC) $(MPI_CPPFLAGS) -I$(top_srcdir)/src/mpi/common -D__HIP_PLATFORM_HCC__= -I/opt/hcc/include

# What is the destination for programs built from this directory?
epcudadir = $(bindir)/EP/HIP

# What programs should be installed in the destination?
epcuda_PROGRAMS = BusSpeedDownload \
						BusSpeedReadback \
						DeviceMemory \
						MaxFlops

BusSpeedDownload_SOURCES	= main.cpp
BusSpeedDownload_LDADD		= BusSpeedDownload.o /home/aditya/Documents/HIP-privatestaging/src/hip_hcc.o $(top_srcdir)/src/common/OptionParser.o -lstdc++ -lc++ -lSHOCCommon -L/opt/hcc/lib -L/opt/hsa/lib -lhc_am -lhsa-runtime64 -ldl -lpthread -lmcwamp -lm $(HIP_LIBS) $(LIBS) 

BusSpeedReadback_SOURCES	= main.cpp
BusSpeedReadback_LDADD		= BusSpeedReadback.o /home/aditya/Documents/HIP-privatestaging/src/hip_hcc.o $(top_srcdir)/src/common/OptionParser.o -lstdc++ -lc++ -lSHOCCommon -L/opt/hcc/lib -L/opt/hsa/lib -lhc_am -lhsa-runtime64 -ldl -lpthread -lmcwamp -lm $(HIP_LIBS) $(LIBS) 

DeviceMemory_SOURCES	= main.cpp
DeviceMemory_LDADD		= DeviceMemory.o /home/aditya/Documents/HIP-privatestaging/src/hip_hcc.o -lstdc++ -lc++ -L/opt/hcc/lib -L/opt/hsa/lib -lhc_am -lhsa-runtime64 -ldl -lpthread -lmcwamp -lm -lSHOCCommon $(HIP_LIBS) $(LIBS) 

MaxFlops_SOURCES	= main.cpp
MaxFlops_LDADD		= MaxFlops.o $(HIP_LIBS) $(LIBS)

