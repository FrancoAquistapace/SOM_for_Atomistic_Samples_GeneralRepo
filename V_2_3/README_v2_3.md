# Self Organising Map for Clustering of Atomistic Samples - V.2.2
## Description
Self Organising Map (also known as Kohonen Network) implemented in Python for clustering of atomistic samples through unsupervised learning. The program allows the user to select wich per-atom quantities to use for training and application of the network, this quantities must be specified in the LAMMPS input file that is being analysed. The algorithm also requires the user to introduce some of the networks parameters:
- _f_: Fraction of the input data to be used when training the network, must be between 0 and 1.
- SIGMA: Maximum value of the _sigma_ function, present in the neighbourhood function.
- ETA: Maximum value of the _eta_ funtion, which acts as the learning rate of the network.
- N: Number of output neurons of the SOM, this is the number of groups the algorithm will use when classifying the atoms in the sample.

The input file must be inside the same folder as the main.py file. Furthermore, the input file passed to the algorithm must have the LAMMPS dump format, or at least have a line with the following format:

`ITEM: ATOMS id x y z feature_1 feature_2 ...`

Check the software report in the general repository for more information: https://github.com/rambo1309/SOM_for_Atomistic_Samples_GeneralRepo

## Dependencies:
This software is written in Python 3.8.8 and uses the following external libraries:
- NumPy 1.20.1
- Pandas 1.2.4

(Both packages come with the basic installation of Anaconda)

## What's new in V.2.3:
Optimized the training process through batched learning, so that the software can run faster. For big samples, the algorithm runs about 20% faster than V.2.2.

Check the report file in the repository for a complete description of the changes made in the software.

## Updates:
Currently working on giving the user the option to change the learning rate funtion, eta, with a few alternatives such as a power-law and an exponential decrease. 
