# visualiseur abstrait

Visualiseur audio-réactif tournant entièrement dans le navigateur (WebGL2, un seul fichier HTML, aucune dépendance externe). Charge un fichier audio (ou reste en mode démo) et laisse tourner : 21 scènes, des effets glitch/image programmables, des LFO, un enregistreur vidéo et une détection de tempo intégrés.

## Utilisation

Ouvre simplement `index.html` dans un navigateur compatible WebGL2 (Chrome, Edge, Firefox récents) — ou utilise la version en ligne si GitHub Pages est activé sur ce dépôt.

- **Audio** : charge un fichier (`Choisir un fichier`) ou reste en mode `démo` pour un signal synthétique.
- **H** : cache/affiche le panneau de contrôle.
- **Plein écran** conseillé pour l'affichage.

## Scènes

21 scènes réparties en trois familles :

- **Abstrait** — champ de particules, braises, image, métaballs, sphère qui respire/implose, sphères qui dansent, sphère + vent, explosion, nuage qui explose, éclairs, galaxie spirale.
- **Semi-abstrait** — grille de Voronoi, mandala, veines topographiques, arbre fractal, racines qui poussent, onde 3D torsadée.
- **Concret** — tempête de particules, skyline procédural (vol libre à travers une ville générée à l'infini), eau/plasma, grille néon cyberpunk.

## Fonctionnalités

- **Scène Image** : charge une photo ou une vidéo, 10 effets (particules 3D, contours, tranches, griffonnage, facettes, fil de fer, sculpture filaire, étincelles, particules vidéo, vent), 17 palettes de couleur (dont deux négatifs inversés), slider de lumière, grain qui monte avec la quantité.
- **Glitch** : 8 effets indépendants combinables (numérique, déformation, echo, glitch, neige, parasite, interférence, irisation).
- **LFO** : 4 emplacements pour moduler n'importe quel paramètre en continu (sinusoïde, aléatoire, ou suivi d'une bande audio).
- **Préréglages** : sauvegarde/chargement de configurations complètes (stockage local du navigateur).
- **Mouvements progressifs** : case à cocher pour lisser les changements de curseurs au lieu de sauts immédiats.
- **Détection de tempo (BPM)** : estimation en direct à partir des coups détectés dans le signal audio.
- **Enregistrement vidéo** : capture ce qui s'affiche (image + son si un fichier audio est en lecture) et télécharge un `.webm`, directement depuis le navigateur.

## Technique

Un seul fichier HTML autonome : WebGL2 pour le rendu (systèmes de particules GPU en ping-pong, shaders plein écran raymarchés, géométrie 3D), Web Audio API pour l'analyse spectrale, MediaRecorder pour l'export vidéo. Aucune build step, aucune dépendance.
