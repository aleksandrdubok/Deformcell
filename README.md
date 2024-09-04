Deformcell
========

A program for cell deformation compatible with Vienna ab initio simulation package POSCAR and CONTCAR file formats.

Installation
------------

1. Download or clone the repository.
2. Install by either adding the putting the deformcell in a folder in your $PATH (~/bin).
3. Change permissions: $chmod +x deformcell.

Basic usage
-----------

$deformcell -t TYPE_OF_DEFORMATION -s STEP -i INPUT_FILE -o OUTPUT_FILE

For help enter: $deformcell -h. 
This script introduce the deformation by multyplying the matrix of basis vectors from input POSCAR or CONTCAR file by the deformation matrix (which is transposed Jacobian matrix 
of deformation, see https://doi.org/10.1103/PhysRevB.52.12627 for reference). 
When using the deformcell note, that input file must be in VASP POSCAR (or CONTCAR) file format, the coordinates being direct (see https://www.vasp.at/wiki/index.php/POSCAR). 
Note, that for any non-test task at least -t and -s options must be set. In the abscense of these two parameters, a trivial deformation of 0% is introduced.
  
Examples of usage
-----------

Introduce the isostatic compression of 10%: $deformcell -t volume -s -10 -i ./POSCAR -o ./mPOSCAR. 
Introduce the uniaxial tension of 10% at cartesian x axis direction: $deformcell -t axialx -s 10 -i ./CONTCAR -o ./POSCAR 

Authors
-------

[Aleksandr Dubok] (https://www.researchgate.net/profile/Aleksandr-Dubok)

License
---------------------

Copyright 2024 Dubok Aleksandr under the Apache License 2.0. See the LICENSE file for more detailed information.
