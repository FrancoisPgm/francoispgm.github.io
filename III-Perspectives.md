---
layout: page
title: III - Perspectives
---

Les GANs permettent de nouvelles utilisations des réseaux de neurones qui sont appelées à modifier notre rapport à l'IA et même à l'information en général. Cela soulève d'une part des promesses peut-être trop enthousiastes et des menaces peut-être trop pessimistes. Si mes propos ne seront pas ici toujours très mesurés, leur objectif n'est pas de dépeindre de façon réaliste le futur que nous réserve les progrès du machine learning, mais de donner des pistes de réflexion sur les enjeux positifs ou négatifs qu'impliquent une telle technologie.

## Génération de données

La principale utilisation des GANs est dans leur nom : générer des données. La première question posée par une éventuelle utilisation massive de GANs très performants sera alors : quel rapport entretenir avec les données et donc l'information en général.
En effet pouvoir générer des données artificielles mais réalistes sous tous les aspects nous ramène à l'analogie faite pour décrire le fonctionnement des GANs, à savoir l'analogie du faussaire. Si on ne s'était intéressé à cette métaphore uniquement pour expliquer le principe des GANs, elle se révèle égalemnt pertinente pour décrire l'utilisation des GANs. Comment croire une information, ou un document quand n'importe qui possède des outils pour devenir un faussaire générant de fausses informations et de faux documents. Alors que l'on s'appuie de plus en plus massivement sur les données numériques dans tous les domaines, ces dernières semblent également deviennent de moins en moins fiables. L'image d'un avenir où la notion de vérité disparaît complètement, où n'importe qui peut être accusé à tort d'un crime à caues d'une vidéo de surveillance générée peut alors doucement se dessiner. Toutefois elle est à relativiser car cette problématique n'est pas nouvelle, cela fait déjà un moment que des logiciels de retouches permettent de réaliser des images photoréalistes de n'importe quoi. Effectivement cela prend une toute autre ampleur avec les GANs car cela automatise le processus et donc change l'échelle du phénomène. Cependant si l'IA devient suffisamment forte pour tromper les humains sur la génération de données, on peut imaginer qu'elle devienne également plus forte dans la reconnaissance de fausses images et qu'en augmentant le problème elle participe en commune mesure à sa solution. A l'inverse on peut arguer que le problème de vérité de l'information est une question qui repose plus sur des notions psychologiques et sociales comme la confiance et la notoriété, et que les considérations techniques ne sont que périphériques au problème qui ne peut être réglé que par les sciences sociales.

<div  align="center">
<img src="/public/images/data.jpg" alt="data" style="width: 360px;"/>
</div>

Une fois ces considérations morales passées, on peut s'attarder sur une opportunité plus techniques qu'offrent la possibilité de générer des données de façon quasi illimitée. Cette opportunité repose sur le besoin de données que présentent tout procédé de machine learning. Un facteur limitant du développement d'algorithme toujours plus intelligent étant la quantité de données disponibles, on peut imaginer repousser la limite en utilisant les données générées par des GANs pour entraîner d'autres réseaux. Ainsi à partir d'une base de données on pourra entrainer un GANs qui complètera la base avec autant de nouvelles données similaires nécessaires et ainsi on multiplie les données disponibles pour entraîner n'importe quel type de réseau. Cela annonce alors une éventuelle accélération exponentielle des performances des réseaux.

## La compréhension des machines

On a évoqué dans la partie *Principe* la possibilité pour les GANs de développer implicitement une arithmétiques de concepts sémantiques sur les données manipulées. On peut imaginer que cela représente un pas vers une compréhension du sens des données. D'autant plus qu'en combinant et reliant plusieurs *latent spaces* de réseaux générant des données dans des espaces de données différents, par exemple des mots des images et des sons, on peut alors lier les concepts entre eux et avoir une représentation plus complètes des concepts. Par exemple on peut imaginer un réseau sachant associer l'image d'un chat au mot chat et aux sons des chats. Une transformation sur un des domaines, comme transformer l'image du chat en chaton pourrait alors entraîner le changement du mot et des sons associés. On peut alors imaginer une IA capables de consistance et cohérence sémantique à travers plusieurs modes de représentations, ce qui serait un premier pas vers une IA dotée de sens commun.

<div  align="center">
<img src="/public/images/metro.jpg" alt="IA_common_sens" style="width: 360px;"/>
</div>

Un autre pas vers le sens commun serait de créer des IA capables d'anticiper des événements, de pouvoir extrapoler les observations passées pour imaginer le déroulement futur d'une situation. Cela rejoint les applications des GANs pour la prédiction vidéo ou de suites de diagrammes logiques. Si ces applications peuvent être poussée et généralisée à la prédiction du futur proche de l'environnement de la machine cela permettrait de simuler une sorte de sens commun. Cela serait particulièrement utile pour la fiabilité des machines. En effet la capacité d'imaginer la suite d'événements sans nécessairement avoir vécu la situation exacte permet aux machines d'anticiper des accidents sans avoir eu à les causer auparavant. Par exemple on voudrait bien qu'une voiture autonome puisse se dire toute seule que foncer dans le ravin est une mauvaise idée, et ce sans devoir reposer sur l'expérience de s'être déjà jetée dans le ravin par le passé. Le fait de pouvoir imaginer ce qu'il se passe si telle ou telle action est effectuée est ainsi un point primordial dans la conception d'IA présentant des comportements se réclamant comme témoignant un sens commun.  

## Le rapport des hommes aux machines

Il est maintenant temps de développer le sous-titre de ce site : "*quand les machines imaginent*". On a jusque là parlé simplement de génération de données, et il est vrai que "*génération de données selon une distribution*" ne fait pas spécialement penser aux profondeurs et nuances de l'imagination humaine. Pourtant il s'agit bien de créer quelque chose qui n'existait pas avant sans s'appuyer sur une donnée extérieure. De plus le réseau génératif ne voit jamais les données réelles et ne s'en inspire donc pas directement, il ne s'appuie que sur les retours du réseau discriminant. Ainsi un réseau générant une image de chat n'a jamais vu de chat. Il semble alors raisonnable de dire qu'il imagine un chat. De plus par des générations conditionnelles, un réseau peut générer des images totalement innovantes, contenant des combinaisons de concepts n'existant nulle part dans le monde réel. Il semble donc bien que les GANs donnnent accès aux machines à l'imagination, capacité qui pourtant jusque là semblait faire partie des caractéristiques profondément humaines, et liée si étroitement à la conscience qu'elle était hors de portée des froides machines.

<div  align="center">
<img src="/public/images/rondo_veneziano.jpg" alt="IA_musician" style="width: 440px;"/>
</div>

Cette incursion des machines au sein des caractéristiques "propres à l'humain" peut donc être perçue comme un argument en faveur de la thèse matérialiste selon laquelle la conscience est un phénomène ne reposant que sur des principes physique. Certains voient alors dans les IA capables de générer des peintures ou des mélodies non sans intérêt artistique, les prémices de consciences artificielles qui éventuellement finiront par réfléchir et dialoguer avec les hommes sur un pied d'égalité intellectuelle.

Se pourrait-il que les GANs soient une étape vers la création d'une conscience artificielle, et que grâce à eux on sache un jour si les androïdes rêvent de moutons électriques ?

<div  align="center">
<img src="/public/images/electric_sheep.jpg" alt="electric_sheep" style="width: 330px;"/>
</div>
