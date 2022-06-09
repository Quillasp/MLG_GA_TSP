---
date: 30 mai 2022
title: Genetic Algorithm
subtitle: The Burman Traveling Salesman Problem
author:
  - Hakim Balestrieri & Soulaymane Lamrani
---

# 6.1 Introduction

Le problème du voyageur de commerce est un problème d'optimisation où l'on veut
déterminer le chemin le plus court pour parcourir toutes les villes d'un circuit
en passant par chaque ville une et une seule fois. Pour résoudre ce problème,
nous allons utiliser un algorithme génétique pour minimiser la distance du
circuit, où un génome représente une liste de 14 villes.

Pour calculer la distance entre chaque ville, il faut prendre en compte que la
Terre est un sphéroïde aplati (oblate) et nous allons donc utiliser la
géodésique pour calculer la plus courte ligne droite entre deux points (dans
notre cas, de la Terre).

<page/>

# 6.2 Résultat

Le meilleur résultat que nous avons trouvé est le suivant:

`[0, 1, 13, 2, 3, 4, 5, 11, 6, 12, 7, 10, 8, 9]`

Cette séquence peut être à l'envers ou décalée d'une ville, mais il faut
toujours que le 11 soit suivi d'un 5 si on garde le même sens, ou d'un 6 si on
va dans l'autre. Sa distance est ≈ 3346.7619740386313 km.

Quant à savoir s'il s'agit de la meilleure solution, nous avons effectué
plusieurs tests, en changeant le taux de mutation, le nombre de générations
ainsi que la taille de la population et le meilleur résultat n'était pas plus
petit que la distance que nous avons trouvée (même en ayant comparé les
décimales). Il s'agit très probablement de la meilleure solution parmi les
<mi>/frac{1}{2}(n-1)! = /setdigitmode{6} /setdigitorder{1}
/digits{3.113.510.400}</mi> candidats (pour n = 14).

# 6.3 Fonction fitness

La fonction de fitness est la fonction utilisée pour calculer la distance du
circuit en utilisant la distance géodésique entre chaque ville.

`geopy.distance.geodesic` utilise le système géodésique mondiale WGS-84, qui est
composé d'un système de coordonnées, d'un ellipsoïde de référence et d'un géoïde
et est utilisé par le système de positionnement par satellite GPS, ce qui lui
permet d'avoir une approximation avec une marge d'erreur allant jusqu'à environ
0.5%.

<page/>

# 6.4 Solution

Nous nous sommes basé sur les différents exemples du laboratoire 7, notamment
`GA_evo-string.ipynb` qui utilise le sélecteur `GTournamentSelector` pour ne pas
utiliser la sélection par rang (rank selection).

Nous nous sommes aussi inspiré de l'exemple `pyevolve_ex12_tsp.py` pour le
calcul de la matrice des distances, de l'initializator pour générer des génomes
aléatoirement non répétitifs.

La solution est donc un chromosome qui représente une liste de ville. Par
exemple: `[4, 2, 8, 9, 5, 1, 3, 7, 6, 0, 10, 11, 12, 13]`.

# 6.5 Configuration de l'algorithme génétique

Paramètre        Configuration
--------------   --------------
Mutator          `G1DListMutatorSwap` qui va changer la position de deux villes dans le chromosome.
Crossover        `G1DListCrossoverEdge` pour avoir une séquence génétique non répétitive, particulièrement utilisé pour le TSP.
Initializator    Nous avons utilisé celui de l'exemple de l'exercice du TSP dans pyevolve, qui permet d'éviter les répétitions lors de l'initialisation des chromosomes.
Population size  Nous avons testé avec 100, puis nous l'avons augmenté pour constater que ça avait un impact négatif sur le résultat, puis nous voulions voir jusqu'où on pouvait descendre et 80 nous permettait, après quelques exécutions, de trouver notre meilleur résultat.
Selection        `GTournamentSelector` qui va sélectionner des chromosomes au hasard parmi la population et le gagnant de chaque tournoi pourra être reproduit.
Mutation rate    Nous avons testé avec des valeurs allant de 1% à 5% et nous sommes parvenu à de meilleur résultat avec 1%.
Crossover rate   Avec 100%, nous obtenions de bons résultats lors des différents tests.
Minimax          Toujours basé sur l'exercice, ceci permet de minimiser la fonction d'évaluation.
Generations      Nous avons testé avec des valeurs en 2000 et 100 pour parvenir avec un bon résultat avec 300.

# 6.6 Graphiques et explications

<page/>

# 6.7 Conclusion

L'utilisation de l'algorithme génétique pour résoudre le problème du voyageur de
commerce, un célèbre problème dans la théorie des graphes, nous a permis de
constater qu'une autre approche heuristique un peu plus proche du vivant nous
permettait de trouver une solution pour un problème qui ne semble pas facile à
répondre au premier abord.

S'il y a une chose à noter tout de même, c'est qu'il est nécessaire d'exécuter
le notebook plusieurs fois pour trouver la meilleure solution. Ou bien parfois
nous sommes chanceux et l'algorithme fonctionne du premier coup.
