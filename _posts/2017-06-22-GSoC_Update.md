---
layout: post
title: GSoC Update #1
---

I've had a good amount of time to go through the code of 3Dmol.js. I now understand the flow of code across different files and functions in it.
My task so far was to find out what info I'd need from the [PDB](https://en.wikipedia.org/wiki/Protein_Data_Bank) file that'd be supplied as input to Avogadro 2. For this, I searched through [parsers.js](https://github.com/3dmol/3Dmol.js/blob/master/3Dmol/parsers.js#L1317), and the following is the list of records that 3Dmol.js takes in from the PDB file

1. ATM and HETATM
  a. Alternate Location
  
  b. Serial
  c. Atom name
  d. Residue name
  e. Chain ID
  f. Residue sequence number
  g. iCode
  h. x, y and z coordinates
  i. Element symbol
  j. Temperature factor
  
2. SHEET
  a. Chain ID of initial residue in strand
  b. Chain ID of terminal residue in strand
  c. Sequence number of initial residue in strand
  
3. CONECT
  a. Serial number of atom
  b. Serial number of bonded atoms
  
4. HELIX
  a. Chain ID of initial chain containing helix
  b. Chain ID of end chain containing helix
  c. Sequence number of initial residue
  d. Sequence number of terminal residue
  
5. REMARK
  a. Info from REMARK 350, if present
  
6. CRYST1
  a. Unit cell parameters: Lengths a, b, c and angles alpha, beta and gamma
  
7. ANISOU
  a. Atom serial number
  b. Temperature factors
  
My next task is to create a mesh geometry using the above records, which can be sent for rendering.
