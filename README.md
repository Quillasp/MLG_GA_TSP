# The Burman Traveling Salesman Problem (TSP)

The travelling salesman problem (TSP) asks the following question: Given a list
of cities and the distances between each pair of cities, what is the shortest
possible route that visits each city exactly once and returns to the origin
city? It is an NP-hard problem in combinatorial optimization, important in
operations research and theoretical computer science [Wikipedia].

The objective of this exercise is to solve the TSP problem for a set of 14
cities in Burma, officially the Republic of the Union of Myanmar. The following
vectors give the GPS position of each city.

   LAT = [16.47, 16.47, 20.09, 22.39, 25.23, 22.00, 20.47,
          17.20, 16.30, 14.05, 16.53, 21.52, 19.41, 20.09]

   LON = [96.10, 94.44, 92.54, 93.37, 97.24, 96.05, 97.02,
          96.29, 97.38, 98.12, 97.38, 95.59, 97.13, 94.55]


Consider that the distance between two cities is not the Euclidean distance. You
have to consider that they are points on the surface of the Earth, which can be
considered to be an oblate spheroid.

In this application, we are interested in getting the best solution as possible
(e.g., the shortest path). However, notice that we do not know the optimal
solution beforehand, so you have to try the GA several times to check if there
is a better solution. In this experiment we are not evaluating the capabilities
of the Genetic Algorithm, so you do not have to test it using different
parameters (mutation and crossover rates, population, etc) to show this, but you
may need to try different parameters to be able to find a better solution to
your problem. I hope this is clear :smile:

# Report

Page 1: Provide a title, your names, school name, course, date 

6.1. Briefly explain the problem and your solution (1/2 page).

Page 2:

6.2 Provide the better route you found and the shortest path in kilometers. Is
it the optimal shortest path ? explain.

6.3 Describe your fitness function

Page 3:

6.4 Explain the way you encoded the solution, give a chromosome example.

6.5 Provide the configuration of the GA you finally used to find your better
results: mutation, crossover, population size, type of selection, mutation,
crossover used, number of generations. Describe the methodology or experiments
performed in order to get your better results.

Page 4:

6.6 Provide relevant plots of your experiments and explanations.

Page 5:

6.7 Conclusions (1/2 page) + [optional] eventual supplementary comments (1/2 page) 

Upload to cyberlearn your zip file named name.zip including your notebook and
the report in PDF.
