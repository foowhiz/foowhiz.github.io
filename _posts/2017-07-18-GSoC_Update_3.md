---
layout: post
title: GSoC Update #3
---
This blog is numbered 3rd, and not second because the second one is not complete yet, it is a long one. Its work is in progress in a separate branch.

The code for the PDB reader has started ([Source](https://github.com/foowhiz/avogadrolibs/blob/pdbreader/avogadro/io/pdbformat.cpp)). I am using [this PDB reader](https://github.com/fogleman/ribbon/blob/master/pdb/reader.go) written in Go as a basis for it.
Here are a few concepts that I learned while coding the PDB reader:
## 1. Difference between END and ENDMDL record of PDB files
There may be many models of the same molecule within one PDB file. It's got something to do with NMR analysis, though I don't understand exactly why there are multiple models. But each model starts with a MODEL record and ends with an ENDMDL record.
On the othe hand, the END record marks the end of the whole PDB file.

## 2. Virtual vs Pure Virtual functions in C++
A virtual function has an implementation, and can be re-implemented in derived classes. Classes that define or inherit a virtual function are polymorphic classes.

A pure virtual function makes the class that it is defined in abstract. We cannot declare classes abstract in C++ as we do in Java by using the keyword `abstract`. A function is made pure virtual by adding a `=0` at the end of a virtual function definition.
(Source: [Stackoverflow](https://stackoverflow.com/questions/2652198/difference-between-a-virtual-function-and-a-pure-virtual-function), [cplusplus.com](http://www.cplusplus.com/doc/tutorial/polymorphism/))

## 3. Unit testing and GTest
Unit testing refers to testing individual units of a program. It is an important part of programming, and many sources say it should not be seen as a separate task, but as part of the code that is to be tested.
Google Test, aka GTEST, is a popular C++ testing framework. It's really easy to learn , and [here is the manual](https://github.com/google/googletest/blob/master/googletest/docs/Primer.md).

## 4. Asymmetric unit, biological assembly, and importance of RECORD 350
An asymmetric unit is the smallest unit in a crystal structure, after applying transformations to which, we can generate the whole crystal structure.
A biological assembly, aka biological unit, is the functional form of the biomolecule. Eg., the functional form of Hemoglobin has four chains.
Remark 350 contains transformations, rotational and translational, in the form of a matrix, that are to be applied to the molecule to generate the biological assembly.
All of this is explained in more and excellent detail at [PDB-101](https://pdb101.rcsb.org/learn/guide-to-understanding-pdb-data/biological-assemblies#Anchor-BioUnit).
