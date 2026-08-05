*Lee esto en otros idiomas: [English](README.md)*

# Proyecto de Deep Learning — Mantenimiento Predictivo para Motores Turbofán (NASA C-MAPSS)

## Descripción General

Este proyecto desarrolla un avanzado **benchmark de Deep Learning para Mantenimiento Predictivo** utilizando el conjunto de datos **NASA C-MAPSS (Commercial Modular Aero-Propulsion System Simulation)**.

En lugar de predecir la **Vida Útil Remanente (RUL, Remaining Useful Life)** exacta mediante regresión, el problema se reformula como una **tarea de clasificación multiclase de series temporales multivariadas**, donde el estado de salud del motor se categoriza en distintos niveles de riesgo operativo.

La solución evalúa y compara **cinco arquitecturas de Deep Learning de última generación** para clasificación de series temporales multivariadas, implementadas en **PyTorch** siguiendo un flujo de trabajo integral de Machine Learning industrial.

---

# Acerca del Dataset

**Dataset:** Conjunto de Datos de Simulación de Degradación de Motores Turbofán (C-MAPSS)

**Fuente:** NASA Prognostics Data Repository

---

# Descripción General

El dataset C-MAPSS simula el proceso de degradación de motores turbofán de aeronaves que operan bajo diferentes condiciones ambientales y modos de falla.

Cada motor es monitoreado mediante múltiples canales de sensores que capturan su comportamiento termodinámico a lo largo del tiempo hasta que ocurre la falla.

El conjunto de datos contiene:

* Configuraciones operativas
* Mediciones de sensores
* Identificadores de motores
* Trayectorias completas de degradación

---

# Reformulación del Problema

En lugar de predecir la Vida Útil Remanente (RUL) exacta, el problema se transforma en una tarea de clasificación multiclase.

Los estados de salud del motor se definen de la siguiente manera:

| Clase       | Vida Útil Remanente |
| ----------- | ------------------- |
| Saludable   | > 60 ciclos         |
| Advertencia | 30–60 ciclos        |
| Crítico     | < 30 ciclos         |

Esta formulación proporciona resultados más accionables para la planificación de mantenimiento y la toma de decisiones industriales.

---

# Ingeniería de Características

El proyecto incluye amplias técnicas de ingeniería de características diseñadas para mejorar la detección de patrones de degradación.

* Características Dinámicas
* Características Estáticas
* Preparación de Datos

---

# Prevención de Data Leakage

Un aspecto crítico de los proyectos de mantenimiento predictivo es evitar la fuga de información.

Para garantizar una evaluación realista:

* Las trayectorias completas de cada motor permanecen dentro de una única partición.
* Particionamiento Train/Validation/Test basado en grupos.
* No se utiliza información futura durante la generación de características.
* Los valores de RUL se eliminan después de la construcción de la variable objetivo.

---

# Arquitecturas de Deep Learning Evaluadas

Se implementaron y compararon cinco arquitecturas avanzadas.

## 1. FCN (Fully Convolutional Network)

Línea base tradicional y sólida para clasificación de series temporales.

---

## 2. InceptionTime

Arquitectura convolucional de última generación para clasificación de series temporales.

---

## 3. Time Series Transformer

Arquitectura basada en Transformers que utiliza mecanismos de autoatención.

---

## 4. PatchTST

Arquitectura Transformer reciente de última generación.

---

## 5. ConvTransformer

Arquitectura híbrida CNN-Transformer.

---

# Estrategia de Entrenamiento

La canalización de entrenamiento incluye:

* Implementación en PyTorch
* Aceleración mediante GPU
* Early Stopping
* Gradient Clipping
* Balanceo de clases mediante pesos
* Optimizador Adam
* Función de pérdida CrossEntropy

---

# Resultados Generados

El proyecto produce automáticamente:

* Tabla comparativa de benchmark
* Comparación de Accuracy
* Comparación de Macro F1
* Comparación de tiempos de entrenamiento
* Matriz de confusión
* Informe de clasificación
* Curvas ROC
* Visualizaciones de degradación de motores
* Identificación del mejor modelo

---

# Impacto de Negocio

Esta solución puede apoyar:

* Planificación de mantenimiento predictivo
* Gestión de flotas aeronáuticas
* Planificación de repuestos
* Reducción de tiempos de inactividad
* Prevención de fallas
* Monitoreo de la salud de los activos

El enfoque multiclase proporciona alertas de mantenimiento interpretables y directamente utilizables por los equipos operativos.

---

# Licencia

Este proyecto está destinado a fines educativos, de investigación y de portafolio.

Dataset proporcionado por el Centro de Investigación NASA Ames.

---

## Autor

**Armando Guarnera**
Data Scientist
Argentina
