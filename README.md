# Testimonios con React

Práctica inicial de React – Ingeniería de Software, Unidad 3 (AGO–DIC 2026), TecNM Celaya.

**Integrante:** [tu nombre completo]
**Etapa terminada:** [Básica / Básica + ampliación con autoplay]
**Versiones:** Node [v...] · npm [...]

## Instalación y ejecución

    npm install
    npm run dev
    npm run build

## Estructura

- `src/data.js`: datos de los testimonios (ficticios).
- `src/components/Testimonial.jsx`: presenta una tarjeta.
- `src/components/Controls.jsx`: botones; comunica las acciones con callbacks.
- `src/App.jsx`: conserva el estado (`index`) y coordina los componentes.
- `src/styles.css`: estilos.

## Decisiones principales

- [Por qué App guarda el estado y los hijos solo reciben props.]
- [Cómo funciona el botón Aleatorio y por qué no repite el actual.]
- [Cómo se manejan los casos de cero y un registro.]

## Pruebas

Ver [PRUEBAS.md](PRUEBAS.md).