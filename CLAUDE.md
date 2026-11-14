# Partidito — contexto para Claude Code

Juego web de fútbol táctico 5 contra 5 para celular. Todo vive en un solo archivo: `index.html` (HTML + CSS + JS, sin dependencias ni build). Se publica con GitHub Pages desde `main` (raíz).

El dueño escribe en español rioplatense (Uruguay); respondé y escribí los textos del juego en ese español.

## Reglas del juego (pedidas por el dueño)
- Cancha completa en vertical (105 × 68 m), vista desde arriba. Para el equipo rojo la vista se da vuelta (siempre defendés abajo).
- 5 por equipo: índices 0–4 celeste (0 = arquero), 5–9 rojo (5 = arquero).
- Los jugadores **no se mueven solos**: solo recorren la línea que el usuario dibuja arrastrándolos.
- La pelota **se pega** apenas toca el borde de un jugador (`RST`, arquero en su área `RKP`).
- El que tiene la pelota no se mueve; los rivales se frenan a `S.cfg.bl` m de él (por defecto 5) y solo pueden cortar pases.
- Ajustes (botón ⚙): distancia de marca `S.cfg.bl` (2–10 m) y potencia máxima `S.cfg.pm` (60–140 %) viajan como acción `{k:'c'}` y valen para todo el partido online; el tiempo de carga del pase `CFG.ch` es local (localStorage `pt_cfg`).
- Pase: tocar al que tiene la pelota → tocar y mantener el destino; el tiempo apretado es la potencia (llega al máximo en `CFG.ch` s, por defecto 1,1). Velocidad `VMIN`..`VMAX*S.cfg.pm`, frenado constante `AB`.
- Saque del medio (`S.ko`): el rival no cruza la mitad hasta el primer pase del que saca.
- Saque de arco (`S.gk`): el rival no entra al área grande hasta que saca el arquero.
- Hay goles, laterales, córners y saques de arco (`restartSim`).

## Arquitectura de `index.html`
- **Simulación determinista** (`stepSim`, `applyAct`, `newState`, `cloneS`): paso fijo de 1/60 s. Mismos eventos ⇒ mismo partido en todos los teléfonos. No usar `Math.hypot`, trigonometría ni azar dentro de la simulación (solo `Math.sqrt`); la IA y el dibujo pueden usar lo que quieran.
- **Eventos** (`act`, `insertEvent`, `advanceTo`, `rollback`): cada acción (`{k:'m', i, path}` mover, `{k:'p', i, tx, ty, pw}` pasar) lleva un `tick`. Si llega tarde, se rebobina con el historial `G.hist` y se recalcula.
- **IA** (`aiThink`): juega los equipos sin humanos (contra la PC, o equipo vacío en el online). Corre cada 30 ticks y genera acciones normales.
- **Online** (`NET`, `netConnect`, `netJoin`, `onMsg`, `netTick`):
  - En GitHub Pages: sala por código (`#codigo` en la URL) sobre brokers MQTT públicos por WebSocket (`mqttRoom`, cliente MQTT 3.1.1 mínimo escrito a mano).
  - Dentro de Claude (artifact): capacidad `room` de Claude (`window.claude.use('room')`), mensajes por `presence`.
  - El primero que entra es el anfitrión: lleva el reloj (`hb`), reprograma las acciones de los clientes (`in` → `ev`) y manda una foto del estado cada 1,5 s (`snap`) para corregir diferencias.
  - Los del mismo equipo comparten los jugadores.
- **Pantalla/toques**: `draw`, `toS`/`toF` (campo ↔ pantalla), `pointerdown/move/up`, panel online (`panel`).
- `window.__T` expone internos para pruebas (`G`, `act`, `advanceTo`, `aiThink`, `blocked`, `netConnect`, `netJoin`…).

## Cómo probar
- Abrir `index.html` en un navegador con vista de celular (390 × 844).
- Pruebas automáticas usadas: Playwright con Chrome; para el online, dos contextos de navegador separados y un broker MQTT local por WebSocket, con `window.__BROKERS=['ws://127.0.0.1:8899/mqtt']` inyectado antes de cargar. Se comparó el estado `G.hist.get(tick)` en los dos y tiene que ser idéntico.

## Historia
Empezó como un juego 3D donde dos dedos eran las piernas; el dueño lo simplificó a este juego táctico 2D porque el online en tiempo real no se veía igual en todos los teléfonos.
