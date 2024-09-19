---
title: "Agile tour Lyon 2022 - Vers une euphorie sans fin"
summary: "Retour d'expérience sur la création d'une équipe Produit au sein d'une entreprise historiquement organisée pour réaliser des projets."
description: "Retour d'expérience sur la création d'une équipe Produit au sein d'une entreprise historiquement organisée pour réaliser des projets."
categories: ["talks"]
tags: ["content", "agile", "rex"]
# externalUrl: "https://nunocoracao.com/posts/202310-blowfish-tutorial/"
date: 2022-06-11
draft: false
showauthor: true
# authors:
#   - nunocoracao
---

![Agile Tour Lyon 2022](/img/conference_agile-tour-lyon-2022-800x450.png)

Avez-vous déjà construit une équipe Agile, la toute première d'une grande organisation? Ou peut-être y avez-vous déjà participé ou encore tout simplement regardé, plein d'espoir pour les changements que cela allait vous apporter?

L'euphorie des débuts se heurte souvent à la structure de l'organisation, freinant l'ardeur des plus volontaires et laissant place à une certaine lassitude. Et pourtant, tout espoir n'est pas perdu! L'histoire ne se répétera pas sans fin. 

Je vous partage une expérience de création d'équipe Produit au sein d'une entreprise historiquement organisée pour réaliser des projets. Nous nous sommes appuyés notamment sur les concepts de Team Topologies pour faire émerger la responsabilité du produit, garantir un découplage fort vis à vis des autres produits / services, et limiter la charge cognitive de l'équipe.

## Le contexte

Une entreprise suisse du secteur de l'énergie, historiquement organisée pour réaliser des projets, a décidé de réaliser une plateforme de télérelève multi-fluides (eau, gaz, électricité, thermique) afin que ses clients puissent récupérer et ainsi diminuer la consommation relevée sur leurs compteurs. 

**Des décisions courageuses sont prises**

Le délai de mise à disposition de cette plateforme à ses clients n'est que de 3 mois alors qu'en moyenne l'entreprise délivre ce type de solution en 5 mois. L'entreprise souhaitait profiter de ce nouveau projet pour acquérir des connaissances dans le développement de solution "Cloud native". 

Il fallait donc sortir des sentiers battus. Pour faciliter l'apprentissage et l'expérimentation, une équipe multidisciplinaire a été construite spécifiquement pour ce projet. Cette dernière a ensuite pu mettre en place le cadre de travail favorisant les approches empiriques. L'autorisation à déroger à certaines règles d'entreprise a été rapidement accordée. Un suivi hebdomadaire de la direction a été instauré pour faire tomber les contraintes organisationnelles auxquelles l'équipe allait devoir faire face. Tout se mettait en place pour autonomiser le plus possible l'équipe et lui permettre de relever le challenge technique et organisationnel.

## La composition d'équipe

![Equipe Produit](/img/equipe-800x400.png)
Pour la première fois l'entreprise a mis en place une équipe multidisciplinaire, composé de:
- **un ingénieur électricien**, coordonnant l'installation des capteurs et la gestion du stock;
- **un ingénieur télécom**, en charge de la communication des données entre les capteurs et la plateforme web;
- **trois ingénieurs développeurs** full stack .Net, en charge du développement de la plateforme Web;
- **un ingénieur DevOps** en charge de l'intégration et du déploiement de la plateforme Web sur Azure;
- **un ingénieur architecte** logiciel;
- **un responsable produit**, en charge de la vision et de la stratégie de la plateforme Web.

Certains membres de cette équipe n'ont malheureusement pas pu être dédiés à 100%. Fort heureusement, nous avons obtenu de la direction :
- la limitation de l'affectation de ces personnes à deux projets au maximum dont le nôtre;
- la capacité de décider ensemble des jours où l'on pouvait travailler ensemble.

## Le Minimum Viable Product

L'incertitude dans la manière d'aborder les contraintes du développement sur le cloud et du délai de 3 mois pour délivrer de la valeur aux clients a forcé l'équipe à se concentrer la définition du "Minimum Viable Product". Le premier chantier a donc porté sur l'identification du flux de valeur, ce qui a permis de sélectionner les activités obligatoires et d'identifier les services de l'entreprise, réutilisables sans complexité pour l'équipe.

