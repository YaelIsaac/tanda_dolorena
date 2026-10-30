# Tanda Doloreña · Flutter con TDD

**Materia:** Desarrollo Móvil Integral
**Universidad:** UTNG, Dolores Hidalgo
**Alumno:** González López Yael Isaac
**Fecha:** [fecha de entrega]

## Descripción

Sistema de ahorro rotativo (tanda) para un grupo de vecinos. Registra quién aportó en la ronda, solo deja cerrarla cuando todos aportaron, entrega el turno según el orden acordado y termina cuando todos ya recibieron el suyo. Toda la lógica está en Dart puro y se desarrolló con TDD (rojo, verde, refactor). La pantalla animada va al final, encima de reglas ya probadas.

## Estructura del proyecto

```
lib/
  modelos/        participante, tanda, cierre_ronda
  logica/         servicio_tanda y resultados (enums)
  presentation/   tanda_screen (pantalla animada)
  main.dart
test/
  servicio_tanda_test.dart
capturas/
```

![Estructura del proyecto](capturas/01_estructura.png)

## Cómo ejecutarlo

```
flutter pub get
flutter test
flutter run
```

## Reglas de negocio probadas

- Cada participante aporta una sola vez por ronda.
- Solo aporta quien pertenece a la tanda.
- La ronda se cierra únicamente cuando todos aportaron.
- Al cerrar, el turno va a quien indica el orden acordado y se avanza al siguiente.
- Cuando todos recibieron su turno, la tanda termina y no acepta más aportaciones.

## Pruebas realizadas

| # | Prueba | Qué verifica |
|---|---|---|
| 1 | Registrar una aportación válida | La aportación se agrega a la ronda actual |
| 2 | Aportación repetida | Devuelve `yaAporto` |
| 3 | Participante desconocido | Devuelve `participanteInvalido` |
| 4 | `puedeCerrarRonda` con faltantes | Es falso si falta alguien |
| 5 | `puedeCerrarRonda` con todos | Es verdadero cuando todos aportaron |
| 6 | Cerrar ronda | Entrega el turno al beneficiario correcto y avanza |
| 7 | Cerrar con faltantes | Devuelve `faltanAportaciones` y no avanza el turno |
| 8 | `haTerminado` al inicio | Es falso mientras hay turnos pendientes |
| 9 | `haTerminado` al final | Es verdadero cuando todos recibieron turno |
| 10 | Aportar con tanda terminada | Devuelve `tandaTerminada` |
| 11 | Simulación completa | Beneficiarios en orden p1, p2, p3 y tanda cerrada |
| 12 | Cerrar con tanda terminada | Devuelve `tandaYaTermino` (extra, evita errores en la pantalla) |

### Todas las pruebas en verde

![Pruebas en verde](capturas/02_pruebas.png)

## Evidencia de la aplicación

### Pantalla inicial
![Pantalla inicial](capturas/03_pantalla_inicial.png)

### Aportaciones a medias
![Aportaciones a medias](capturas/04_aportaciones.png)

### Cierre sin que todos aporten
![Cierre con faltantes](capturas/05_cierre_con_faltantes.png)

### Turno entregado
![Turno entregado](capturas/06_turno_entregado.png)

## Ciclo TDD (opcional)

![Prueba en rojo](capturas/07_prueba_roja.png)

![Tanda terminada](capturas/08_tanda_terminada.png)

## Conclusiones

[Escribe 3 o 4 líneas con tus palabras: qué aprendiste de TDD y de separar la lógica de la pantalla.]
