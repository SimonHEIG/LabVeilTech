+++
categories = ["Front-end"]
date = "2023-01-26"
description = "Découverte du composant Vue 3 : <Suspense>"
linktitle = ""
title = "Vue 3 <Suspense>"
slug = "vue3-suspense"
type = "post"
+++

## Introduction

Lors du chargement de données dans un composant, il est souvent nécessaire d’afficher un **loader** afin de montrer à l’utilisateur que le système n’est pas bloqué et qu’il se passe bien quelque chose. Une manière classique d’ajouter un **loader** est de passer directement par le composant en lui ajoutant du code indiquant que tant qu’il n’a pas reçu de données, il doit afficher un **loader**. 

Le problème est que si plusieurs composant doivent recevoir des données, on peut vite se retrouver avec une interface plus du tout conviviale car remplie de *loaders.* Pour palier ce problème, il est possible d’utiliser le *built-in component* Vue : `<Suspense>` .

>⚠️ `<Suspense>` est encore une **experimental feature**, il ne faut pas encore prendre pour acquis l’état actuel du composant car il pourra encore être modifié avant sa sortie officielle.


## Le fonctionnement de <Suspense>

Le principe est simple, il suffit de réunir tous les composants nécessitants un fetch de donnés entre deux balises `<Suspense>`. Lors du rendu initial de la page, `<Suspense>` va afficher le contenu par défaut du slot de chaque dépendance. Durant ce processus, `<Suspense>` va détecter si certaines de ses dépendances sont asynchrones. Si c’est le cas, elles entrent dans un **pending state**. Tant que les dépendances n’ont pas été résolues, le **fallback content** sera affiché. Une fois les données disponibles dans chacune des dépendances asynchrones, `<Suspense>` passe à l’état **resolved** et le contenu final est affiché.

## Conclusion

Le composant `<Suspense>` est donc une potentielle futur bonne pratique que tout bon développeur Vue devra adopter. Il est donc bon de se maintenir au courant de l’avancement du développement de ce composant afin d’être informé quand il sera officiellement introduit au framework.

---

### Sources

- [Vue Suspense - A Cleaner Way to Manage Loading States](https://fadamakis.hashnode.dev/vue-suspense-a-cleaner-way-to-manage-loading-states-54df885a52c3)
- [Suspense | Vue.js](https://vuejs.org/guide/built-ins/suspense.html)