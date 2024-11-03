# Lab 2 - Travelling salesman problem
https://www.wolframcloud.com/obj/giovanni.squillero/Published/Lab2-tsp.nb

This project implements two versions of an evolutionary algorithm (EA) to solve the Traveling Salesman Problem (TSP). The aim is to minimize the total travel distance across a set of cities such that each city is visited exactly once before returning to the starting point.

## Versions

The project includes two evolutionary algorithm versions that differ in speed and accuracy.

### 1. **Faster but Less Accurate Version**

This version uses a simpler and faster approach to solve the TSP. It prioritizes computation speed by using:

- **Population Size**: 200
- **Generations**: 200
- **Mutation Rate**: 0.2
- **Selection Method**: Tournament Selection, which selects parents based on a small random subset of the population.
- **Crossover Strategy**: Partially Mapped Crossover (PMX), which maintains relative city order and prevents duplicates in offspring.
- **Mutation Strategy**: Simple swap mutation, which randomly swaps two cities in a tour with a set mutation probability.

While this approach is computationally efficient, it may converge to suboptimal solutions due to limited selection diversity and simpler genetic operations.

### 2. **Slower but More Accurate Version**

This version adopts a more sophisticated approach to enhance solution quality at the expense of speed. Key differences include:

- **Population Size**: 200
- **Generations**: 1000
- **Mutation Rate**: 0.3 (adaptive)
- **Selection Method**: Roulette Wheel Selection based on fitness, which probabilistically selects parents, giving higher chances to better solutions while maintaining diversity.
- **Crossover Strategy**: Order Crossover (OX) resulting in more diverse and potentially higher-quality offspring.
- **Mutation Strategy**: Adaptive mutation rate, which decreases linearly over generations, allowing more exploration early on and focusing on exploitation as the solution stabilizes.
- **Elitism**: Preserves a fraction of the top-performing individuals (2%) in each generation, ensuring that the best solutions are retained.

This version is more likely to find optimal or near-optimal solutions due to its refined selection and genetic operations. However, it requires significantly more computation time due to more generations, and advanced operators.

## Credits

The crossover functions and the roulette wheel selection function were developed with the support from ChatGPT, which provided insights into advanced genetic operators to enhance solution accuracy.

