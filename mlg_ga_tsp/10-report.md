---
date: 30 mai 2022
title: Genetic Algorithm
subtitle: The Burman Traveling Salesman Problem
author:
  - Hakim Balestrieri & Soulaymane Lamrani
---

# 6.1

Le problème du voyageur de commerce est un problème d'optimisation où l'on veut
déterminer le chemin le plus court pour parcourir toutes les villes d'un circuit
en passant par chaque ville une et une seule fois. Pour résoudre ce problème,
nous allons utiliser un algorithme génétique pour minimiser la distance du
circuit, où un génome représente une liste de 14 villes.

Pour calculer la distance entre chaque ville, il faut prendre en compte que la
Terre est un sphéroïde aplati et nous allons donc utiliser la géodésique pour
calculer la plus courte ligne droite entre deux points (dans notre cas, de la
Terre).
