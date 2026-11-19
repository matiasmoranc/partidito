# Partidito ⚽

Fútbol táctico 5 contra 5 para el celular, en 3D low-poly (con estadio, hinchada y jugadores animados) o como mapa 2D. Un solo archivo HTML, sin librerías.

**Jugar:** https://matiasmoranc.github.io/partidito/

## Cómo se juega
- **Cámara:** arrastrá el pasto (donde no hay jugadores) con un dedo para mirar cualquier parte de la cancha; *⌖ pelota* vuelve a seguir la pelota (también vuelve sola después de un gol). Pellizcá con dos dedos para acercar o alejar (en la PC: ruedita del mouse o las teclas + y -). El botón 🎥 vuelve a los zooms fijos (cerca, medio, lejos) o pasa al mapa 2D. El botón ⛶ pone pantalla completa y tocándolo otra vez se sale (en iPhone: Compartir → Agregar a inicio). En ⚙ elegís la cámara de costado (como en la tele) o desde atrás.
- **Movimientos:** los jugadores corren, preparan el pase llevando la pierna atrás (más recorrido y brazos abiertos en los pases largos), paran la pelota y la apoyan bajo la suela; el arquero la agarra con las manos y se tira en los penales. En los goles la pelota entra y mueve la red; si sale, sigue de largo.
- **Mover jugadores:** arrastrá un jugador tuyo: va a recorrer exactamente la línea que dibujaste. Los jugadores no se mueven solos. Si lo tocás mientras corre, se frena ahí. Si tocás la pelota suelta, sale a buscarla el tuyo que llega primero.
- **La pelota se pega:** apenas toca el borde de un jugador (de cualquier equipo), queda en sus pies.
- **Zona del que tiene la pelota:** los rivales se frenan a 5 m del que la tiene y solo pueden cortar pases. Los compañeros se frenan 1,5 m más lejos.
- **El arquero sí puede ir a sacarla:** si el arquero rival toca la pelota del que la tiene, es suya.
- **Saque del medio:** el rival no puede cruzar la mitad de la cancha hasta que el equipo que saca haga el primer pase.
- **Saque de arco:** el rival no puede entrar al área grande hasta que el arquero saque.
- **Pasar o patear:** tocá una vez al que tiene la pelota, después tocá y mantené el lugar adonde querés pasarla. Cuanto más mantenés, más fuerte (con un máximo). Mientras mantenés ves hasta dónde va a llegar.
- **10 segundos:** el que tiene la pelota tiene 10 s para pasarla (el anillo de color alrededor). Si no, lateral para el rival a la altura de la pelota.
- **Partido con reloj:** dos tiempos de 5 minutos. Si empatan, 2 minutos de alargue y después penales. Al final, *Revancha*.
- **Penales:** el que patea toca al pateador y mantiene apretado en el arco; el que ataja toca adónde se tira su arquero (el rival no lo ve).
- Hay goles, laterales, córners y saques de arco.
- **⚙ Ajustes:** distancia de marca del rival, potencia máxima del pase y tiempo de carga del pase.

## Contra la PC u online
- Al abrir aparece el menú (☰): elegí el nivel de la PC (fácil, medio o difícil), *Jugar contra la PC* o *Jugar online*. La primera vez hay un tutorial corto.
- **👥 ONLINE → ⚡ Partida rápida:** entra a una sala abierta si hay alguna; si no, crea una y jugás contra la PC hasta que entre alguien.
- **Salas abiertas:** la lista muestra las salas que están esperando gente; tocá *Entrar* y te pone en el equipo con menos personas. *Crear sala abierta* abre una nueva que todos ven.
- **Sala privada con código:** no aparece en la lista; mandá el link para que entren. Los del mismo equipo comparten los jugadores; un equipo sin personas lo juega la PC.
- El online manda solo las jugadas (movimientos y pases), y cada teléfono calcula el partido igual, así que todos ven exactamente lo mismo.
- Las jugadas viajan por un servidor MQTT público y gratuito (sin cuentas). A una sala privada puede entrar cualquiera que sepa el código, así que usá uno propio.
