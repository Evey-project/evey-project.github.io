# evey-project.github.io

Site GitHub Pages de l'organisation Evey-project, servi à la racine de
https://evey-project.github.io/.

## Contenu

- `index.html` - page d'accueil minimale du projet.
- `cast-receiver.html` + `assets/` - le **Web Receiver Google Cast custom**
  d'Evey (URL à déclarer dans la Google Cast Console). Il sonde les capacités
  réelles du Chromecast, re-négocie le flux avec l'instance Evey de
  l'utilisateur et décode l'AC-3/E-AC-3 sur la TV via ac3go (WebAssembly).
- `wasm/` - le décodeur ac3go compilé en WebAssembly et son worker.
  Licence : PolyForm Noncommercial (voir `wasm/ac3go.LICENSE.md`).

## Regénérer

Depuis le dépôt evey :

```bash
docker exec evey-web sh -c 'cd /app && pnpm --filter web run build:cast-receiver'
cp -r frontend/apps/web/dist-cast-receiver/* <ce-repo>/
cp -r frontend/apps/web/public/wasm <ce-repo>/wasm
```
