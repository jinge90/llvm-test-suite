##===- Makefile --------------------------------------------*- Makefile -*-===##
#
# This makefile runs the SPEC benchmarks.
#
##===----------------------------------------------------------------------===##

LEVEL = ../..
PARALLEL_DIRS := CFP2006 CINT2006 CFP2000 CINT2000 CFP95 CINT95
include $(LEVEL)/Makefile.config

#
# Remove SPEC95, SPEC2000, and SPEC2006 per the user's configuration
#
ifndef USE_SPEC2006
PARALLEL_DIRS := $(filter-out CFP2006, $(PARALLEL_DIRS))
PARALLEL_DIRS := $(filter-out CINT2006, $(PARALLEL_DIRS))
endif

ifndef USE_SPEC2000
PARALLEL_DIRS := $(filter-out CFP2000, $(PARALLEL_DIRS))
PARALLEL_DIRS := $(filter-out CINT2000, $(PARALLEL_DIRS))
endif

ifndef USE_SPEC95
PARALLEL_DIRS := $(filter-out CFP95, $(PARALLEL_DIRS))
PARALLEL_DIRS := $(filter-out CINT95, $(PARALLEL_DIRS))
endif

# If reference input is requested, these are run under the SPEC test module.
# (The test module uses the makefile harness as well but it builds the
# benchmarks directly under their subdirectory so this check is bypassed.)
ifdef USE_SPEC_TEST_MODULE
PARALLEL_DIRS := $(filter-out CFP2006 CINT2006 CINT2000, $(PARALLEL_DIRS))
endif

include $(LEVEL)/Makefile.programs
