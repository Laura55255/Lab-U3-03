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

| ID | Prueba | Resultado esperado | Resultado obtenido | Estado | Corrección |
|:---:|---|---|---|:---:|---|
| A01 | Activación | Reanudar inicia avances cada 5 segundos. | | | |
| A02 | Pausa | Pausar mantiene el testimonio actual por más de 5 segundos. | | | |
| A03 | Acción manual | Anterior, Siguiente y Aleatorio cambian la tarjeta y pausan el autoplay. | | | |
| A04 | Reanudación | Reanudar continúa los avances sin acelerar ni duplicar intervalos. | | | |
| A05 | Límites | El último testimonio regresa al primero automáticamente. | | | |
| A06 | Pocos datos | Con cero o un registro no se crea ningún intervalo. | | | |
| A07 | Limpieza | El return del efecto elimina el intervalo anterior al pausar o reanudar. | | | |