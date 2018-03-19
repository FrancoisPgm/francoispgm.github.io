---
layout: page
title: I - Principe
---

Comme leur nom l'indique, les GANs sont des **réseaux**, **génératifs** et **adversaires**.

## Réseaux

Les GANs utilisant des réseaux de neurones, quelques rappels sur le fonctionnement de tels réseaux semblent de mise.
Les réseaux de neurones sont des opérateurs composés de couches successives de neurones. Chaque neurone possède des entrées, sur lesquelles il applique une opération simple dépendant de ses paramètres (ses poids) pour calculer une sortie. On part donc de notre donnée de départ, que l'ont donne en entrée aux neurones de la première couche, qui calculent chacun une sortie en fonction de leurs poids respectifs. Toutes les sorties de la première couche sont alors données en entrées de la seconde couche, qui produit également une sortie, et ainsi de suite jusqu'à obtenir la sortie finale. En comparant cette sortie à la sortie attendue, on peut utiliser cette erreur pour modifier les paramètres de tous les neurones du réseaux (par la méthode de rétropropagation du gradient). En faisant cela un grand nombre de fois sur de nombreux exemples, on arrive finalement à trouver un ensemble de paramètres qui permettent au réseau de donner la bonne sortie dans la majorité des cas.

![Reseau simple](/public/images/reseau_classifieur.png)
<em>Réseau classifieur</em>

Les réseaux de neurones correspondent donc à des fonctions paramétrables, qui pour une entrée **X** donnent une sortie **Y**. Le succès des réseaux de neurones depuis 2012 repose principalement sur leur capacité à apprendre à classifier des données. Ainsi l'engouement pour le deep learning (i.e. l'utilisation de réseaux profonds à plusieurs couches) a pour point de départ les résultats surprenants de réseaux profonds lors de la compétition de classification d'images ImageNet Large Scale Visual Recognition Challenge (ILSVRC). Depuis l'usage le plus courant de tels réseaux a été la classifications de données. On prend comme **X** une donnée à classer, par exemple une image, et on obtient en **Y** la classe de la donnée, par exemple si l'image représente un mouton ou non. Ce fonctionnement se révèle assez efficace mais nécessite un processus d'apprentissage supervisé. Cela signifie que le réseau nécessite un grand nombre d'exemples pour lesquels la réponse attendue a préalablement été déterminée (le plus souvent par un opérateur humain). Ainsi pour apprendre à notre réseau à reconnaître les images de moutons, il faudra disposer d'une importante collection d'exemples d'images annotées "mouton" ou "pas mouton".


## Génératifs

Les GANs sont donc des réseaux, mais des réseaux génératifs. Contrairement aux réseaux classifieurs décrits ci-dessus, les réseaux génératifs ne prennent pas en entrée **X** une donnée mais en produise une dans leur sortie **Y**. Que leur donne-t-on donc comme **X** ? Pour comprendre cela on va regarder un autre type d'architecture mettant en jeu un réseau génératif : les auto-encodeurs.

Les auto-encodeurs sont composés d'un réseau descriptif semblable à un réseau classifieur, et un réseau génératif. Le but du premier est de prendre en entrée une donnée, par exemple une image, et de donner en sortie un descripteur de cette image, c'est-à-dire une transformation de l'image dans ce qu'on appelle le *latent space*. Cette projection de l'image dans le *latent space* a pour particularité d'être de dimension bien inférieure à l'image de départ. Elle ne doit donc concerver que les informations importantes dérivant l'image. Par exemple si l'image représente un visage, on va passer d'une donnée de départ très riche : la couleur de chacun des pixels, à une description plus petite mais plus évocatrice : la position des yeux, du nez, de la bouche, la couleur des cheveux... Le second réseau de l'auto-encodeur, le réseau génératif donc, prend en entrée la description produite par le réseau descripteur et va former en sortie une reconstruction de l'image d'origine. Le réseau ne génère donc pas à partir de rien, il prend en entrée un vecteur **Z** qui correspond à la projection de l'image dans le *latent space*, à savoir sa description par ses caractéristiques principales ou *features*.

![Auto-encodeur](/public/images/auto_encodeur.png)
<em>Auto-encodeur</em>

L'objectif de l'auto-encodeur est donc de trouver un encodage, une projection dans un *latent space*, qui soit suffisamment pertinent pour permettre de reconstituer l'image par la suite. Pour la génération, on part donc d'un vecteur du *latent space*. C'est également le cas pour la génération chez les GANs, sauf que cette fois on ne dispose pas du réseau descripteur. On va donc simplement donner un vecteur du *latent space* aléatoirement généré en entrée de notre réseau générateur.

<p class="message">
  <b>Latent space</b> : un espace vectoriel représentant les <i>features</i> des données originales. Il convient de remarquer que ce n'est pas l'espace vectoriel qui porte lui-même les notions de <i>features</i> mais les transformations utilisées pour passer de l'espace de départ au <i>latent space</i> et inversement. En prenant l'exemple de la génération d'images de chats, cela signifie que le choix de l'espace vectoriel (nombre de dimension, norme...) ne correspond pas au choix des <i>features</i> qui seront utilisées par le réseau de neurones. On ne choisit pas à l'avance que telle dimension définit la taille des oreilles et telle autre la couleur du pelage. Ces choix de <i>features</i> vont émerger avec l'apprentissage du réseau. C'est le réseau générateur qui par son processus d'apprentissage va décider d'interpréter telle dimension comme représentant telle caractéristique d'image de chat.
</p>

## Adversaires

Notre architecture de GANs est donc constituée d'un réseau génératif **G**, produisant des données à partir d'un vecteur aléatoire du *latent space* et d'un réseau classifieur **D** prenant en entrée une donnée et en sortie nous donne un label correspondant à la classe de l'objet. Il nous reste à voir le processus d'apprentissage, et c'est là que l'adjectif *adversarial* va prendre sens. En effet le principe innovant des GANs réside dans le fait que l'apprentissage se fait en enraînant deux réseaux simultanément dans un *zero sum game* ou jeu à somme nulle. **G** et **D** sont donc adversaires dans un jeu où les gains de l'un sont la perte de l'autre. Le but du jeu va être de différencier les données produites par **G** de données déjà existantes venant d'une base de données. **D** aura donc pour labels *vrai* et *générée*, et devra attribuer correctement ces labels tandis que **G** aura pour objectif de faire en sorte que **D** se trompe dans sa clasification.

![Schéma du processus d'apprentissage](/public/images/schema_appr.png)
<em>Schéma du processus d'apprentissage</em>

Ce jeu peut être vu comme l'affrontement d'un faussaire et d'un détective. Le faussaire génère de la fausse monnaie en essayant tromper le détective tandis que ce dernier essaie de distinguer les faux billets des vrais. 
