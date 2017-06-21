---
layout: post
title: GSoC Update #1
---

I've had a good amount of time to go through the code of 3Dmol.js. I now understand the flow of code across different files and functions in it.
My task so far was to find out what info I'd need from the [PDB](https://en.wikipedia.org/wiki/Protein_Data_Bank) file that'd be supplied as input to Avogadro 2. For this, I searched through [parsers.js](https://github.com/3dmol/3Dmol.js/blob/master/3Dmol/parsers.js#L1317), and the following is the list of records that 3Dmol.js takes in from the PDB file

1. ATM and HETATM
  *   Alternate Location
  *   Serial
  *   Atom name
  *   Residue name
  *   Chain ID
  *   Residue sequence number
  *   iCode
  *   x, y and z coordinates
  *   Element symbol
  *   Temperature factor
  
2. SHEET
  *   Chain ID of initial residue in strand
  *   Chain ID of terminal residue in strand
  *   Sequence number of initial residue in strand
  
3. CONECT
  *   Serial number of atom
  *   Serial number of bonded atoms
  
4. HELIX
  *   Chain ID of initial chain containing helix
  *   Chain ID of end chain containing helix
  *   Sequence number of initial residue
  *   Sequence number of terminal residue
  
5. REMARK
  *   Info from REMARK 350, if present
  
6. CRYST1
  *   Unit cell parameters: Lengths a, b, c and angles alpha, beta and gamma
  
7. ANISOU
  *   Atom serial number
  *   Temperature factors
  
My next task is to create a mesh geometry using the above records, which can be sent for rendering.
