[English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Português (Brasil)](README.pt-BR.md) · [日本語](README.ja.md)

# Haunted Hearts — Juego cooperativo de puzles de Halloween

👻 Dos fantasmas, dos medios corazones y una sola linterna. Acompaña a Luna y Rose por ocho habitaciones encantadas donde ayudar al otro abre el camino a casa. Puedes controlar a ambos personajes o compartir un dispositivo y decidir los movimientos en compañía.

**[Jugar ahora](https://halloween-love-game.crazy3d.org/)** · [Ver los 12 juegos de Halloween](https://github.com/AshinTop/halloween-games) · [⭐ Dar una estrella en GitHub](https://github.com/AshinTop/halloween-love-game)

El README está disponible en cinco idiomas. La **interfaz del juego solo ofrece inglés y chino simplificado**.

![Puzle de Halloween Haunted Hearts con Luna, Rose, corazones de colores, puertas y una linterna compartida](docs/images/gameplay.jpg)

## Qué lo hace especial

- Ocho habitaciones de una sola pantalla introducen puertas, caminos personales y el intercambio de la linterna.
- Dos fantasmas independientes, cada uno con su medio corazón y su arco de salida.
- Deshacer sin límite, reiniciar y pedir una pista calculada desde la posición actual.
- Récords de movimientos y enlaces a habitaciones para volver a los retos favoritos.
- Escenarios SVG originales, sonido sintetizado opcional, controles táctiles y de teclado, y movimiento reducido.

## Cómo jugar

Selecciona a Luna o Rose y recoge el medio corazón de cada personaje. Luna usa las casillas azules de luna y termina en el arco azul; Rose usa las casillas rosas y su arco correspondiente. Para completar la habitación, ambos deben tener su corazón y estar en su propia salida. No pueden compartir una casilla.

Las placas de luna y estrella mantienen abiertas las puertas correspondientes **mientras alguien esté encima**. Antes de abandonar una placa, comprueba si tu compañero necesita cruzar. En algunas habitaciones puede relevarte desde otra placa.

Solo quien lleva la linterna puede **entrar en la niebla**. Pásala cuando los fantasmas estén uno al lado del otro. Un fantasma que ya está dentro de la niebla puede salir después de entregarla: ese detalle permite resolver varios cruces.

Las ocho habitaciones avanzan desde un encuentro sencillo hasta combinaciones de puertas, pasillos y luz compartida. No hay reloj ni límite de movimientos. Las rutas iniciales más cortas verificadas son de **8, 18, 22, 20, 19, 24, 28 y 30 movimientos**; son una meta para repetir, no una condición para ganar.

## Controles

| Acción | Cómo hacerlo |
| --- | --- |
| Elegir personaje | Clic en el retrato o fantasma; **Q** alterna |
| Moverse | Flechas / **WASD**, botones de dirección o una casilla adyacente |
| Pasar la linterna | **L** o el botón correspondiente, estando juntos |
| Deshacer | **Z** o **Undo** |
| Pista, reinicio y habitación | Botones del juego |

## Un poco de estrategia

Coloca primero al personaje que ayuda a abrir la puerta. Deja espacio para que ambos puedan acercarse al pasar la linterna. Una pista selecciona al fantasma adecuado y explica el siguiente paso de una ruta más corta desde el **estado actual**, sin ejecutarlo. Si ya no existe una salida, deshaz movimientos o reinicia.

## Progreso y enlaces de desafío

Los mejores resultados por habitación y las preferencias de idioma y sonido se guardan en este navegador. Recargar reinicia la habitación seleccionada; no recupera los movimientos de una partida sin terminar. Los registros no se sincronizan entre dispositivos.

El enlace a la [habitación 6](https://halloween-love-game.crazy3d.org/#room=6), por ejemplo, empieza ese reto desde el principio. Compartir copia tu resultado real y el enlace, sin subir una repetición. Si falla el portapapeles, aparece el texto para copiarlo manualmente.

## Capturas y presentación en vídeo

![Haunted Hearts en una ventana compacta con selección de personajes y botones de dirección visibles](docs/images/mobile.jpg)

Captura real dentro de un iframe compacto. Muestra la distribución en una ventana pequeña, no una prueba en un teléfono físico.

[Reproductor y transcripción](https://halloween-love-game.crazy3d.org/intro.html) · [Descargar el MP4](docs/media/intro.mp4)

La **presentación de 24 segundos, sin sonido**, combina capturas reales y rótulos. Es un recorrido visual, no una partida grabada de forma continua ni una muestra de audio.

## Preguntas frecuentes

### ¿Necesito otra persona?

Puedes resolver las ocho habitaciones a solas, alternando personajes. Dos personas también pueden turnarse en un mismo dispositivo; no hay multijugador a distancia.

### ¿Por qué se cerró la puerta o no puedo entrar en la niebla?

Una puerta necesita su placa ocupada. Para entrar en niebla hay que llevar la linterna. Revisa ambas condiciones antes de mover al ayudante.

### ¿Es una calculadora de amor?

Es un juego de lógica cooperativa con corazones y fantasmas. No solicita nombres ni calcula compatibilidad o puntuaciones de pareja.

## Ejecutar en local e insertar el juego

Sirve la raíz del repositorio mediante HTTP:

```sh
python3 -m http.server 4173
```

Abre **http://localhost:4173/**. No requiere compilación ni dependencias. Usa HTTP: `file://` puede bloquear los módulos JavaScript.

Ejecuta las comprobaciones incluidas con Node:

```sh
npm test
```

Las pruebas cubren rutas completas de las ocho habitaciones, colisiones, casillas personales, placas, puertas, linterna, niebla y enlaces de habitación inválidos.

```html
<iframe src="https://halloween-love-game.crazy3d.org/?embed=1"
  title="Haunted Hearts"
  style="display:block;width:100%;height:521px;border:0"
  allow="fullscreen" allowfullscreen></iframe>
```

El escenario principal mide aproximadamente **833×521** en escritorio. También se revisaron ventanas de **356×280**, **326×280**, **390×650** y **844×340**. Usa los botones de dirección en marcos muy bajos; una altura de **480 px o más** resulta más cómoda en móvil cuando sea posible. El iframe activa la presentación compacta; `?embed=0` recupera la página completa.

Consulta [EMBEDDING.md](EMBEDDING.md) para tamaño, almacenamiento, foco y permisos. Mide la altura restante después de la barra del sitio anfitrión.

## Más pequeñas aventuras de Halloween

- **[Moonlit Mirrors](https://halloween-mirror-hearts.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-mirror-hearts) — Guía a dos fantasmas a la vez por tableros reflejados.
- **[Ghost Lanterns 3D](https://halloween-3d.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-3d) — Enciende un jardín de calabazas con lógica Lights Out y vínculos de almas.
- **[Witch’s Candy Blocks](https://halloween-block-blast.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-block-blast) — Encaja dulces en un tablero de 8×8 y completa pedidos de pociones.
- **[Pumpkin Jam](https://halloween-sprunki.crazy3d.org/)** · [Código](https://github.com/AshinTop/halloween-sprunki) — Crea una banda de cuatro partes y prueba tu oído con Ghost Echo.

## Créditos y apoyo

Creado para **AshinTop** y **Midnight Candy Club** con diseño, programación y revisión dirigidos por personas y asistidos por IA. Arte y sonidos sintetizados originales del proyecto. No necesita cuenta remota; el alojamiento puede añadir scripts o registros de solicitudes.

¿Te ha gustado? **[Dale una estrella en GitHub](https://github.com/AshinTop/halloween-love-game)**. Para informar de errores, incluye navegador, tamaño del iframe, enlace y pasos para reproducirlos.
