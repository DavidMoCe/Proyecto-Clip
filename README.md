# Project: Fuzzy Control of an Oven with CLIPS for Grandma María's Cookies 🍪

## 🌍 Choose Your Language / Elige tu idioma:
- [English](#english-)
- [Español](#español-)

---

## English 🇬🇧

## Project Description

This project implements an expert system based on fuzzy logic to control oven temperature. It simulates Grandma María's artisanal process for baking her famous homemade cookies, where she manually adjusts the temperature based on the cookies' chromatic index. The goal is to automate this process using **CLIPS** and fuzzy sets.

### Implemented System

The system uses:
- 🌫️ **Fuzzy sets** to represent the cookies baking conditions and the oven's temperature levels.
- ⚙️ **Rules** that adjust the temperature based on the cookies' chromatic index.
- 🖥️ **CLIPS inference engine**, which applies the rules and calculates the oven temperature.

## Project Structure 📂

The project is divided into two main files and a console output image generated in FuzzyCLIPS:

### 1. **Knowledge Base (`bc_galletas.clp`)** 
This file contains:

- 🗂️ **Fact templates (`deftemplate`)** defining fuzzy sets for the chromatic index and oven temperature.
- 📜 **Fuzzy rules (`defrule`)** describing how to adjust the temperature based on the cookies' baking state.

#### Content Summary:
```clips
(deftemplate IC
    ...
)

(deftemplate temperature
    ...
)

(defrule rule_1
    (IC slightly_raw)
    =>
    (assert (temperature medium))
)

(defrule rule_2
    (IC half_done)
    =>
    (assert (temperature high))
)

(defrule rule_3
    (IC golden)
    =>
    (assert (temperature low))
)
```
### 2. **Fact Base (`bh_galletas.clp`)**
This file initializes the current values for the chromatic index, set to 6 in this case.

#### Content Summary:
```clips
(deffacts facts
    (IC (6 0) (6 1) (6 0)) 
)
```
### 3. Console Results (FuzzyCLIPS) 🖼️
The following image shows the system's execution in FuzzyCLIPS, where:

- ✅ The knowledge base and facts load successfully.
- ⚙️ The inference engine evaluates the rules and generates fuzzy temperatures.
- 🔢 Defuzzification is performed to calculate a precise temperature value.

**Console Results:**
- **Initial Facts**: Chromatic Index (IC) = 6.
- **Max Defuzzification**: Calculates a temperature of 230.0 °C.
- **Center of Gravity Defuzzification**: Calculates a temperature of 206.25 °C.

This indicates that:
1. With a chromatic index of 6, the cookies are classified as half-done.
2. According to the system's rules, the oven adjusts its temperature to a high level.
3. Defuzzification values provide an estimated range for the precise oven temperature.

![FuzzyCLIPS console](galletas/Captura%20de%20pantalla%202024-12-03%20111444.png)

## System Functionality 🛠️
1. **File Loading**:
    - `bc_galletas.clp`: Defines rules and fuzzy sets.
    - `bh_galletas.clp`: Defines initial facts (chromatic index = 6).

2. **Inference Engine**:
    - Based on the chromatic index value, the system evaluates the rules.
    - The most suitable fuzzy temperature is selected.
    - 
3. **Result**:
    - The system generates a fuzzy temperature and displays it in the FuzzyCLIPS console.


## Requirements to Run the Project 💻

  1. **FuzzyCLIPS** installed on the system.
  2. Load both files into the FuzzyCLIPS environment.
  3. Execute the following commands in the console:
     ```clips
     (load "bc_galletas.clp")
     (load "bh_galletas.clp")
     (reset)
     (run)
     ```
     
## Conclusion 🏁
This system successfully automates oven temperature control using fuzzy logic, replicating Grandma María's artisanal criteria. By using CLIPS and FuzzyCLIPS, it effectively manages the uncertainty in chromatic indices, ensuring precise cookie baking control.

---

## Español 🇪🇸

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

