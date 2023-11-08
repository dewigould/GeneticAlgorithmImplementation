# GeneticAlgorithmImplementation

## Summary
In this repo we code up a simple example of a genetic algorithm (GA), first introduced in [Goldberg, David E. Genetic algorithms. pearson education India, 2013.]

GA's are a class of search/ optimization algorithms which seek to find the optimum set of parameters which maximise a so-called fitness function. They draw inspiration from Darwinian evolution or 'survival of the fittest'.

We implement a simple example, but note that there are many choices and modifications that can be made at various stages of the algorithm.

## The Algorithm
- First begin with an input which is a set of random parameters (this is the initial population). 
- We 'evolve' the population by considering which individuals are the 'fittest' (according to some fitness function), and only these individuals are allowed to 'reproduce'.
- 'Reproduction' means that only a certain subset of the population are kept to the next step, and in particular their parameters are mixed and somewhat randomized (reproduction and mutation).
- We implement 'binary tournament selection' - we take the N/2 strongest individuals (where N=size of initial population) and remove the rest.
- For reproduction, we use WAX crossover. This means that we take random pairs (parents), and each parent set produces 200 offspring. The 'genetic information' (parameters) of the offspring are a random combination of the parents' genetic information: We select a random number r = [0,1], and then assign information $a_i = r a_i^{(1)} + (1-r) a_i ^{(2)}$, where $a_i^{(j)}$ is the ith genetic information of the jth parent
- We then run tournament selection amongst the children (6-fold). This means we run many tournaments of 6 random children, and the children with the most 'wins' after some set of tournaments are allowed to survive.

## Validation
- We test this implementation on various simple 2-parameter functions where we can explicitly compute the minima. The model is able to find these minima to high accuracy within 3 time periods!