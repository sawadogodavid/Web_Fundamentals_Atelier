# 📒 Mon carnet de bord

**Nom :** 

**Prénom :** 

**Adresse de mon site :** https://______.pythonanywhere.com

> Modifiez ce fichier directement sur GitHub (icône crayon ✏️) pour répondre aux questions de chaque exercice.
> Écrivez avec vos propres mots : une réponse courte et juste vaut mieux qu'un long copier-coller ! 🙂

---

## 🟢 Exercice 1 — Mon premier déploiement

1. Où se trouve physiquement le code qui fabrique votre page : sur votre ordinateur, sur GitHub ou sur PythonAnywhere ?

   > _Ma réponse :_ Il se trouve physiquement sur le serveur de PythonAnywhere (c'est là qu'il s'exécute pour traiter les requêtes et fabriquer la page), après avoir été récupéré depuis GitHub.

2. Pourquoi votre voisin(e) peut-il voir votre site, alors que vous n'avez rien installé sur son ordinateur ?

   > _Ma réponse :_ Parce que le site est hébergé et s'exécute sur un serveur distant accessible via Internet (via une URL). Le navigateur web de votre voisin se connecte simplement à ce serveur distant pour afficher le résultat, sans nécessiter aucune installation sur sa machine.

---

## 🟢 Exercice 2 — Les URL et les routes

1. Dans l'URL `https://www.google.com/maps`, quel est le nom de domaine ? Quel est le chemin ?

   > _Ma réponse :_ Nom de domaine : [www.google.com](https://www.google.com)   

Chemin (path) : /maps

2. Que veut dire le message *Not Found* ? Qui l'a envoyé : votre navigateur ou le serveur ?

   > _Ma réponse :_ La page demandée n'a pas été trouvée (le serveur ne connaît pas cette route/adresse)

3. Que se passe-t-il si deux fonctions portent le même nom dans `flask_app.py` ? (Indice : essayez, puis lisez l'Error log.)

   > _Ma réponse :_ La deuxième fonction écrase la première. Python ne garde que la dernière définition en mémoire, et l'ancienne route est remplacée (ou génère une erreur au démarrage/dans les logs selon la configuration).

---

## 🔵 Exercice 3 — Le langage HTML

1. Quelle est la différence entre ce que le serveur **envoie** et ce que le navigateur **affiche** ?

   > _Ma réponse :_ Le serveur envoie du code HTML brut, tandis que le navigateur interprète ce code pour afficher une page web visuelle.

2. À quoi servent les balises `<h1>`, `<p>`, `<ul>` et `<li>` ?

   > _Ma réponse :_ <h1> : C'est un grand titre (Heading 1).
<p> : C'est un paragraphe de texte.
<ul> : C'est une liste à puces (Unordered list).
<li> : C'est un élément (un point) à l'intérieur de cette liste (List item)

3. Pourquoi l'image s'affiche-t-elle alors qu'elle n'est pas sur votre serveur ?

   > _Ma réponse :_ Parce que le lien (src="...") pointe directement vers une image hébergée sur Internet (sur Wikipédia). C'est le navigateur qui va la chercher tout seul là-bas au moment d'afficher la page.

---

## 🔵 Exercice 4 — Les templates

1. Pourquoi est-ce une bonne idée de séparer le code Python et le HTML ? (Pensez à une équipe avec un développeur et un graphiste.)

   > _Ma réponse :_ Ça permet de séparer la logique (le code Python géré par le développeur) du design et de la mise en page (le HTML géré par le graphiste), ce qui évite d'avoir un gros fichier illisible et permet à chacun de travailler de son côté plus facilement.

2. Les `{{ prenom }}` sont-ils remplacés par le serveur ou par le navigateur ? Comment l'avez-vous vérifié ?

   > _Ma réponse :_ Ils sont remplacés par le serveur (grâce au moteur de template avant l'envoi), et on peut le vérifier en faisant un « Afficher le code source » dans le navigateur, où l'on voit que le prénom en clair a remplacé les accolades.

---

## 🔵 Exercice 5 — Le CSS et les liens

1. Quelle est la différence de rôle entre le HTML et le CSS ?

   > _Ma réponse :_ Le HTML sert à structurer le contenu de la page (les textes, les titres, les liens), tandis que le CSS sert à la mise en forme et au design (les couleurs, les polices, l'agencement).

2. Pour afficher votre page `/presentation`, combien de fichiers le navigateur doit-il télécharger ? (Vous pourrez le vérifier à l'exercice suivant !)

   > _Ma réponse :_ Il doit en télécharger 2 : le fichier HTML (presentation.html) et le fichier de style (style.css).

3. Pourquoi faut-il parfois faire **Ctrl + F5** pour voir les changements de CSS ?

   > _Ma réponse :_ Pour vider le cache du navigateur et le forcer à télécharger la nouvelle version du fichier CSS au lieu d'utiliser l'ancienne version qu'il avait gardée en mémoire.

---

## 🟣 Exercice 6 — Espionner le navigateur

1. Que signifie HTTP ? Qui envoie la **requête** et qui envoie la **réponse** ?

   > _Ma réponse :_ HTTP : HyperText Transfer Protocol.
Requête : Envoyée par le navigateur (client).
Réponse : Envoyée par le serveur.

2. Combien de requêtes votre page `/presentation` a-t-elle déclenchées ? Lesquelles ?

   > _Ma réponse :_ Nombre : 3 requêtes.
Lesquelles : La page HTML (presentation), la feuille de style (style.css) et le favicon (favicon.ico).

3. Que signifie le code `200` ? Et le code `404` de la favicon ?

   > _Ma réponse :_ 200 : Succès (OK, la ressource a été trouvée et envoyée).
404 : Non trouvé (le serveur n'a pas trouvé le fichier favicon.ico).

4. Pourquoi les modifications faites dans l'onglet Éléments ne sont-elles pas visibles par les autres visiteurs ?

   > _Ma réponse :_ Parce que ces modifications sont faites uniquement en local sur ton navigateur, sans toucher au fichier stocké sur le serveur distant.

---

## 🟣 Exercice 7 — Envoyer des informations dans l'URL

1. Dans l'URL `https://www.youtube.com/results?search_query=chat`, quel est le nom du paramètre ? Quelle est sa valeur ?

   > _Ma réponse :_ Nom du paramètre : search_query
Valeur : chat

2. Pourquoi le serveur plante-t-il avec `a=bonjour` ? Que faudrait-il faire pour l'éviter ?

   > _Ma réponse :_ Pourquoi : Le serveur plante généralement parce qu'il s'attend à un type de données précis (par exemple un nombre entier avec int()) ou à un autre nom de paramètre, et la valeur fournie provoque une erreur (comme une conversion impossible).
Ce qu'il faut faire : Gérer les erreurs (avec un bloc try...except) ou vérifier si le paramètre existe et a le bon format avant de l'utiliser.

3. Pourquoi est-il dangereux d'afficher **tel quel** ce que l'utilisateur envoie ?

   > _Ma réponse :_ Parce que l'utilisateur peut envoyer du code malveillant (comme du JavaScript dans une balise <script>), ce qui expose à des failles de sécurité de type XSS (Cross-Site Scripting) où un attaquant pourrait détourner la page ou voler des données.

---

## 🟣 Exercice 8 — Les formulaires

1. Quelle est la différence visible entre GET et POST ?

   > _Ma réponse :_ Avec GET, les données passées s'affichent directement dans l'URL (dans la barre d'adresse). Avec POST, les données sont cachées et voyagent discrètement dans le corps de la requête (le corps HTTP), donc l'URL reste propre.

2. Pour un formulaire de **recherche**, quelle méthode choisiriez-vous ? Et pour un formulaire de **connexion avec mot de passe** ? Pourquoi ?

   > _Ma réponse :_ Recherche : La méthode GET, car cela permet d'avoir la recherche dans l'URL, ce qui est pratique pour copier, enregistrer ou partager le lien.
Connexion (mot de passe) : La méthode POST, pour éviter que le mot de passe ne s'affiche en clair dans la barre d'adresse.

3. Les données envoyées en POST sont-elles vraiment « secrètes » ? (Pensez à ce que vous avez vu dans l'onglet Réseau.)

   > _Ma réponse :_ Non, elles ne sont pas vraiment secrètes : elles sont juste cachées de l'URL. N'importe qui peut facilement les voir en ouvrant l'onglet Réseau (Network) des outils de développement du navigateur.

---

## 🔴 Exercice 9 — Les codes de statut

1. Quelle est la différence entre une erreur `4xx` et une erreur `5xx` ? Qui est « fautif » dans chaque cas ?

   > _Ma réponse :_ Erreur 4xx : Vient du client (le navigateur a demandé une page qui n'existe pas ou mal formulée). Le « fautif » est le client/l'utilisateur.
Erreur 5xx : Vient du serveur (le serveur a planté ou a un bug interne). Le « fautif » est le serveur/le code du site.

2. Comment fonctionne une redirection ? Qui fait la deuxième requête : le serveur ou le navigateur ?

   > _Ma réponse :_ Le serveur répond avec un code de redirection et une nouvelle adresse. C'est ensuite le navigateur qui prend le relais et fait automatiquement la deuxième requête vers cette nouvelle URL.

3. Donnez un exemple de situation où un vrai site utilise une redirection.

   > _Ma réponse :_ Quand on tape une ancienne adresse d'un site ou qu'on tape google.fr, le site redirige automatiquement vers la version sécurisée [https://www.google.fr](https://www.google.fr) (ou lorsqu'on se connecte, on est redirigé vers sa page de profil).

---

## 🔴 Exercice 10 — Ce que le serveur sait de vous

1. Citez trois informations que le serveur connaît sur vous, sans que vous ayez rien rempli.

   > _Ma réponse :_ L'adresse IP (la localisation approximative), le type de navigateur/système d'exploitation (User-Agent) et la langue préférée.

2. À quoi peut servir l'en-tête `Accept-Language` pour un site comme Wikipédia ?

   > _Ma réponse :_ À afficher directement les articles dans la langue préférée de l'utilisateur (par exemple en français si le navigateur est configuré en français).

3. Dans l'Access log, retrouvez une requête qui a reçu un code `404`. Quelle page était demandée ?

   > _Ma réponse :_ Réponse libre selon ton fichier de log : Le nom de la ressource introuvable qui apparaît sur la ligne avec le code 404 (par exemple /favicon.ico ou une page inexistante).

4. Après cet exercice, que pensez-vous de la notion de « navigation anonyme » ?

   > _Ma réponse :_ Elle est trompeuse car elle cache seulement l'historique sur l'appareil local : le serveur distant voit toujours l'adresse IP, le navigateur utilisé et les requêtes envoyées.

---

## 🔴 Exercice 11 — Le Web des machines : API et JSON

1. Quelle est la différence entre une page HTML et une réponse JSON ? À qui chacune est-elle destinée ?

   > _Ma réponse :_ Page HTML : Elle contient la structure visuelle et la mise en page d'un site web. Elle est destinée à être affichée par le navigateur pour être lue par un humain.
Réponse JSON : C'est un format de données brut (sous forme de texte structuré). Elle est destinée à un autre programme ou script (comme une application mobile ou JavaScript) pour être traitée facilement.

2. Dans la page `/horloge`, quel code s'exécute sur le **serveur** et quel code s'exécute dans le **navigateur** ?

   > _Ma réponse :_ Le code Python (Flask) qui récupère l'heure ou génère la réponse s'exécute sur le serveur. Le code HTML/CSS ou le script qui affiche le résultat s'exécute dans le navigateur.

3. Citez une application de votre téléphone qui, selon vous, utilise une API. Quelles données échange-t-elle ?

   > _Ma réponse :_ Exemple (Météo) : L'application météo. Elle envoie une requête API avec les coordonnées GPS de ta position et reçoit en retour des données JSON (température, prévisions, humidité) pour les afficher.

---

## 🏁 Pour conclure

En quelques phrases, expliquez à un ami ce qui se passe entre le moment où il tape une adresse dans son navigateur et celui où la page s'affiche :

> _Ma réponse :_ 
