# Registro de pruebas

## Etapa básica

| Prueba | Acción y resultado esperado | Resultado obtenido | Estado | Corrección realizada |
|---|---|---|---|---|
| P01 Inicio | Se muestra Ana y "1 de 3" | | | |
| P02 Siguiente | Desde Ana, Siguiente muestra Luis y "2 de 3" | | | |
| P03 Límite superior | Desde María, Siguiente muestra Ana | | | |
| P04 Límite inferior | Desde Ana, Anterior muestra María | | | |
| P05 Aleatorio | Desde cualquier posición cambia a otra válida (repetir 10 veces) | | | |
| P06 Un registro | Con un solo objeto, los controles mantienen el registro y no hay errores | | | |
| P07 Sin registros | Con `[]` aparece el mensaje y no se muestran controles | | | |
| P08 Ampliación de datos | Con 8 registros, navegación completa y contador de ocho | | | |
| P09 Presentación | Tres anchos (320, 768, 1280), textos largos y teclado | | | |
| P10 Compilación | `npm run build` sin errores; consola sin errores de aplicación | | | |

## Ampliación con Autoplay 
## Pruebas de la ampliación (autoplay)

| Prueba | Acción y resultado esperado | Resultado obtenido | Estado |
|--------|-----------------------------|--------------------|--------|
| A01 Activación | Reanudar inicia avances separados aproximadamente cinco segundos. | Al presionar Reanudar, el testimonio cambió cada ~5 segundos. | Aprobado |
| A02 Pausa | Pausar mantiene el testimonio al esperar más de cinco segundos. | Con Pausar, la tarjeta se mantuvo igual por más de 5 segundos. | Aprobado |
| A03 Acción manual | Anterior, Siguiente o Aleatorio cambian la tarjeta y dejan pausada la reproducción. | Los tres botones cambiaron la tarjeta y el botón volvió a mostrar Reanudar. | Aprobado |
| A04 Reanudación | Reanudar permite nuevos avances; repetir varias veces sin aceleración. | Pausé y reanudé varias veces y el ritmo se mantuvo en 5 segundos. | Aprobado |
| A05 Límites | Durante autoplay, el último vuelve al primero. | Del testimonio 8 de 8 pasó al 1 de 8. | Aprobado |
| A06 Pocos datos | Con cero o un registro no se crea un intervalo. | Con un solo registro desapareció el botón Pausar/Reanudar y no hubo avance. | Aprobado |
| A07 Limpieza | El return del efecto limpia el intervalo; no se acumulan al alternar pausa y reproducción. | El useEffect incluye `clearInterval(intervalo)` y no se aceleró al alternar. | Aprobado |