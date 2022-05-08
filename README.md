Changes introduced for better results

1. Mutation function: The mutation function now chooses a column and changes the position of the queen in that column in such a way that it meets the following conditions: 
  ● The new position should not be the same as the initial position. 
  ● The new position should be the same as that of the neighbouring queens.
  
2. Change in cutoff-probability for mutation: The cutoff-probability for a mutation in the improved version of the algorithm is kept at 0.1 for the first 100 iterations. For all the remaining iterations, it is kept at 0.4, which is also the cutoff probability in the original version. This idea was taken from Simulated Annealing, wherein during the initial phases of the algorithm you try to move the current state to a neighbouring state with a very high probability, this was just a crude implementation of it.

3. Increasing population size, for the first 100 iterations: Increasing the population size by 5 in each iteration, till it reaches 100. After reaching 100, the population is again made 20, with the help of weighted probability; the weights being respective fitness values. This particular modification was made by keeping in mind the under-utilisation of space and the underlying motivation of the genetic algorithm, which is sexual reproduction. The population has been increased as follows: 
  ○ More than one offspring, as a result of the crossover: Instead of one crossover point, three have been taken, which when carefully permuted can give rise to multiple offsprings. In my version, I have produced 6 offsprings. This is done hoping to exploit the variation produced. 
  ○ These six offsprings are returned and the best one is chosen as the primary offspring which is all conditions added into the new population set. 
  ○ All the second-best offsprings in one iteration of the algorithm are taken, and five out of them are chosen with the help of weighted probability; the weights being their respective fitness values.Results* Both the algorithms converge. The naive one takes a significantly greater amount of time than the improved version.
  
4. Weights assigned to the population: In the naive version, the weight associated with a state was taken to be its fitness value (30000 - path_cost). In the improved version, weight for a state was taken to be the following: (30000 - (path_cost)) / ( 2 ^ (number of pairs of cities with no route)).

5. Change in cutoff-probability for mutation: The cutoff-probability for a mutation in the improved version of the algorithm is kept at 0.1 for the first 100 iterations. For all the remaining iterations, it is kept at 0.4, which is also the cutoff probability in the original version. This idea was taken from Simulated Annealing, wherein during the initial phases of the algorithm you try to move the current state to a neighbouring state with a very high probability, this was just a crude implementation of it.

6. Increasing population size, for the first 100 iterations: Increasing the population size by 5 in each iteration, till it reaches 100. After reaching 100, the population is again made 20, with the help of weighted probability. This particular modification was made by keeping in mind the under-utilisation of space and the underlying motivation of the genetic algorithm, which is sexual reproduction. The population has been increased as follows: 
 a. More than one offspring, as a result of the crossover: Instead of one crossover point, three have been taken, which when carefully permuted can give rise to multiple offsprings. In my version, I have produced four offsprings. This is done hoping to exploit the variation produced. 
 b. These four offsprings are returned and the best one is chosen as the primary offspring which is all conditions added into the new population set.
 c. All the second-best offsprings in one iteration of the algorithm are taken, and five out of them are chosen with the help of weighted probability. Results* Fitness function = 30000 - total_path_cost Penalty for a pair of cities with no path=1000 The naive algorithm converges quite rarely for 40000 iterations.
