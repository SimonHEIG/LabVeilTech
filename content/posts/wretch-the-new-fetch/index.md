+++
categories = ["Front-end"]
date = "2023-01-18"
description = "Analyse de la libraire de requêtes HTTP open-source \"wretch\". "
linktitle = ""
title = "Wretch, the new fetch ?"
slug = "wretch-the-new-fetch"
type = "post"
+++

## Introduction

La fonction JavaScript `fetch` est une fonction très puissante et utile qui permet aux développeurs d'effectuer des requêtes HTTP en toute simplicité. Il est devenu l'un des éléments les plus populaires de l'API JavaScript, et est largement utilisé pour les applications web. Seulement, `fetch` comprend aussi quelques points négatifs. 

La librairie `wretch` a été conçue comme une amélioration construite autour de la fonction `fetch` de base ayant pour but de simplifier la manière d’effectuer des requêtes et de gérer les réponses.

## Différences entre wretch et fetch

Sur son repository Github, il est décrit que `wretch` a été créé pour réponde à 4 motivations : 

### 1 - Les deux callbacks

La première amélioration que propose `wretch` est de simplifier la requête de base en s’affranchissant du second callback.

```jsx
// 🚩 Avec fetch
fetch("examples/example.json")
  .then(response => response.json())
  .then(json => {
    //Do stuff with the parsed json
  });

// ✅ Avec wretch
wretch("examples/example.json")
  .get()
  .json(json => {
    // Do stuff with the parsed json
  });
```

### 2 - La gestion des erreurs

Dans une utilisation classique avec un `try / catch` la fonction `fetch` renvoie uniquement un code d’erreur 200 chaque erreur. Palier ce problème devient rapidement très lourd, `wretch` propose donc une solution beaucoup plus légère.

```jsx
// 🚩 Avec fetch 
fetch("anything")
	.then(response => {
	  if(!response.ok) {
	    if(response.status === 404) throw new Error("Not found")
	    else if(response.status === 401) throw new Error("Unauthorized")
	    else if(response.status === 418) throw new Error("I'm a teapot !")
	    else throw new Error("Other error")
	  }else {
			// ...
		}
	})
	.then(data => /* ... */)
	.catch(error => { /* ... */ })

// ✅ Avec wretch
wretch("anything")
  .get()
  .notFound(error => { /* ... */ })
  .unauthorized(error => { /* ... */ })
  .error(418, error => { /* ... */ })
  .res(response => /* ... */)
  .catch(error => { /* uncaught errors */ })
```

### 3 - L’envoie aisé d’un json

Lors d’un requête `POST`  classique, envoyer un objet nécessite une sérialisation. Ce n’est plus le cas avec `wretch`.

```jsx
// 🚩 Avec fetch 
fetch("endpoint", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ "hello": "world" })
}).then(response => /* ... */)
// Omitting the data retrieval and error management parts…

// ✅ Avec wretch
wretch("endpoint")
	.post({ "hello": "world" })
  .res(response => /* ... */)
```

### 4 - Une configuration unique

Fetcher des données est souvent nécessaire à plusieurs endroit du code. En utilisant une API ayant besoin d’authentification ou autre configuration, dans une utilisation de base, il faudrait réécrire cette configuration a chaque requête. Avec `wretch` ce problème est résolu.

```jsx
// Cross origin authenticated requests on an external API
const externalApi = wretch("http://external.api") // Base url
  // Authorization header
  .auth(`Bearer ${token}`)
  // Cors fetch options
  .options({ credentials: "include", mode: "cors" })
  // Handle 403 errors
  .resolve((_) => _.forbidden(handle403));

// Fetch a resource
const resource = await externalApi
  // Add a custom header for this request
  .headers({ "If-Unmodified-Since": "Wed, 21 Oct 2015 07:28:00 GMT" })
  .get("/resource/1")
  .json(handleResource);

// Post a resource
externalApi
  .url("/resource")
  .post({ "Shiny new": "resource object" })
  .json(handleNewResourceResult);
```
## Avantages, inconvénients et conclusion

| **Avantages**          	| **Inconvénients**          	|
|------------------------	|----------------------------	|
| ✔️ Léger (2KB)            	| ❌ Un package supplémentaire  	|
| ✔️ Intuitif               	| ❌ Pas (encore ?) un standard 	|
| ✔️ Open-source & maintenu 	|                            	|
| ✔️ Fortement typé         	|                            	|

En conclusion, `wretch` est une librairie JavaScript très utile qui permet aux développeurs d'effectuer des requêtes HTTP en toute simplicité et plus rapidement qu'avec la fonction `fetch` de base. Son installation ne représentant pas un poids conséquent elle est donc parfaite pour compléter la fonction originale de `fetch` et peut être intéressant à intégré dans des futurs projets javascript.

---

### Sources
Repository Github de wretch : [github.com](https://github.com/elbywan/wretch)