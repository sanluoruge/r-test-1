# r-test

This repository serves as a container for regression test data for OpenFAST. The test cases are taken from the FAST V8 CertTests. The repository contains:
- input files for test execution
- directories with outputs for various machine and compiler combinations
The output files serve as "gold standard" solutions for the regression test suite.

## inputs
The inputs directory contains the OpenFAST input files for the 26 CertTest cases: `.fst`. Also included are turbine specific auxiliary files:
5MW_Baseline
AOC
AWT27
SWRT
- spd_trq.dat
UAE_VI
WP_Baseline
- pitch.ipt

## macos-gnu
These results were generated on a MacBook Pro running on macOS Sierra 10.12.4. The OpenFAST binary was compiled with gfortran installed through Homebrew's gcc package at gcc version 6.3.0 (Homebrew GCC 6.3.0_1).

## rhel-intel
These results were generated on NREL's Peregrine HPC cluster running on Red Hat Enterprise Linux Server release 6.3 (Santiago). The OpenFAST binary was compiled with Intel's ifort compiler version

## How this repository can be used
### Local baseline
The inputs directory is included here to provide an easy method for local testing of OpenFAST. Copy `inputs` to a new directory and run the included cases to generate a local "gold standard" set.
### NOTE
The 5MW turbine cases require a compiled controller library for ServoDyn. A python script is included in `inputs` to compile the necessary controllers. Run the python script with this command:
`python compileDISCON.py [compiler type: gnu/intel] [build type: debug/release]`
for example:
`python compileDISCON.py gnu release`
