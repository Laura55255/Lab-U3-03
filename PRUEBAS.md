# Registro de pruebas

**Nota:** las pruebas se realizaron con los 8 registros ya cargados en `data.js`. P06 y P07 se hicieron modificando el arreglo de forma temporal y después se restauraron los 8 registros.

## Etapa básica

| Prueba | Acción y resultado esperado | Resultado obtenido | Estado | Corrección realizada |
|---|---|---|---|---|
| P01 Inicio | Se muestra Ana y "1 de 8" | Al abrir la página se mostró Ana Pérez y "Testimonio 1 de 8". | Aprobado | No requirió |
| P02 Siguiente | Desde Ana, Siguiente muestra Luis y "2 de 8" | Se mostró Luis García y "Testimonio 2 de 8". | Aprobado | No requirió |
| P03 Límite superior | Desde el último testimonio (Roberto, 8 de 8), Siguiente muestra Ana | Desde Roberto Salinas, Siguiente regresó a Ana Pérez (1 de 8). | Aprobado | No requirió |
| P04 Límite inferior | Desde Ana, Anterior muestra al último (Roberto) | Desde Ana Pérez, Anterior mostró a Roberto Salinas (8 de 8). | Aprobado | No requirió |
| P05 Aleatorio | Desde cualquier posición cambia a otra válida (repetir 10 veces) | En 10 intentos cambió siempre a un testimonio distinto del actual. La lógica suma un salto entre 1 y total − 1, por lo que no puede repetir. | Aprobado | No requirió |
| P06 Un registro | Con un solo objeto, los controles mantienen el registro y no hay errores | Con un solo objeto en data.js, los botones no cambiaron la tarjeta y no hubo errores en consola. | Aprobado | No requirió |
| P07 Sin registros | Con `[]` aparece el mensaje y no se muestran controles | Con el arreglo vacío apareció "No hay testimonios disponibles." sin controles. | Aprobado | No requirió |
| P08 Ampliación de datos | Con 8 registros, navegación completa y contador de ocho | Con los 8 registros, la navegación recorrió todos y el contador mostró "de 8". | Aprobado | No requirió |
| P09 Presentación | Tres anchos (320, 768, 1280), textos largos y teclado | Se revisó en los tres anchos sin desplazamiento horizontal. Con Tab se recorrieron los botones con foco visible y Enter/Espacio los activaron. | Aprobado | No requirió |
| P10 Compilación | `npm run build` sin errores; consola sin errores de aplicación | La compilación terminó sin errores y la consola no mostró errores de la aplicación. | Aprobado | No requirió |

## Ampliación con autoplay

| Prueba | Acción y resultado esperado | Resultado obtenido | Estado |
|--------|-----------------------------|--------------------|--------|
| A01 Activación | Reanudar inicia avances separados aproximadamente cinco segundos. | Al presionar Reanudar, el testimonio cambió cada ~5 segundos. | Aprobado |
| A02 Pausa | Pausar mantiene el testimonio al esperar más de cinco segundos. | Con Pausar, la tarjeta se mantuvo igual por más de 5 segundos. | Aprobado |
| A03 Acción manual | Anterior, Siguiente o Aleatorio cambian la tarjeta y dejan pausada la reproducción. | Los tres botones cambiaron la tarjeta y el botón volvió a mostrar Reanudar. | Aprobado |
| A04 Reanudación | Reanudar permite nuevos avances; repetir varias veces sin aceleración. | Pausé y reanudé varias veces y el ritmo se mantuvo en 5 segundos. | Aprobado |
| A05 Límites | Durante autoplay, el último vuelve al primero. | Del testimonio 8 de 8 pasó al 1 de 8. | Aprobado |
| A06 Pocos datos | Con cero o un registro no se crea un intervalo. | Con un solo registro desapareció el botón Pausar/Reanudar y no hubo avance. | Aprobado |
| A07 Limpieza | El return del efecto limpia el intervalo; no se acumulan al alternar pausa y reproducción. | El useEffect incluye `clearInterval(intervalo)` y no se aceleró al alternar. | Aprobado |

## Corrección realizada durante la publicación

**Problema:** al publicar en GitHub Pages desde la rama `main`, la página se veía en blanco.

**Causa:** GitHub Pages servía el código fuente sin compilar. El `index.html` del proyecto carga `/src/main.jsx`, que el navegador no puede ejecutar. Además, el sitio vive en la ruta `/Lab-U3-03/` y Vite no lo sabía.

**Solución:**
1. Se agregó `base: '/Lab-U3-03/'` en `vite.config.js`.
2. Se creó `.github/workflows/deploy.yml` para que GitHub Actions ejecute `npm run build` y publique la carpeta `dist`.
3. Se cambió la fuente de Pages a "GitHub Actions".

**Verificación:** el flujo terminó con palomita verde y el sitio https://laura55255.github.io/Lab-U3-03/ ya muestra la aplicación.