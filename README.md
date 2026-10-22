# Blokový vesmír — interaktívna vizualizácia

Keď sa pohyb v dvoch rozmeroch zmení na statickú geometriu v troch.

**Živá stránka:** https://tw9mini.github.io/blokovy-vesmir/

## Čo to je

Jednostránkový Three.js experiment, ktorý krok za krokom ukazuje, ako z
dvojrozmerného sveta pohybujúceho sa v čase vznikne blokový vesmír
(block universe) — štvorrozmerná „kocka“, v ktorej je celá história
naraz prítomná ako geometria.

## Ako to funguje

1. **01 / 05 — Dvojrozmerný svet** — Slnko a dve planéty sa pohybujú v rovine.
2. **02 / 05 — Zastavený okamih** — jedna ohraničená „karta“ = celý vesmír v jednom čase.
3. **03 / 05 — Skladanie snímok** — karty sa skládajú na seba ako balíček.
4. **04 / 05 — Spojitý časopriestor** — nekonečne veľa snímok dá súvislé svetové trubice.
5. **05 / 05 — Blokový vesmír** — celá história je jeden statický geometrický blok.

Po úvode (62 s, dá sa preskočiť) sa spustí interaktívny režim:

- slider **Časový okamih** odhaľuje históriu po zvolený čas (orezávacia rovina)
- **PIP** vpravo dole ukazuje zodpovedajúci 2D rez časopriestorom
- myš otáča scénu, koliesko približuje, dvojklik vycentruje

## Spustenie lokálne

Stránka je čisté statické HTML — stačí ju obslúžiť cez HTTP (kvôli
ES modulom a import mapám), nie cez `file://`:

```sh
python3 -m http.server 8000
# -> http://localhost:8000/
```

## Technika

- `index.html` — jediná aplikácia, bez buildu, bez bundleru
- [three.js 0.164.1](https://threejs.org/) cez CDN import map (žiadne `node_modules`)
- svetové trubice sú orezané jednou vodorovnou rovinou (`clippingPlanes`),
  takže odhaľovanie času je skutočný orez geometrie, nie animácia
