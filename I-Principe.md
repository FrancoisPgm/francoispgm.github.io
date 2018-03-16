---
layout: page
title: I - Principe
---

Comme leur nom l'indique, les GANs sont des **réseaux**, **génératifs** et **adversaires**.

## Réseaux

Les GANs utilisant des réseaux de neurones, quelques rappels sur le fonctionnement de tels réseaux semblent de mise.
Les réseaux de neurones sont des opérateurs composés de couches successives de neurones. Chaque neurone possède des entrées, sur lesquelles il applique une opération simple dépendant de ses paramètres (ses poids) pour calculer une sortie. On part donc de notre donnée de départ, que l'ont donne en entrée aux neurones de la première couche, qui calculent chacun une sortie en fonction de leurs poids respectifs. Toutes les sorties de la première couche sont alors données en entrées de la seconde couche, qui produit également une sortie, et ainsi de suite jusqu'à obtenir la sortie finale. En comparant cette sortie à la sortie attendue, on peut utiliser cette erreur pour modifier les paramètres de tous les neurones du réseaux (par la méthode de rétropropagation du gradient). En faisant cela un grand nombre de fois sur de nombreux exemples, on arrive finalement à trouver un ensemble de paramètres qui permettent au réseau de donner la bonne sortie dans la majorité des cas.

Les réseaux de neurones correspondent donc à des fonctions paramétrables, qui pour une entrée **X** donnent une sortie **Y**. Le succès des réseaux de neurones depuis 2012 repose principalement sur leur capacité à apprendre à classifier des données. Ainsi l'engouement pour le deep learning (i.e. l'utilisation de réseaux profonds à plusieurs couches) a pour point de départ les résultats surprenants de réseaux profonds lors de la compétition de classification d'images ImageNet Large Scale Visual Recognition Challenge (ILSVRC). Depuis l'usage le plus courant de tels réseaux a été la classifications de données. On prend comme **X** une donnée à classer, par exemple une image, et on obtient en **Y** la classe de la donnée, par exemple si l'image représente un mouton ou non. Ce fonctionnement se révèle assez efficace mais nécessite un processus d'apprentissage supervisé. Cela signifie que le réseau nécessite un grand nombre d'exemples pour lesquels la réponse attendue a préalablement été déterminée (le plus souvent par un opérateur humain). Ainsi pour apprendre à notre réseau à reconnaître les images de moutons, il faudra disposer d'une importante collection d'exemples d'images annotées "mouton" ou "pas mouton".

## Génératifs

Les GANs sont donc des réseaux, mais des réseaux génératifs. Contrairement aux réseaux classifieurs décrits ci-dessus, les réseaux génératifs ne prennent pas en entrée **X** une donnée mais en produise une dans leur sortie **Y**.

*image*




## Adversaires
