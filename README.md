# Companion code for extreme points of Gibbs-preserving stochastic maps

A computational companion to the study of the convex structure of Gibbs-preserving stochastic maps with degenerate energy spectra.

This repository contains a Wolfram Mathematica notebook implementing symbolic constructions of extreme-point germs of Gibbs-preserving stochastic maps in the presence of energy degeneracy. The code accompanies the associated paper and provides tools for exploring both high-temperature and low-temperature extremal families.

## Overview

The notebook implements two complementary constructions:

- **High-temperature construction**: generates first-order extreme-point germs emerging from permutation matrices in the infinite-temperature limit.
- **Low-temperature construction**: generates extreme-point germs emerging from admissible deterministic stochastic maps in the zero-temperature limit.

## Main Functions

### High-temperature analysis

```Mathematica
HighTempExtPoints[testPerm, dim]
```

```Mathematica
AllHighTExtPoints[enStruct]
```

### Low-temperature analysis

```Mathematica
GenerateAdmissibleMatrices[enStruct]
```

```Mathematica
LowTempExtPoints[testPerm, dim, enStruct]
```

```Mathematica
AllLowTExtPoints[enStruct]
```

## Energy-Degeneracy Structure

```Mathematica
enStruct = {d0, d1, ..., dk}
```

Example:

```Mathematica
enStruct = {2, 1, 3}
dim = Total[enStruct];
```

## Typical Workflow

```Mathematica
enStruct = {2, 1};

dim = Total[enStruct];

highTempResults = AllHighTExtPoints[enStruct];
admissibleMatrices = GenerateAdmissibleMatrices[enStruct];
lowTempResults = AllLowTExtPoints[enStruct];
```

## Output Convention

All generated maps are represented as column-stochastic matrices satisfying

```Mathematica
M.g == g
```

for the appropriate Gibbs vector `g`.

## Computational Remarks

The computational cost grows rapidly with Hilbert-space dimension due to the enumeration of permutation matrices, admissible zero-temperature matrices, active constraints, and symbolic feasibility checks.

## Citation

If you use this code in academic work, please cite the accompanying paper and acknowledge this repository.

## License

This repository is licensed under the Creative Commons Attribution 4.0 International License (CC BY 4.0).
