This code is associated with the paper from Trakoshiset al., "Intrinsic excitation-inhibition imbalance affects medial prefrontal cortex differently in autistic men versus women". eLife, 2020. http://doi.org/10.7554/eLife.55684

# Instructions to simulate the LIF network model 

## Building the neuron model 

Instructions to compile the neuron model in NEST are based on the tutorial about “Writing an extension module” (https://nest.github.io/nest-simulator/extension_modules). 

1 - Define the environment variable 'NEST_INSTALL_DIR' to contain the path to which you have installed NEST, e.g. using bash:

export NEST_INSTALL_DIR=/Users/pablo/NEST/ins

2 - Create a build directory in the folder 'neuron_model':

cd neuron_model
mkdir build
cd build

3 - The configure process uses the script 'nest-config' to find out where NEST is installed, where the source code resides, and which compiler options were used for compiling NEST. If 'nest-config' is not in your path, you need to provided it explicitly like this (don't forget to add '..' at the end):

cmake -Dwith-nest=${NEST_INSTALL_DIR}/bin/nest-config ..

4 - Compile:

make

make install

It might be also necessary to update the LD_LIBRARY_PATH, e.g.:

export LD_LIBRARY_PATH=${NEST_INSTALL_DIR}/lib/python2.7/site-packages/nest:$LD_LIBRARY_PATH




## Running a simulation 

Simulation scripts are in folder 'network/analysis'. Adjust the simulation parameters in the script and execute it using the Python interpreter, e.g.:

python save_results_1.py
