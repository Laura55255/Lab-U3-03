# Testimonios con React

Práctica inicial de React – Ingeniería de Software, Unidad 3 (AGO–DIC 2026), TecNM Celaya.

**Integrante:** Laura Beatriz Ruiz Oros
**Etapa terminada:** Básica + ampliación con autoplay
**Versiones:** Node v24.11.1 · npm 11.6.2
**Sitio publicado:** https://laura55255.github.io/Lab-U3-03/

## Instalación y ejecución

    npm install
    npm run dev
    npm run build

Con la configuración de GitHub Pages, la dirección local de desarrollo es
`http://localhost:5173/Lab-U3-03/`.

## Estructura

- `src/data.js`: datos de los testimonios (ficticios).
- `src/components/Testimonial.jsx`: presenta una tarjeta.
- `src/components/Controls.jsx`: botones; comunica las acciones con callbacks.
- `src/App.jsx`: conserva el estado (`index`) y coordina los componentes.
- `src/styles.css`: estilos.
- `vite.config.js`: configuración de Vite, incluye `base` para GitHub Pages.
- `.github/workflows/deploy.yml`: compila y publica el sitio automáticamente.

## Decisiones principales

- `App` guarda el estado `index` y los hijos solo reciben props. Así hay un único
  lugar que decide qué testimonio se muestra, `Testimonial` solo presenta datos y
  `Controls` solo avisa qué botón se presionó.
- El botón Aleatorio suma al índice actual un salto entre 1 y `total - 1`, con
  módulo `total`. Así nunca cae en el mismo testimonio cuando hay dos o más.
- Con cero registros se muestra un mensaje y no se renderizan tarjeta ni
  controles. Con un registro, los botones no cambian nada y no se muestra
  Pausar/Reanudar.
- Para publicar en GitHub Pages se agregó `base: '/Lab-U3-03/'` en Vite y un
  flujo de GitHub Actions que ejecuta `npm run build` y publica `dist`.

## Pruebas

Etapa básica (P01 a P10) y ampliación (A01 a A07): ver [PRUEBAS.md](PRUEBAS.md).

## Autoplay con useEffect

La ampliación agrega reproducción automática cada 5 segundos, con los botones
Pausar y Reanudar. El efecto crea un `setInterval` solo cuando `reproduciendo`
es verdadero y hay al menos dos registros. La función de limpieza
(`clearInterval`) elimina el intervalo antes de ejecutar de nuevo el efecto y al
desmontar el componente. Así no se acumulan temporizadores ni se acelera el
avance. Al usar Anterior, Siguiente o Aleatorio, la reproducción se pausa y
solo Reanudar la activa otra vez.