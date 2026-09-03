# Le pari empreinte (~10 min)
Fourchettes de `CO2e`:
-  `< 1g CO2e`
- `1–10g CO2e`
- `10–100g CO2e`
- `> 100g CO2e`

```markdown
| # | Situation                                               | Fourchette          |
|---|---------------------------------------------------------|---------------------|
| A | 1h de Netflix en HD                                     | ?                   |
| B | 1 mail avec PJ de 5 Mo envoyé à 10 personnes            | ?                   |
| C | 1 requête ChatGPT (GPT-4)                               | ?                   |
| D | 1 réunion vidéo de 1h à 6 personnes (caméras allumées)  | ?                   |
| E | 1 recherche Google                                      | ?                   |
| F | 1 image générée par Midjourney (v6) ou DALL-E 3         | ?                   |
```

> Ouvrir un nouveau fichier dans votre éditeur. Copier ce tableau et parier. 
> Pas de calcul, pas de recherche. Votre intuition. En silence.

## Corrections / explications

| # | Situation                                               | Réponse        | Équiv. voiture¹ |
|---|---------------------------------------------------------|----------------|-----------------|
| A | 1h de Netflix en HD                                     | ~36g CO2e      | ~300 m          |
| B | 1 mail avec PJ de 5 Mo envoyé à 10 personnes            | ~50g CO2e      | ~420 m          |
| C | 1 requête ChatGPT (GPT-4)                               | ~2–4g CO2e     | ~25 m           |
| D | 1 réunion vidéo de 1h à 6 personnes (caméras allumées)  | ~500–700g CO2e | ~5 km           |
| E | 1 recherche Google                                      | ~0,2–0,3g CO2e | ~2 m            |
| F | 1 image Midjourney (v6) / DALL-E 3                      | ~3–10g CO2e    | ~50 m           |

