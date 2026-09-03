Les Familles individuellement.
Après les `Spécifications` : trouver les non-conformités via les Benchmarks habituels :
- 
- **C1** : *"le site obèse choisi ce matin - vos paris sur sa note EcoIndex ?"* - chaque groupe parie, on note
- **C2** : 10 min de cadrage - ce que mesure EcoIndex, Lighthouse, Website Carbon Calculator, ce qu'ils ratent
- **C3** : atelier 1h - chaque binôme passe le site choisi dans les 3 outils, compare les résultats, calcule un équivalent parlant (km voiture, recharges smartphone × volume annuel estimé)
- **C4** : galerie tournante - chaque binôme affiche son tableau de résultats, les autres circulent et annotent

---

## Jour 2 - Agir et industrialiser

### Reconnexion (~20 min)
- **C1 global** : speed-recap par paires + relecture rapide du backlog affiché

--

### Module 7 - Leviers code : pagination, projection DTO, index (~1h30)

- **C1** : démo live - un endpoint `/films` qui retourne tout avec `SELECT *`. Mesure du payload, du temps de réponse, du nombre de requêtes
- **C2** : pagination, projection DTO, indexation - les 3 patterns + leurs anti-patterns
- **C3** : kata - chaque groupe implémente les 3 leviers sur un endpoint dédié, mesure avant/après avec `ab`
- **C4** : tableau collectif des deltas mesurés. *"Quel levier a eu le plus gros impact sur votre endpoint ?"*

---

### Pause déjeuner

---

### Module 8 - Leviers code avancés : cache, lambdas, monades (~1h15)

- **C1** : *"montrez-moi un bout de code de votre projet qui pourrait être mieux"* - partage à 2
- **C2** : cache applicatif, mémoïsation des lambdas répétées, monades `Result<T,E>` vs exceptions - convergence qualité/sobriété
- **C3** : sur le projet support, refactorer 1 service avec un de ces leviers au choix, mesurer
- **C4** : *"quel pattern j'introduis dès la semaine prochaine dans mon code ?"*

---

### Module 9 - Accessibilité dès le Jour 1 avec axe-core + Playwright (~1h)

- **C1** : démo - passer axe-core sur le front Svelte du projet, révéler les violations
- **C2** : intégrer l'a11y dans les tests E2E plutôt qu'en fin de sprint, principes
- **C3** : par binôme, écrire 1 test Playwright + axe-core sur un parcours du projet
- **C4** : chacun s'engage sur 1 test a11y à ajouter dans son projet pro

---

### Module 10 - Mesurer en continu : EcoIndex et `ab` au CI (~1h)

- **C1** : *"comment vous détectez aujourd'hui une régression de perf ?"* - recueil rapide
- **C2** : la sobriété comme test, intégration au pipeline, seuils et build cassant
- **C3** : ajouter un job CI au projet support qui lance EcoIndex + `ab` et casse le build si régression
- **C4** : tableau collectif - *"qu'est-ce que je peux ajouter à ma CI dès demain ?"*

---

### Module 11 - Badge de transparence (~30 min)

- **C1** : *"si vous deviez afficher votre Nutri-Score numérique sur votre site, vous oseriez ?"*
- **C2** : le badge comme geste de transparence - version numérique du Nutri-Score, ce qu'il force comme posture
- **C3** : chaque groupe rédige et maquette le badge de son projet support - score, date, page "Notre empreinte"
- **C4** : galerie des badges affichée au mur

---
