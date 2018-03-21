---
layout: page
title: II - Applications
---

Les GANs ont beau être assez récent, les applications faites sont déjà très variées. Elles restent cependant du domainde de la recherche et ne sont pas encore déployées dans l'industrie, en partie à cause de la difficulté à gérer des données complexes comme les images de haute résolution. Voici donc un éventail non exhaustif d'applications possibles des GANs.

## Image enhancement

Un intérêt de la génération de données est de partir de données corrompues ou de mauvaise qualité et essayer de retrouver des données de bonne qualité. C'est ici ce que fait Mike Swarbrick en entraînant un *deep convolutional GANs* (dcGANs) qui part d'une image de basse résolution, trouve le vecteur latent qui lui correspond grâce à un réseau encodeur et génère une image de plus haute résolution à partir de ce vecteur latent. L'image doit donc correspondre à celle de basse résolution mais en ajoutant des détails. On peut voir ci-dessous les résultats obtenus (avec à chaque fois l'image de départ en HD à gauche, l'image en basse qualité au milieu et à droite l'image générée par le réseau à partir de l'image de basse qualité).

![image enhancement](/public/images/enhancement.png)
<em>Résultats du réseau d'image enhancement</em>

Le code est disponible dans [ce repo github](https://github.com/mikesj-public/dcgan-autoencoder).

## Image inpainting

Dans la même idée d'améliorer des données de mauvaise qualité, Yeh, Chen et al proposent un réseau permettant de compler les pixels manquant dans une image. On peut voir sur la figure des résultats ci-dessous qu'il suffit de très peu de pixels pour retrouver une image.

![image inpainting](/public/images/inpainting.png)
<em>Résultats du réseau d'image inpainting</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1607.07539.pdf).

## Face aging

On reste dans la modification d'image mais cette fois ce n'est pas simplement la qualité de l'image que l'on veut changer, on désire effectuer des transfirmations sémantiques sur l'image, donc sur le sens de ce qu'elle représente. Ici Antipov et al proposent un réseau capable de modifier l'âge d'un visage sur une image. Le réseau va donc trouver le vecteir latent correspondant à l'image de départ, puis l'utiliser en lui ajoutant une condition sur son âge pour générer une nouvelle image avec un âge différent. Le réseau vérifie également que l'image de sortie ne s'éloigne pas trop de l'image de départ afin de ne pas perdre l'identité du visage et générer un visage effectivement plus vieux mais non ressemblant.

![face aging](/public/images/aging.png)
<em>Résultats du réseau de face aging</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1702.01983v1.pdf).

## Image to image translation

Ici aussi il s'agit de modifier une caractéristque d'une image : Zhu, Park et al proposent un réseau capable de translater une image d'une catégorie à l'autre. Par exemple sur l'image ci-dessous on peut voir qu'un zèbre peut devenir un cheval et inversement, ou qu'une peinture de Monet peut devenir une photo et une photo peut devenir une peinture de Monet.

![image to image translation](/public/images/translation.png)
<em>Résultats du réseau d'image to image translation</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1703.10593.pdf).

## Pix2Pix

Pix2Pix est également un réseau d'image translation mais lui part d'image ne contenant que des contours et la transforme en image de la catégorie souhaitée comme une image de chat, de sac ou de façade.

![edges to cat](/public/images/cat.png)
<em>edges to cat</em>

![edges to bag](/public/images/bag.png)
<em>edges to bag</em>

![edges to facade](/public/images/facade.png)
<em>edges to facade</em>

Une [implémentation en ligne](https://affinelayer.com/pixsrv/) permet d'essayer de générer des images à partir de ses propres dessins.

## Text to image

Cette application a déjà été évoquée dans la partie précédente, il s'agit d'analyser le contenu sémantique d'un texte et de générer une image conditionnée par le contenu du texte.

![text to image translation](/public/images/text.png)
<em>Résultats du réseau de text to image translation</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1605.05396.pdf).

## Abstract reasoning diagram generation

Ici il s'agit de s'appuyer sur une suite de diagramme abstrait et de deviner le suivant. La suite présente donc une logique et le réseau doit tenir compte de cette logique pour générer un diagramme cohérent. Ce type d'application sur des séries temporelles est particulièrement intéressant car il ressemble à un problème très important dans l'intelligence artificielle et en particulier l'IA appliquée à la robotique : la prédiction d'un événement. En effet un robot qui interagit avec le monde devrait pouvoir anticiper les conséquences de ses actions avant de les entreprendre. Si au lieu de prendre en entrée des diagrammes abstraits, le réseau utilise les gestes d'un robot, le réseau pourrait alors prédire les trajectoire du robot et des agents extérieurs environnants et donc éviter des collisions par exemple. Ici sont utilisées des diagrammes mais c'est bien la capacité de raisonnement qui est apprise, et le fait justement que des diagrammes abstraits soient utilisées laisse à penser que ce procédé peut être utilisé sur bien d'autres éléments te situations.

![text to image translation](/public/images/diagram4.png)
![text to image translation](/public/images/diagram3.png)
![text to image translation](/public/images/diagram2.png)
![text to image translation](/public/images/diagram1.png)
<em>Résultats du réseau d'abstract reasoning diagram generation</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1609.09444.pdf).

## Video prediction

Dans le même esprit, Michael Mathieu, Camille Couprie et Yann LeCun proposent un réseau qui s'appuie sur le début d'une vidéo pour en prévoir la suite.

![video prediction](/public/images/video.png)
<em>Résultats du réseau de video prediction</em>

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1511.05440.pdf).

## Sketch retrieval

L'aspect non supervisé des GANs peut être mis à profit pour des tâches habituellement réservées aux réseaux classiques, ainsi Antonia Creswell et Anil Anthony Bharath ont utilisé des GANs pour détecter des marques de marchants sur des documents manuscrits. Ne disposant pas de base de données labélisée de ces marques manuscrites, ils ont enraîné un GANs à généré des marques et ont utilisé la représentation des marques apprise par ce réseau pour les détecter sur des images de documents.

![sketch retrieval](/public/images/sketch1.png)
<em>Illustration de la tâche de sketch retrieval</em>

![sketch retrieval](/public/images/sketch2.png)
<em>Résultats du réseau de sketch retrieval</em>


Sur l'image ci-dessus, pour chaque ligne le symbole dans le cadre violet est le symbole recherché et le reste de la ligne montre les 8 marques trouvées correspondant le plus.


L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1607.02748.pdf).

![ ](/public/images/white.png)
<p class="message">
NB : J'ai volontairement choisi des exemples graphiques car plus impressionnants et faciles à montrer au travers d'un écran mais les applications des GANs ne s'arrêtent pas aux images, aussi des GANs sont utilisés pour générer des sons, des molécules et toutes sortes de types de données.
</p>