¹ Voiture thermique moyenne française : 120g CO2e/km ([ADEME, Base Empreinte](https://base-empreinte.ademe.fr/)).

> *"Je vais vous donner des ordres de grandeur - pas des vérités absolues. 
> Les chiffres sur l'empreinte du numérique varient selon les sources, les hypothèses, les pays, les mix énergétiques. 
> C'est exactement le piège que ce cours va vous apprendre à éviter. Je source tout ce que j'avance."*

### Situation A - 1h de Netflix en HD
`~36g CO2e` mais la fourchette réelle va de quelques grammes à plusieurs dizaines selon le contexte.

Ce qui change tout :
- **Le device** : un smartphone en 4G consomme bien plus qu'un ordinateur connecté en fibre sur un écran sobre.
- **Le réseau** : Wi-Fi < 4G < 5G.
- **Le mix énergétique** : regarder depuis un pays à fort nucléaire (France) vs. charbon (Pologne) multiplie l'impact par 5 à 10.

La valeur de 36g/h est issue d'une analyse IEA / Carbon Brief (2020) qui corrigeait les estimations très hautes du Shift Project (2019, ~1,6 kg/h - chiffre depuis retiré). 
Netflix publie également un rapport de durabilité qui situe l'empreinte autour de `100g/h` à l'échelle mondiale en incluant la fabrication des équipements.

Source : [The carbon footprint of streaming video: fact-checking the headlines](https://www.iea.org/commentaries/the-carbon-footprint-of-streaming-video-fact-checking-the-headlines) 


### Situation B - 1 mail avec PJ de 5 Mo envoyé à 10 personnes

`~50g CO2e`

L'ADEME cite ~19g CO2e pour un mail "standard" avec pièce jointe. 
5 Mo × 10 destinataires représente un cas sensiblement plus lourd : 50g est un ordre de grandeur raisonnable, à ne pas prendre au gramme près.

Source : [La face cachée du numérique, 2019](https://www.ademe.fr/la-face-cachee-du-numerique/)

#### Pourquoi autant ? L'histoire des pièces jointes

L'intuition dit : "c'est juste un fichier qui circule sur un réseau."

Voici ce qui se passe réellement quand tu envoies ce mail :

```
[Ton laptop]          → serveur sortant → 10 serveurs entrants
  ↓ (terminal 1)                              ↓
  encode le fichier                     stockent chacun 5 Mo

10 smartphones/laptops ← notification ← chaque serveur
(terminaux 2 à 11)
  ↓
  téléchargent la PJ
  décodent le fichier
  en font un aperçu
  la gardent en cache
```

La transmission réseau représente une fraction mineure de l'impact. 

Le vrai coût, c'est l'**énergie consommée par les 11 terminaux** :
- ton appareil pour envoyer
- et les 10 appareils des destinataires pour recevoir, décoder, afficher, stocker

Si certains l'ouvrent plusieurs fois, ou la font suivre, chaque action recommence.

> C'est le premier indice d'une règle que tu vas retrouver tout au long de ce cours : **dans un service numérique, 60 à 80% de l'impact est côté terminal**, pas côté serveur. 

### Situation C - 1 requête à ChatGPT (GPT-4)

`~2 à 4g CO2e` par requête courte (mais ça monte vite).

Ce qui fait exploser l'impact :
- **La longueur du contexte** : un prompt court avec réponse courte ≠ un long fil de conversation.
- **Le type de requête** : génération de code > question-réponse > résumé (à puissance de calcul variable).
- **Le multimodal** (images, audio, vision) : plusieurs ordres de grandeur au-dessus d'une requête texte.
- **Le mix énergétique du datacenter** : les serveurs d'OpenAI sont majoritairement sur Azure (mix US + Europe).

Une requête GPT-4 est estimée à ~0,001 à 0,01 kWh selon la complexité (Luccioni et al., 2023). Rapporté au mix carbone moyen des datacenters concernés, on obtient 1 à 10g CO2e.

Sources : 
- [Luccioni, A. S., Jernite, Y., & Strubell, E. (2024). "Power Hungry Processing: Watts Driving the Cost of AI Deployment?"](https://arxiv.org/abs/2311.16863) 
- [Goldman Sachs Research (2024). "GS SUSTAIN: Generational Growth - AI/data centers' global power surge and the sustainability impact"](https://www.goldmansachs.com/insights/goldman-sachs-research/gs-sustain-generational-growth-ai-data-centers-global-power)

### Situation D - 1 réunion vidéo de 1h à 6 personnes (Teams/Zoom, caméras allumées)

`~500 à 700g CO2e au total` (soit ~100g par personne et par heure).

Une réunion en ligne semble "légère", dématérialisée, sans déplacement. 
En réalité, elle cumule :
- 6 appareils en encoding vidéo simultanés
- 6 casques ou enceintes actifs
- 6 connexions réseau
- les serveurs de relais qui traitent les flux en temps réel

Ce qui amplifie :
- **Caméras allumées vs. éteintes** : couper la caméra divise l'impact d'environ 10 (Carbon Trust, 2021). 
  - L'audio seul d'une réunion d'1h coûte ~7g par personne.
- **Le fond virtuel** : traitement GPU local continu (consommation en hausse mesurable).
- **Le nombre de participants** : l'impact est quasiment linéaire. 12 personnes ≈ 1,2 kg CO2e pour 1h.

À titre de comparaison : 1h de réunion vidéo pour 6 personnes coûte à peu près autant que 6h de streaming Netflix solo. 
Ce n'est pas un argument contre les réunions à distance, c'est un argument pour se demander quand les caméras ajoutent vraiment de la valeur.

Source : ["The overlooked environmental footprint of increasing Internet use."](https://energy.mit.edu/publication/the-overlooked-environmental-footprint-of-increasing-internet-use/)

### Situation E - 1 recherche Google

`~0,2 à 0,3g CO2e`

Celle-là va dans l'autre sens : les gens surestiment largement. 
Google publie dans son rapport de durabilité une estimation interne de `~0,3g CO2e` par requête, réseau et datacenter inclus.

Ce qui est bas :
- **L'index est précalculé** : Google ne parcourt pas le web à chaque recherche. 
  - Le résultat est servi depuis un cache gigantesque (très peu de calculs au moment de la requête).
- **Les datacenters Google** sont alimentés à 100% en énergie renouvelable en neutralité carbone.
- **La page de résultats est légère** : texte + quelques liens - bien loin d'un site e-commerce surchargé.

Ce qui est sous-estimé : la fabrication de ton smartphone ou laptop n'est pas dans ces 0,3g. 

> Si on intègre la quote-part d'amortissement du terminal sur toute sa durée de vie, chaque geste numérique coûte plus cher que ce que la mesure en usage laisse entendre. 
> C'est l'angle "cycle de vie" qu'une vraie ACV capture.

Source : [Google - Sustainability Report 2023](https://sustainability.google/reports/google-2023-environmental-report/)

### Situation F - 1 image générée par Midjourney (v6) ou DALL-E 3

**~3 à 10g CO2e** par image.

C'est souvent perçu comme "plus lourd que ChatGPT".
Intuitivement, générer une image semble plus complexe que du texte. 

En pratique, les ordres de grandeur sont proches, mais la génération d'image est effectivement plus GPU-intensive que la génération de texte.

Ce qui varie :
- **Le nombre de steps de diffusion** : Midjourney V6 fait des passes successives de débruitage.
- **La résolution** : une image 2048×2048 coûte sensiblement plus qu'une 512×512.
- **Les variantes** : générer 4 variantes × upscale = 5 à 8× le coût d'une image simple.


Source : [Luccioni, A. S., Jernite, Y., & Strubell, E. (2024). "Power Hungry Processing: Watts Driving the Cost of AI Deployment?"](https://arxiv.org/abs/2311.16863)