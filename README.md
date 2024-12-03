# Proyecto: Control Difuso de un Horno con CLIPS para las Galletas de la Abuela María 🍪

## Descripción del Proyecto

Este proyecto consiste en implementar un sistema experto basado en lógica difusa para controlar la temperatura de un horno. Se simula el proceso artesanal de la abuela María para hornear sus famosas galletas caseras, en el que ajusta manualmente la temperatura en función del índice cromático de las galletas. El objetivo es automatizar este proceso utilizando **CLIPS** y conjuntos difusos.

### Sistema Implementado

El sistema utiliza:
- 🌫️ **Conjuntos difusos** para representar las condiciones de cocción de las galletas y los niveles de temperatura del horno.
- ⚙️ **Reglas** que ajustan la temperatura en función del índice cromático de las galletas.
- 🖥️ **Motor de inferencia de CLIPS**, que aplica las reglas y calcula la temperatura del horno.

## Estructura del Proyecto 📂

El proyecto se divide en dos archivos principales y una imagen generada en la consola de FuzzyCLIPS:

### 1. **Base de Conocimientos (`bc_galletas.clp`)**

Este archivo contiene:
- 🗂️ **Plantillas de hechos (`deftemplate`)** que definen los conjuntos difusos para el índice cromático y la temperatura del horno.
- 📜 **Reglas difusas (`defrule`)** que describen cómo ajustar la temperatura en función del estado de cocción de las galletas.

#### Resumen del Contenido:
```clips
(deftemplate IC
    ...
)

(deftemplate temperatura
    ...
)

(defrule regla_1
    (IC poco_crudas)
    =>
    (assert (temperatura media))
)

(defrule regla_2
    (IC medio_hechas)
    =>
    (assert (temperatura alta))
)

(defrule regla_3
    (IC doraditas)
    =>
    (assert (temperatura baja))
)
```

### 2. **Base de Hechos (`bh_galletas.clp`)**
Este archivo inicializa los valores actuales del índice cromático, en este caso, 6.

#### Resumen del Contenido:
```clips
(deffacts hechos
    (IC (6 0) (6 1) (6 0)) 
)
```

### 3. **Resultados en Consola (FuzzyCLIPS)** 🖼️
La siguiente imagen muestra la ejecución del sistema en FuzzyCLIPS, donde:
- ✅ Se cargan correctamente la base de conocimientos y los hechos.
- ⚙️ El motor de inferencia evalúa las reglas y genera las temperaturas difusas.
- 🔢 Se realiza la defuzzificación para calcular un valor de temperatura preciso.

**Resultados de la Consola**:
- **Hechos iniciales**: Índice cromático (IC) = 6.
- **Defuzzificación máxima**: Calcula una temperatura de 230.0 °C.
- **Defuzzificación por momento**: Calcula una temperatura de 206.25 °C.

Esto indica que:
1. Con un índice cromático de 6, las galletas son clasificadas como medio hechas.
2. Según las reglas del sistema, el horno ajusta su temperatura a un nivel alto.
3. Los valores de defuzzificación proporcionan un rango estimado para la temperatura precisa del horno.

![Consola de FuzzyCLIPS](galletas/Captura%20de%20pantalla%202024-12-03%20111444.png)

## Funcionamiento del Sistema 🛠️
 1. **Carga de los Archivos**:
    - `bc_galletas.clp`:  Define las reglas y conjuntos difusos.
    - `bh_galletas.clp`: Define los hechos iniciales (índice cromático = 6).
 2. **Motor de Inferencia**:
    - Según el valor del índice cromático, el sistema evalúa las reglas.
    - Se selecciona la temperatura difusa más adecuada.
 3. **Resultado**:
    - El sistema genera una temperatura difusa y la muestra en la consola de FuzzyCLIPS.

## Requisitos para Ejecutar el Proyecto 💻
  1. **FuzzyCLIPS** instalado en el sistema.
  2. Cargar ambos archivos en el entorno de FuzzyCLIPS.
  3. Ejecutar las siguientes instrucciones en la consola:
     ```clips
     (load "bc_galletas.clp")
     (load "bh_galletas.clp")
     (reset)
     (run)
     ```
     
## Conclusión 🏁
Este sistema automatiza exitosamente el ajuste de temperatura del horno utilizando lógica difusa, replicando el criterio artesanal de la abuela María. El uso de CLIPS y FuzzyCLIPS permite manejar la incertidumbre en los índices cromáticos, garantizando un control preciso de la cocción de las galletas.

