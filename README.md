# Prototype AprilTag iPhone — tag36h11 40 mm

## Test rapide
1. Héberger ce dossier sur un site HTTPS (GitHub Pages, Netlify, Cloudflare Pages, etc.).
2. Ouvrir l'URL dans Safari sur iPhone.
3. Toucher **Démarrer la caméra** et autoriser l'accès.
4. Présenter un AprilTag `tag36h11` imprimé avec une taille de détection de 40 mm.

## Important sur la précision
La V1 utilise une approximation du champ de vision (~65°) pour calculer `fx/fy`. La détection/ID et le contour sont exploitables pour une démo, mais X/Y/Z et la distance sont explicitement des estimations. Pour une pose métrique précise, remplacer cette approximation par les intrinsèques calibrés de la caméra utilisée.

## Dépendance
Le HTML charge `apriltag_wasm.js` depuis la démo ARENA XR. Pour une version de présentation totalement autonome, copier `apriltag_wasm.js` et `apriltag_wasm.wasm` dans ce dossier et remplacer la balise `<script src=...>` par `src="./apriltag_wasm.js"`.

## Réglages principaux
Dans `index.html` :
- `TAG_SIZE=.04` : taille du tag en mètres.
- `PROC_W=640` : largeur d'analyse, compromis vitesse/distance de détection sur iPhone.
- `65` : approximation du champ de vision horizontal utilisée pour la V1.
