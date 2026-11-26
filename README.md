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

## Contra la PC u online
- **Online con compañeros:** si en tu equipo hay más de uno, los jugadores se reparten (el arquero le toca a uno al azar). Los tuyos dicen *VOS*; los de tu compañero, *J1*, *J2*… El rival no ve esas marcas.
- Al abrir aparece el menú (☰): elegí el nivel de la PC (fácil, medio o difícil), *Jugar contra la PC* o *Jugar online*. La primera vez hay un tutorial corto.
- **Canchas:** clásica, estadio, nieve, potrero (tierra y arcos de palos), calle y Paladino (tribunas rojas y amarillas). Se eligen solo online (la elige el que crea la partida); contra la PC se juega en la clásica. Solo cambia cómo se ve.
- **👥 Jugar online → ➕ Crear partida:** elegís cuántos contra cuántos (de 1 a 5 personas por equipo, por defecto 1 vs 1), en qué equipo jugás, cuánto dura (5, 8, 10, 12 o 16 minutos; por defecto 10), la cancha y si es privada. El partido no arranca hasta que estén todos.
- **Partidas creadas:** la lista muestra las que esperan gente y cuántos faltan; al entrar elegís equipo entre los que tienen lugar. 
- **Cupo:** en cada equipo entran como máximo las personas que eligió el creador; si dos entran al último lugar a la vez, el segundo vuelve a elegir.
- **✕ arriba a la izquierda:** salir del partido. Si tenías compañeros, tus jugadores pasan a ellos.
- **Solo conexión directa:** el partido arranca cuando todos los jugadores tienen conexión directa (⚡) con el creador; la sala muestra ✅/⏳ por jugador. Si a los 20 s alguno no la logra, se avisa quién (mejor wifi y sin VPN) y el creador puede tocar *Jugar igual por servidor*. Si en pleno partido se corta la directa de alguien, el partido se pausa hasta que vuelva. (Dentro de Claude no hay conexión directa, así que ahí no se exige.)
- **Mirar partidos:** cuando el partido ya empezó, en *Partidos en juego* tocá *👁 Mirar* para entrar como espectador (también en una privada con el código). Ves todo pero no manejás jugadores; a los que juegan les avisa que se unió un espectador. Aparecés como un muñeco al costado de la cancha y con *💬 Hablar* le decís cosas a los jugadores en un globito arriba de tu cabeza.
- **Privada:** no aparece en la lista; mandá el link o el código (*Entrar a una partida privada con código*). Los del mismo equipo se reparten los jugadores; si alguien se va, los suyos los juega la PC.
- El online manda solo las jugadas (movimientos y pases), y cada teléfono calcula el partido igual, así que todos ven exactamente lo mismo.
- Las jugadas viajan por un servidor MQTT público y gratuito (sin cuentas). A una sala privada puede entrar cualquiera que sepa el código, así que usá uno propio.

El juego se conecta a los tres servidores públicos a la vez (usa el que responda más rápido) y, si la red lo permite, abre una conexión directa entre los teléfonos (arriba dice "⚡ directo"); si no, sigue por los servidores ("☁ servidor").
