# You Man Quest

> Défends la planète Disco !

Jeu de tir pseudo-3D (raycasting type *Wolfenstein 3D*) en **un seul fichier HTML autonome**,
optimisé pour mobile en format portrait 9:16, sans aucune dépendance externe.

👉 Ouvrez [`index.html`](index.html) dans un navigateur — c'est tout.

## Le jeu

Vous incarnez le **You Man du futur**, héros venu défendre la planète Disco.
Explorez le donjon électro-techno, récupérez les **5 vinyls sacrés**, dissipez les
fantômes qui menacent le groove universel, traversez les **Backrooms**, et atteignez la
**boule disco cosmique** qui sauve la planète.

| Niveau | Contenu |
| --- | --- |
| 1 — Donjon électro-techno | Labyrinthe néon, 3 vinyls, 5 fantômes |
| 2 — The Backrooms | Couloirs jaunes-beige, néons vacillants, 2 vinyls, aucun ennemi |
| 3 — Salle disco cosmique | Boule disco géante et lasers rainbow rotatifs |

- 3 vies : chaque contact avec un fantôme coûte une vie (écran rouge).
- 3 projectiles pour dissiper un fantôme.
- 1 tir toutes les 0,5 s (recharge automatique).

## Contrôles

**Mobile**
- Gyroscope : pencher vers l'avant = avancer, vers l'arrière = reculer, inclinaison latérale = tourner.
  Sensibilité, zone morte et bouton *Recalibrer* dans les Options. iOS 13+ : bouton « Activer le gyroscope ».
- Flèches tactiles (prioritaires sur le gyroscope) + gros bouton **TIR**. Un tap sur la zone haute de l'écran tire aussi.
- Repli automatique sur les commandes tactiles si aucun capteur n'est disponible.

**Ordinateur**

| Touche | Action |
| --- | --- |
| `Z` / `W` / `↑` | Avancer |
| `S` / `↓` | Reculer |
| `Q` / `A` / `←` | Tourner à gauche |
| `D` / `→` | Tourner à droite |
| `Espace` | Tirer |
| `Échap` | Pause / menu |
| `M` | Afficher / masquer la mini-carte |

## Technique

- Canvas 2D uniquement, JavaScript vanilla, aucun framework ni ressource réseau (~90 Ko).
- Raycasting DDA avec z-buffer, textures et sprites générés procéduralement au chargement.
- Résolution de rendu interne adaptative (ajustement automatique si les FPS descendent sous 40).
- Niveaux générés à chaque partie (labyrinthe par backtracking + boucles et salles creusées).
- Audio synthétisé à la volée avec la Web Audio API : séquenceur techno/drone/disco selon le niveau, et effets sonores.
- `DeviceOrientation` avec gestion de `requestPermission()` pour iOS 13+.
- Verrouillage du zoom, gestion des zones sûres (encoches) et message si l'appareil est en paysage.
