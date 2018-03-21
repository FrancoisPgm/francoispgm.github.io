---
layout: page
title: II - Applications
---

Les GANs ont beau être assez récent, les applications faites sont déjà très variées. Elles restent cependant du domainde de la recherche et ne sont pas encore déployées dans l'industrie, en partie à cause de la difficulté à gérer des données complexes comme les images de haute résolution. Voici donc un éventail d'applications possibles des GANs.

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

L'article présentant le réseau est disponible [ici](https://arxiv.org/pdf/1607.07539.pdf).

## Image to image translation
