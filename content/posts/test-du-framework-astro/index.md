+++
categories = ["Front-end"]
date = "2023-01-16"
description = "Analyse de l'utilisation des frameworks javascripts en 2022"
linktitle = ""
title = "The State of JS | Front-end framework"
slug = "state-of-js-frontend-framework"
type = "post"
+++

## Sujet et objectifs de l'expérience

En décembre dernier est sorti à été publié le site web de l’application *[Streali](https://www.streali.com/)*. Trouvant le design particulièrement réussi et par curiosité je me suis rendu sur le repository Github du projet et j’ai remarqué que le site avait été développé avec un framework dont je n’avais encore jamais entendu parlé : **[Astro](https://astro.build/)**.

Ayant déjà des connaissances en front-end avec Vue.js ainsi qu’en back-end avec Express.js et Laravel, Astro paraissait comme une nouvelle manière de développer une page web. C’est la première fois que j’entendais parler d’`island architecture` ou de `server side rendering`. J’ai donc décidé de tester ce framework pour la création de mon portfolio dans le cadre d’un cours nommé *Profil professionnel*. Cela m’a aussi permis de pouvoir raconter mon expérience lors de la prise en main de ce framework pour le cours de *Laboratoire de veille technologique*.

Mon objectif était simple : Prendre en main un nouveau framework adoptant une approche différentes de la création de page web de celles que je connaissais déjà.

## Résultat attendu vs Résultat obtenu

En utilisant **Astro** pour la création de mon portfolio, mon but était d’obtenir un site web fonctionnel rapidement en ayant besoin de peu de connaissances car cet une des promesses d’Astro. Le résultat obtenu correspond parfaitement à mes attentes même s’il m’a pris un peu plus de temps que prévu. Ce temps supplémentaire n’est pas réellement dû à la prise en main d’Astro mais plutôt au fait que c’était aussi la première fois que j’utilisais *Tailwind CSS.*

## Points d'apprentissage

Lors de mon utilisation d’**Astro** j’ai appris plusieurs choses sur ses capacités.

1. Il est possible de générer des pages web grâce à des fichier `.md` ou `.mdx`. Cela rend la création de contenu très simplifiée comme cela peut l’être avec le `static site generator` **Hugo**.
2. Il est possible de créer dynamiquement des pages en fonction des données fournies par une API. Imaginons qu’une liste de produits avec leurs caractéristiques est stockée sur un serveur distant et disponible à travers une API, il suffirait de créer un template pour une page d’article et de faire une requêtes à l’API pour que les pages soient générées à la volée sans avoir à les hardcoder.
3. L’utilisation de l’`island architecture` est très utile pour générer des sites nécessitant peu de réactivité. De cette manière, la majorité du contenu est générée par le serveur (SSR) alors que la minorité de contenu nécessitant d’être réactive est côté client (CSR). Cela permet d’obtenir un site web très performant comme c’est le cas avec des générateurs de sites statiques mais en gardant un côté dynamique et réactifs par endroit. De plus le SSR favorise l’indexation dans les moteurs de recherches.

## Idées/exemples d'application de la méthode

Après avoir utilisé **Astro** du début à la fin d’un projet, je dirais qu’il peut être intéressant de l’utiliser dans 2 cas de figures : 

1. Sites ayant des données d’une API à afficher. **Astro** facilite vraiment la création dynamique de pages pour ce genre de contenu.
2. Des sites de taille petite à moyenne ne nécessitant pas une logique trop grande. Le framework permet vraiment d’avoir un résultat très rapidement pour ce genre de projets. Notamment grâce aux `composants astro` qui peuvent se substituer à ceux de Vue ou de React pour des opérations de bases.

---

### Sources
Site d'Astro : [astro.build](https://astro.build/)
Documentation d'Astro : [docs.astro.build](https://docs.astro.build/en/concepts/why-astro/)
Portfolio réalisé avec Astro : [meia.dev](https://meia.dev/)