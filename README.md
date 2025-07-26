# Votación P2P en Tiempo Real

Una aplicación web sencilla y sin servidor (*serverless*) para crear votaciones en tiempo real y compartir con una audiencia, utilizando tecnología WebRTC para la comunicación directa entre pares (P2P).

## Descripción

Esta herramienta permite a un presentador crear una pregunta con múltiples opciones de respuesta y compartirla con los participantes a través de un código, un enlace directo o un código QR. Los resultados se actualizan en la pantalla del presentador en tiempo real a medida que se reciben los votos.

La principal característica de esta aplicación es que no requiere un servidor central para gestionar las votaciones, lo que garantiza la privacidad y la simplicidad. La comunicación se establece directamente entre el navegador del presentador (anfitrión) y los navegadores de los participantes (pares).

-----

## Características principales

  - **Creación de Votaciones:** Formula una pregunta y añade tantas opciones de respuesta como necesites.
  - **Sin Servidor (Serverless):** Utiliza WebRTC para una comunicación P2P, lo que significa que no hay bases de datos ni servidores intermedios.
  - **Compartir de Múltiples Formas:**
      - Código QR para un acceso rápido con la cámara del móvil.
      - Enlace directo para compartir por mensajería.
      - Código de sesión corto para introducción manual.
  - **Resultados en Tiempo Real:** Las barras de resultados se actualizan instantáneamente en la pantalla del presentador.
  - **Modo Proyección:** Una vista a pantalla completa optimizada para proyectores.
  - **Soporte Multilingüe:** Interfaz disponible en español, catalán, gallego y euskera, con detección automática del idioma del navegador.
  - **Fiabilidad Mejorada:** Sistema de confirmación y temporizador para asegurar que los votos no se pierdan por problemas de red.
  - **Preparación de Sesiones:** Genera un enlace para guardar una votación y lanzarla más tarde.
  - **Optimización de Recursos:** La conexión de cada participante se cierra tras votar para liberar recursos del presentador.

-----

## Cómo funciona

La aplicación se basa en la librería **PeerJS**, que simplifica el uso de la tecnología **WebRTC**.

1.  **Rol de Presentación:** Al crear una sesión, su navegador se convierte en el "anfitrión" de la sesión, generando un ID único.
2.  **Rol de Participante:** Al unirse, el navegador del participante utiliza ese ID para establecer una conexión directa P2P con el navegador del anfitrión.
3.  **Comunicación:** El anfitrión envía la pregunta y las opciones al participante. El participante envía su voto de vuelta al anfitrión.
4.  **Actualización:** El anfitrión recibe los votos, actualiza el conteo y su propia interfaz.

-----

## Cómo usar la aplicación

1.  **Abre el archivo `index.html`** en un navegador web.

### Para el presentador

1.  Haz clic en el enlace inferior para cambiar al **rol de presentación**.
2.  Escribe tu pregunta y al menos dos opciones de respuesta.
3.  Pulsa **"Iniciar Sesión"**.
4.  En la pantalla de resultados, comparte la sesión con tu audiencia utilizando cualquiera de los tres métodos proporcionados.
5.  Usa el botón **"Proyectar"** para mostrar los resultados a pantalla completa.

### Para el participante

1.  Al abrir la aplicación, verás la pantalla para unirte.
2.  Introduce el código de la sesión proporcionado por el presentador y pulsa **"Unirse"**.
3.  Alternativamente, escanea el código QR o abre el enlace directo que te hayan compartido.
4.  Selecciona tu respuesta. Una vez confirmado el voto, la conexión se cerrará.

-----

## Tecnologías utilizadas

  - **HTML5**
  - **Tailwind CSS** para el diseño de la interfaz.
  - **JavaScript (ES6)** para toda la lógica de la aplicación.
  - **PeerJS** como librería de abstracción sobre WebRTC.
  - **QRCode.js** para la generación de códigos QR.

-----

## Autor y Licencia

Aplicación creada por **Juan José de Haro** ([bilateria.org](https://bilateria.org)).

El código de esta aplicación se distribuye bajo la licencia [Creative Commons Reconocimiento-CompartirIgual 4.0 Internacional (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

![Logo de CC BY-SA](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)
