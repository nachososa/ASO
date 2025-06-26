# Planificación de Procesos | TP

## ¿Qué es la planificación de procesos?

La **planificación de procesos** es una función del sistema operativo que decide **qué proceso se ejecuta y cuándo**, entre todos los procesos que están listos para usar la CPU.  
El objetivo es **aprovechar eficientemente el procesador** y ofrecer un buen rendimiento al usuario.

---

## Objetivos principales de la planificación

| Objetivo                 | Significado                                                                 |
|--------------------------|------------------------------------------------------------------------------|
| **Equidad**              | Todos los procesos deben tener oportunidad de ejecutarse.                   |
| **Eficacia**             | La CPU debe estar ocupada todo el tiempo.                                   |
| **Tiempo de respuesta**  | El sistema debe responder rápidamente a las solicitudes del usuario.        |
| **Tiempo de regreso**    | El tiempo desde que un proceso entra hasta que termina debe ser el menor posible. |
| **Rendimiento**          | Ejecutar la mayor cantidad de procesos por unidad de tiempo.                |

---

## Tipos de políticas de planificación

### Según si pueden interrumpir un proceso

- **No expropiativas (No expulsivas):**
  - Una vez que el proceso tiene la CPU, **no se lo puede interrumpir**.
  - Termina por sí solo.
  - Ejemplo: `FCFS`, `SJF no expropiativo`

- **Expropiativas (Expulsivas):**
  - El sistema puede **quitarle la CPU** a un proceso si otro más importante llega.
  - Ejemplo: `Round Robin`, `PSJF`

---

## Algoritmos estudiados en el TP

| Algoritmo                 | Tipo           | Características principales |
|---------------------------|----------------|------------------------------|
| **FCFS / FIFO**           | No expropiativo| Atiende por orden de llegada. Simple, pero puede causar espera larga si el primer proceso es muy largo. |
| **SJF (Short Job First)** | Puede ser ambos| Ejecuta el proceso más corto. Mejora el tiempo medio, pero puede causar inanición en procesos largos. |
| **PSJF**                  | Expropiativo   | Variante de SJF donde puede interrumpirse el proceso si llega otro más corto. |
| **Round Robin (RR)**      | Expropiativo   | Se asigna un tiempo fijo (*quantum*) a cada proceso, y van rotando. Equitativo, ideal para sistemas interactivos. |

---

## Métricas observadas en la simulación

| Métrica                  | ¿Qué mide?                                                               |
|--------------------------|--------------------------------------------------------------------------|
| **CPU Time**             | Tiempo real en que la CPU estuvo funcionando                             |
| **Tiempo de respuesta**  | Desde que un proceso llega hasta que comienza a ejecutarse              |
| **Turnaround Time**      | Desde que el proceso llega hasta que termina completamente               |
| **Tiempo de espera**     | Tiempo que pasó en cola listo sin ejecutarse (deducible de los otros)    |
