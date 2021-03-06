# amplituhedronBoundaries

![latest version](https://img.shields.io/badge/version-1.0.2-blue.svg)
![compatibility](https://img.shields.io/badge/Mathematica-11.x-Red.svg)

amplituhedronBoundaries is a Mathematica package for studying the boundary stratifications of three positive geometries: the amplituhedron, the momentum amplituhedron, and the hypersimplex. The first two geometries are relevant for scattering amplitudes in planar <img src="https://render.githubusercontent.com/render/math?math=\mathcal{N}=4"> SYM, while the last one is a well-studied polytope appearing in many important contexts in mathematics. This package includes an array of useful tools for exploring the structure of these positive geometries, including their boundary stratifications, drawing their boundary posets, and additional tools for manipulating combinatorial structures useful for positive Grassmannians.

# Documentation

Documentation for this package can be found at [[arxiv:2002.07146]](https://arxiv.org/abs/2002.07146).

# Installation and Setup

The amplituhedronBoundaries package was developed using Mathematica 11. Some of the functions produce unexpected behaviour for Mathematica 12+.

## Dependencies
The amplituhedronBoundaries package has the following Mathematica package dependencies:
- MaTeX: for creating Latex labels in diagrams. This package can be installed following the instructions found [here](https://github.com/szhorvat/MaTeX).
- positroids: for finding the stratification of boundaries in the positive Grassmannian. This package was written by Jacob Bourjaily [arXiv:1212.6974] and it is available for download from his arXiv submission [here](https://arxiv.org/e-print/1212.6974).

## Installation
The amplituhedronBoundaries package is available on GitHub and can be download using
```
SetDirectory[NotebookDirectory[]];
URLDownload["https://raw.githubusercontent.com/mrmrob003/amplituhedronBoundaries/master/"<>#,#]&@"amplituhedronBoundaries.m";
 ```
which downloads the package into directory of the notebook used to execute the above command. 

Once the amplituhedronBoundaries package has been downloaded, together with the pre-requisite packages listed above, it can be loaded using
```
SetDirectory[NotebookDirectory[]];
<<amplituhedronBoundaries`
```

After loading the package
- a local data directory called Data/ is created in the same directory of the notebook, and
- a private variable called `$cache` is set to `False`.

Having `$cache=False` means that the outputs of all functions are stored in the kernel's memory only and not to file. However, one can choose to have the outputs of some functions saved to file by setting `$cache=True`:
```
SetDirectory[NotebookDirectory[]];
$cache=True;
<<amplituhedronBoundaries`
```

Storing these outputs to file has the advantage that they will never need to be explicitly calculated again as they can be looked-up  almost immediately by the package. The disadvantage of choosing to store outputs to file is that the first-time evaluation of the above functions is longer.

## Prepared Data Files
A collection of data files containing the stored outputs for a number of important functions, evaluated for a number of examples has been prepared and is available on GitHub. These prepared files can be downloaded and added to the local data directory Data/ by executing the following command:
```
fetchData[]
```

## Directory Structure
Once the pre-requisite packages have been installed/downloaded, and the *amplituhedronBoundaries* package has been installed, the package has the following directory structure:

```bash
    .
    ├── positroids.m              # pre-requisite package developed by Jacob Bourjaily [arXiv:1212.6974] 
    └── amplituhedronBoundaries.m # main package                                  
```

After loading the *amplituhedronBoundaries* package for the first time, an additional directory called Data/ is created, resulting in the modified directory structure:

directory structure:

```bash
    .
    ├── positroids.m              # pre-requisite package developed by Jacob Bourjaily [arXiv:1212.6974] 
    ├── amplituhedronBoundaries.m # main package
    └── Data/                     # a directory for storing the outputs of long calcualtions to file
```
