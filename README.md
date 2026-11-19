# Tanda Doloreña con TDD · Flutter

**Materia:** Desarrollo Móvil Integral
**Universidad:** UTNG, Dolores Hidalgo
**Profesor:** Anastacio Rodríguez García
**Alumno:** González López Yael Isaac
**Fecha:** 18 - noviembre - 2026

## Descripción

App de tanda (ahorro rotativo vecinal) para un grupo de vecinos de Dolores Hidalgo. Registra quién ya aportó en la ronda actual, solo deja cerrar la ronda cuando todos aportaron, entrega el turno según el orden acordado y avanza al siguiente. Cuando todos ya recibieron su turno, la tanda termina y no acepta más aportaciones. Toda la lógica está en Dart puro y se desarrolló con TDD (prueba en rojo, código en verde, refactor); la interfaz animada es la última capa.

## Estructura del proyecto

![Estructura del proyecto](capturas/01_estructura.jpeg)

## Pruebas de casos (éxito y fallo) · `test/servicio_tanda_test.dart`

### Prueba 1: registrar una aportacion valida la agrega a la ronda actual

#### Éxito
![Prueba 1 éxito](capturas/02_prueba_01_exito.png)

#### Fallo
![Prueba 1 fallo](capturas/02_prueba_01_fallo.png)

### Prueba 2: un participante no puede aportar dos veces en la misma ronda

#### Éxito
![Prueba 2 éxito](capturas/02_prueba_02_exito.png)

#### Fallo
![Prueba 2 fallo](capturas/02_prueba_02_fallo.png)

### Prueba 3: alguien que no pertenece a la tanda no puede aportar

#### Éxito
![Prueba 3 éxito](capturas/02_prueba_03_exito.png)

#### Fallo
![Prueba 3 fallo](capturas/02_prueba_03_fallo.png)

### Prueba 4: puedeCerrarRonda es falso si falta algun participante por aportar

#### Éxito
![Prueba 4 éxito](capturas/02_prueba_04_exito.png)

#### Fallo
![Prueba 4 fallo](capturas/02_prueba_04_fallo.png)

### Prueba 5: puedeCerrarRonda es verdadero cuando todos ya aportaron

#### Éxito
![Prueba 5 éxito](capturas/02_prueba_05_exito.png)

#### Fallo
![Prueba 5 fallo](capturas/02_prueba_05_fallo.png)

### Prueba 6: cerrar la ronda entrega el turno al beneficiario y avanza

#### Éxito
![Prueba 6 éxito](capturas/02_prueba_06_exito.png)

#### Fallo
![Prueba 6 fallo](capturas/02_prueba_06_fallo.png)

### Prueba 7: no se puede cerrar la ronda si algun participante no ha aportado

#### Éxito
![Prueba 7 éxito](capturas/02_prueba_07_exito.png)

#### Fallo
![Prueba 7 fallo](capturas/02_prueba_07_fallo.png)

### Prueba 8: haTerminado es falso mientras queden turnos pendientes

#### Éxito
![Prueba 8 éxito](capturas/02_prueba_08_exito.png)

#### Fallo
![Prueba 8 fallo](capturas/02_prueba_08_fallo.png)

### Prueba 9: haTerminado es verdadero cuando todos ya recibieron su turno

#### Éxito
![Prueba 9 éxito](capturas/02_prueba_09_exito.png)

#### Fallo
![Prueba 9 fallo](capturas/02_prueba_09_fallo.png)

### Prueba 10: no se puede aportar una vez que la tanda ha terminado

#### Éxito
![Prueba 10 éxito](capturas/02_prueba_10_exito.png)

#### Fallo
![Prueba 10 fallo](capturas/02_prueba_10_fallo.png)

### Prueba 11: simulacion completa: 3 vecinas completan una tanda de principio a fin

#### Éxito
![Prueba 11 éxito](capturas/02_prueba_11_exito.png)

#### Fallo
![Prueba 11 fallo](capturas/02_prueba_11_fallo.png)

## Todas las pruebas juntas

![Todas las pruebas en verde](capturas/03_todas_las_pruebas.png)

## Evidencia de la aplicación

### Pantalla inicial
![Pantalla inicial](capturas/04_pantalla_inicial.jpeg)

### Todos aportaron
![Todos aportaron](capturas/05_todos_aportaron.jpeg)

### Cierre de ronda y entrega del turno
![Cierre de ronda](capturas/06_cierre_ronda.jpeg)

### Tanda terminada
![Tanda terminada](capturas/07_tanda_terminada.jpeg)