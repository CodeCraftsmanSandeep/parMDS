# parMDS
Effective Parallelization of the Vehicle Routing Problem, a GECCO 2023 Paper.


## Publication

**Effective Parallelization of the Vehicle Routing Problem**, 
<ins>Rajesh Pandian M </ins>, Somesh Singh, Rupesh Nasre. and N.S. Narayanaswamy,
*Genetic and Evolutionary Computation Conference* **(GECCO)**, 2023.
 [(Preprint)](https://mrprajesh.co.in/pdfs/CVRP_v4.pdf) 
 [(DOI)](#) [(Slides)](#) [(Video)](#) //TODO

## Requirements  

- parMDS: [NVIDIA's HPC SDK](https://developer.nvidia.com/hpc-sdk) . Has `nvc++`  compiler
- seqMDS: GCC 7+. Tested on GCC 9.3.1
- Should work on every Linux Distribution. Tested on Ubuntu 22.04.


## How to run

### Build and run executable
```
## To compile. Runs toy example on parMDS & seqMDS 

make

## To run the executable

./seqMDS.out toy.vrp [-round 0 or 1 DEFAULT:1 means round it!]
./parMDS.out toy.vrp [-nthreads <n> DEFAULT is 20] [-round 0 or 1 DEFAULT:1]


## An example
./parMDS.out inputs/Antwerp1.vrp -nthreads 16 -round 1
./seqMDS.out toy.vrp -round 0

## Output Description

//One line stats printed on std err whereas the solution on std out
inputs/Antwerp1.vrp Cost 556105 548740 518042 Time(seconds) 0.599911 2.18137 2.19818 parLimit 16 VALID    
Route #1: ..
Route #2: ..
...
Route #k:
Cost <val>

```

### Build and run paper's artifact

```
bash ./runRounds.sh
```


- Runs both seqMDS and parMDS on all 130 inputs using round conventions.
- Create .sol files for each instances.
- Create a folder `output*` and places all .log and .sol files.
- Create a time.txt file which contains Cost and Time of all instances.
- In addition to it, Cost and Time is printed on the terminal as well.



## Authors 
 * Rajesh Pandian M | https://mrprajesh.co.in
 * Somesh Singh     | https://ssomesh.github.io
 * Rupesh Nasre     | www.cse.iitm.ac.in/~rupesh
 * N.S.Narayanaswamy| www.cse.iitm.ac.in/~swamy


# LICENSE
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)
