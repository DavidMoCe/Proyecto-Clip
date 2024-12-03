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

### 1. Base de Conocimientos (`bc_galletas.clp`)

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

### 2. Base de Hechos (`bh_galletas.clp`)
Este archivo inicializa los valores actuales del índice cromático, en este caso, 6.

#### Resumen del Contenido:
```clips
(deffacts hechos
    (IC (6 0) (6 1) (6 0)) 
)
```

### 3. Imagen de Consola en FuzzyCLIPS 🖼️
La imagen muestra el resultado del sistema al ejecutarse en FuzzyCLIPS, incluyendo:
- ✅ La inferencia realizada.
- 🔥 La temperatura calculada en función del índice cromático.

### Funcionamiento del Sistema 🛠️
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
  4. Visualiza el resultado.

### Ejemplo de Salida Esperada 📊
Con un índice cromático de 6, se infiere que las galletas están medio hechas y la temperatura del horno debe ser alta. Esto se refleja en el valor difuso correspondiente.



