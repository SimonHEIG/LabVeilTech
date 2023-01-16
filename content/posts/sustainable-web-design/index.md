+++
categories = ["Front-end"]
date = "2023-01-16"
description = "Recherches et pistes d'amélioration sur comment adopter un développement plus vert et plus \"sustainable\""
linktitle = ""
title = "Sustainable Web Design"
slug = "sustainable-web-design"
type = "post"
+++

## Introduction

Compte tenu des immense enjeux climatiques dans lesquels nous évoluons depuis plusieurs années, la plupart des industries ont aujourd’hui des standards énergétiques et environnementaux à respecter. Seulement, ça n’est pas encore le cas du web. Il est cependant important que le secteur commence à s’intéresser sérieusement à cette problématique afin de contribuer à l’effort global (ou presque) pour luter contre le dérèglement climatique.

Le but est de réduire les émissions de CO2 produites par la consommation de page web, et cela implique de considérer les sources qui contribuent à cette production. Seulement, ce n’est pas chose facile à mesurer car les sources de CO2 sont bien loin de nous, développeurs. Nous devons donc comprendre ce qui influe sur la quantité d'énergie consommée pour pouvoir ensuite la réduire. 

Pour ce faire, il est possible de prendre en compte deux variables : 

- Le transfert de données
- L’intensité en carbone de l’électricité


>💡 Le site [websitecarbon.com](http://websitecarbon.com/) permet d’évaluer les émission carbone d’un site web ainsi que d’obtenir d’autres information à ce sujet.

## Transfert de données

Le premier facteur a prendre en compte est le volume de données qui doit faire le trajet entre le serveur et le client. La quantité d’énergie nécessaire au transfert de données est mesurée en kWh/GB. Plus cette valeur est grande, plus les émissions de carbone nécessaire à produite l’énergie le seront aussi.

Pour les pages web, il est assez aisé de calculer grâce à l’outil développeur du navigateur, la quantité de données transférées au premier chargement de la page. Cette quantité de données correspond approximativement au poids de la page web. Environ la moitié de ce transfert de données sont des fichiers d'image, ce qui en fait la principale source d'émissions de carbone sur un site web moyen.

En tant que développeur, un moyen de se restreindre est d’adopter le concept du budget de performances. Le principe est simple, il s’agit de fixer un objectif de temps limite au chargement d’une page web. Ainsi, en designant pour des meilleures performances, on fait beaucoup plus attention au volume de données comprises dans nos pages et elles deviennent donc plus sustainable. 

## L’intensité en carbone de l’électricité

Là où la pollution du transfert de données était calculée en kWh/GB, il sera ici question de gCO2/kWh. Autrement dit, cette unité représente si une source de production de l’électricité dégage beaucoup, ou non de CO2 par kWh produits. Il est donc préférable d’héberger nos sites web dans des pays ou le taux de CO2 par kWh est faible. Le site [electricitymaps.com](https://app.electricitymaps.com/map) permet de se rendre compte de l’impacte en CO2 des différentes régions du monde ainsi de leur part de renouvelable. 

Il est aussi nécessaire de prendre en compte la distance entre les serveurs et les utilisateurs. Plus la distance est grande, plus une quantité d’énergie importante sera nécessaire pour faire transiter les données. Ainsi, pour un site web majoritairement visité par des européens, un hébergement a faible intensité en carbone comme le Canada ne serait pas forcément un meilleur choix qu’un pays européen ayant une intensité un peu supérieure.

## Comment développer plus vert ?

La prise en compte de ces facteurs peut s’avérer être un défi, mais il est important de ne pas oublier que chaque petit geste peut contribuer à réduire l’impact sur l’environnement. En développant des pages web qui limitent le transfert de données, qui sont optimisées pour un chargement rapide et qui sont hébergées près des utilisateurs, les développeurs web peuvent contribuer à leur manière à réduire la consommation d'énergie et à avoir un impact positif sur l’environnement.

---

### Sources
Sustainable Web Design, An Excerpt : [alistapart.com](https://alistapart.com/article/sustainable-web-design-excerpt/)