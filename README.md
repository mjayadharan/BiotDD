
# [Multisacale Mortar Finite Element Implementation for Biot system(BIOTDD-MMMFE)](https://arxiv.org/abs/2010.15353)
Fluid flow simulator based on Biot system of poroelasticity, using Mixed Finite Element method with domain decomposotion techniques to improve computational efficiency.  
![ezgif com-gif-maker (3)](https://user-images.githubusercontent.com/35903705/97790134-68adc980-1b9c-11eb-9431-ec5bfcc6da36.gif) 

  
__Note__: If you use the code for research or development, please cite the following original publications: [Domain decomposition and partitioning methods for mixed finite element discretizations of the Biot system of poroelasticity M Jayadharan, E Khattatov, I Yotov Computational Geosciences 25, 1919-1938](https://link.springer.com/article/10.1007/s10596-021-10091-w)
and
[Multiscale mortar mixed finite element methods for the Biot system of poroelasticity M Jayadharan, I Yotov arXiv preprint arXiv:2211.02949](https://arxiv.org/abs/2211.02949)

__Limited user manual. Please visit the similar [space-time DD project](https://github.com/mjayadharan/MMMFE-ST-DD) to see a detailed documentaion on how to install and run the simulator.__  
Code developed to simulate time-dependent diffusion problem using Multiscale Mortar Mixed Finite Elements(MMMFE). Model can be easily adapted to simulate other fluid flow models based on linear PDEs. Sub-domain solves are done in parallel across different processors using MPI. Computed solutions are outputted and visualized on a global space-time grid in the .vtk and .vtu formats. 
### Note:
- The simulator is written using deal.ii FE package which is based on C++.  
-  All instructions are with respect to a terminal in linux/mac. Please use the ubuntu sub-system if you are using windows 10. A good installation guide for the linux sub-system can be found [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10).
- Image/animation processing and visualization can be done using paraview. Installation guide can be found [here.](https://www.paraview.org/Wiki/ParaView:Build_And_Install)

## Authors
-----------
Manu Jayadharan, Department of Mathematics at University of Pittsburgh, 9/17/2019

email: [manu.jayadharan@gmail.com](mailto:manu.jayadharan@gmail.com), [manu.jayadharan@pitt.edu](mailto:manu.jayadharan@pitt.edu)  
[researchgate link](https://www.researchgate.net/profile/Manu_Jayadharan)  
[linkedin profile](https://www.linkedin.com/in/manu-jayadharan/)  
 
Eldar Khattatov, Department of Mathematics at University of Pittsburgh, 2018  


## deal.ii 9.5.2 requirement (latest at the time)
---------------------------------------
Need deal.ii configured with mpi  to compile and run the simulations. Latest version of dealii can be found at : [https://www.dealii.org/download.html](https://www.dealii.org/download.html)

**deal.ii installation instruction:** Follow readme file to install latest version of deal.ii with `-DDEAL_II_WITH_MPI=ON` and .. -DCMAKE_PREFIX_PATH=path_to_mpi_lib flags to cmake. 


## Compilation instructions.
-------------------------------------------
`cmake -DDEAL_II_DIR=/path to dealii installation folder/ .` from the main directory

`make release` for faster compilations

`make debug` for more careful compilations with warnings

`mpirun -n 'j' BiotDD` where j is the number of subdomains(processses)

**Please contact the author for further instructions.**

## Quick start guide for the simulator.
-------------------------------------
* Most of the parameters including number of refinements, mortar_degree, max_number of gmres iterations, final_time, subdomain mesh size
ratio etc are fed to the executable file DarcyVT using parameter.txt in the main folder. This file can simply be modified
without recompiling the program.  