Ainsi, l'équipe a décidé :
- de construire peu d'outils d'exploitation au vu du faible volume de capteurs à gérer dans un premier temps (<100);
- de minimiser le travail sur l'ergonomie des activités de gestion de la configuration et d'ajout de capteurs dans la plateformeen ne fournissant le service que sous forme de lignes de commandes;
- d'écarter pour le moment tous les sujets d'intégration complexes avec les services de l'entreprise (gestion des commandes et du stock de capteurs).

Comme souvent au début des projets, l'équipe pensait qu'après avoir pris toutes les décisions difficiles et défini les contours du produit, la réalisation de la plateforme n'allait être qu'un long fleuve tranquille. Il en fut tout autrement...

![La dure réalité du terrain](/img/conference_agile-tour-lyon-2022_realisation_mvp-800x400.png)

Habituée à avoir à disposition une infrastructure dans ses locaux, l'équipe ne portait pas attention au coût de sa solution sur le cloud. Elle montait des environnements multitples (dev, qual, prod) qui fonctionnait tout le temps, avec un important volume de données pour lesquelles aucune contrainte sur leur durée de vie n'a été prise en compte.

La réalisation du flux de données "Device to cloud" a été simple à mettre en oeuvre. Le flux opposé "Cloud to device" a été vraiment problématique pour l'équipe.

Une interruption de services sur les capteurs de test a été provoqué par un changement de structure de la base de données mal validé. Cela a permis d'identifier un manque dans la définition de nos besoins pour exploiter la solution sereinement: la capacité à rejouer des événements du passé.

Fort heureusement, pour passer ces difficultés, l'équipe a pu s'appuyer sur:
- une approche empirique centrée sur la valeur;
- une solidarité et un esprit d'équipe construits petit à petit;
- un management à l'écoute et pro-actif;
- une approche orientée solution plutôt qu'orientée problème.

## La 1ère livraison au client

Classiquement, comme pour toute organisation orientée projet, l'équipe a été évaluée sur sa capacité à atteindre les objectifs intrinsèques, à savoir "être dans les délais", "périmètre fonctionnel atteint" et "dans les budgets!". L'équipe a répondu présente en atteignant ces objectifs "classiques". Cependant, elle s'était aussi fixée d'autres objectifs, extrinsèques ceux-là, précurseurs d'une approche orientée produit:
- la satisfaction des clients;
- la satisfaction de la direction concernant l'efficacité d'une équipe transverse multicompétentes;
- la satisfaction de l'équipe sur le travail réalisé et les apprentissages effectués (techniques, fonctionnels et humains);
- la mise à l'échelle du service offert par la plateforme (au niveau technique comme au niveau exploitation).

![Première livraison](/img/conference_agile-tour-lyon-2022_1erelivraison_800x400.png)

Mise à part ce dernier point, tous les objectifs de l'équipe ont été remplis.

## Un service est né avec de nouveaux challenges

Un projet se termine. Il est temps de disloquer l'équipe pour que les collaborateurs soient affectés à d'autres projets! Combien de fois avez-vous constater cela dans des organisations orientées projet? Trop souvent pour ma part. Fort heureusement, comme le comité de direction suivait de près l'équipe et que le projet était un véritable succès, ils ont rapidement accepter de lancer une nouvelle expérimentation: "You build it, you run it!"

![Nouveaux challenges](/img/conference_agile-tour-lyon-2022_nouveaux-challenges_800x400.png)

Un accord a été trouvé pour garder une équipe stable pendant un an, financée à 60% par les revenus qu'elle générait, et 40% restant à trouver par le responsable Produit et les équipes commerciales. 
L'équipe devait désormais développer et exploiter la plateforme. 

## Les bénéfices des expérimentations

Sans détailler toutes les expérimentations menées avec cette équipe, au bout d'un peu plus de deux années de travail, voici les principaux bénéfices relevés:
- une capacité à pivoter le produit face aux changements de stratégie de l'entreprise
- une capacité à garder "lean" le coût de la plateforme grâce à une approche FinOps
- une dette technique basse 
- une charge d'exploitation optimisée
- la charge de gestion des budgets et des plannings capacitaires a fortement diminué chez les managers

## Les facteurs clé du succès

- Un management à l'écoute et pro-actif
- Une volonté d'expérimenter
- Une équipe multi-compétentes pour faciliter les prises de décision
- Une approche empirique pour adresser la complexité
- Une approche produit structurée basée sur des objectifs
- Les concepts Team topologies pour définir les contours du produit et faciliter les interactions avec les autres équipes


