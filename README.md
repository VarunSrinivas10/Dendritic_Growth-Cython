# Dendritic_Growth-Cython
This repository contains a Cython implementation for dendritic crystal growth as proposed by Kobayashi in "Modeling and numerical simulations of dendritic crystal growth"

Requirements:
Numpy and Cython

To run the simulation:
  1. Place all three files in the same directory
  2. Run the following command: python3 setup.py build_ext --inplace 
  3. This creates a CPython module of the func_body.pyx file, and only needs to be done once or if changes are made to the func_body.pyx file
  4. Run the simulation using: python3 run.py

The following parameters can be modified in the run.py file:
  1. kappa - dimensionless latent heat
  2. theta0 - orientation
  3. seed - initial system configurtion

The following parameters can be modified in the func_body.pyx file:
  1. dx,dy,dt - spatial and temporal discretisation constants
  2. tau, gamma, alpha, delta, epsilonb
  3. teq - equilibrium temperature
  4. amp_noise - noise term constant
Note: After modifying the func_body.pyx file, build the CPython module again using step (2)

Every 100th frame is stored in an array and saved as a .npy file. The files are named Phase.npy and Temp.npy, corresponding to the phase and temperature fields. The frequency of the frames being stored can be modified in the func_body.pyx file and by changing the size of the temporary A and B arrays in the run.py file.
