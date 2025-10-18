# ENLACE DEL VIDEO


# ✈️ Sistema de Gestión de Vuelos con Árbol AVL en Java

---

## 📘 Descripción General

El **Sistema de Gestión de Vuelos con Árbol AVL** es un proyecto desarrollado en **Java** cuyo objetivo es **almacenar, organizar y manipular información de vuelos de forma eficiente**, utilizando estructuras de datos avanzadas.

Este sistema está diseñado con fines **académicos y prácticos**, mostrando cómo los **árboles balanceados AVL** pueden aplicarse a problemas reales como la gestión de bases de datos dinámicas (en este caso, vuelos), donde la inserción, búsqueda y eliminación deben mantenerse rápidas y estables en el tiempo.

A diferencia de un arreglo o lista simple, un **Árbol AVL** garantiza que su estructura se mantenga **balanceada automáticamente** después de cada operación, evitando que el rendimiento se degrade conforme crece la cantidad de elementos.

---

## 🎯 Objetivo del Proyecto

El propósito principal es demostrar el uso del **balanceo automático en árboles binarios de búsqueda** para mantener operaciones en tiempo **O(log n)**, incluso con inserciones y eliminaciones continuas.

Además, se busca que el usuario pueda:
- Registrar vuelos con sus datos principales.
- Buscar vuelos de manera rápida por número o destino.
- Eliminar vuelos sin afectar la estructura ni el orden.
- Visualizar el árbol en distintos recorridos.
- Comprender cómo las **rotaciones AVL** mantienen el árbol equilibrado.

---

## 🧩 Estructura del Proyecto


---

## ⚙️ Descripción de las Clases

### 🧱 `Vuelo.java`
Contiene la estructura de datos que representa cada vuelo.  
Incluye atributos como:
- Número de vuelo (clave principal)
- Origen
- Destino
- Hora de salida
- Aerolínea

Implementa la interfaz `Comparable` para permitir que los vuelos se comparen por su número y puedan insertarse en el árbol ordenadamente.

---

### 🌳 `ArbolAVL.java`
Es el núcleo del sistema.  
Implementa la lógica del árbol AVL:
- Inserción y eliminación de nodos.
- Cálculo del **factor de equilibrio**.
- Ejecución de **rotaciones simples y dobles**.
- Recorridos en inorden, preorden y postorden.

Cada inserción o eliminación recalcula automáticamente la altura de los nodos y decide si se requiere balanceo.

---

### 🔗 `Nodo.java`
Define la estructura de cada nodo del árbol:
- Dato (`Vuelo`)
- Referencias al hijo izquierdo y derecho
- Altura del nodo

Es una clase interna simple pero esencial, ya que almacena los valores y enlaces necesarios para mantener la jerarquía del árbol.

---

### 💻 `App.java`
Proporciona la **interfaz de consola** para que el usuario interactúe con el sistema.  
El menú principal ofrece opciones como:

Registrar vuelo

Buscar vuelo

Eliminar vuelo

Mostrar vuelos (Inorden / Preorden / Postorden)

Salir


El usuario ingresa la información por teclado, y cada opción invoca los métodos correspondientes del árbol AVL.

---

## ⚖️ Funcionamiento del Balanceo AVL

Cada vez que se inserta o elimina un nodo, el árbol calcula el **factor de equilibrio (FE)** de cada nodo:

FE = altura(subárbol_izquierdo) - altura(subárbol_derecho)


- Si `FE` está entre `-1` y `1`, el árbol está balanceado.
- Si `FE` < -1 o > 1, el árbol está desbalanceado y debe **rotar**.

### 🔁 Tipos de Rotaciones

| Tipo de rotación | Caso que corrige | Descripción breve |
|------------------|------------------|-------------------|
| **Simple a la derecha (RR)** | Izquierda-Izquierda | El subárbol izquierdo es más alto. |
| **Simple a la izquierda (LL)** | Derecha-Derecha | El subárbol derecho es más alto. |
| **Doble derecha (LR)** | Izquierda-Derecha | Inserción en el subárbol derecho del hijo izquierdo. |
| **Doble izquierda (RL)** | Derecha-Izquierda | Inserción en el subárbol izquierdo del hijo derecho. |

---

## 📊 Ejemplo de Balanceo Automático

Supongamos que el usuario inserta los vuelos en este orden:


AV300, AV200, AV100


Inicialmente:

  AV300
 /


AV200
/
AV100


El árbol está desbalanceado (FE = 2).  
Se aplica una **rotación simple a la derecha**, obteniendo:


 AV200
 /   \
AV100 AV300


Ahora el árbol está **perfectamente balanceado**, y cualquier búsqueda o inserción futura se mantendrá eficiente.

---

## 🚀 Instrucciones de Uso

### 🔧 Requisitos previos
- **Java 17** o superior instalado
- **VS Code** o **IntelliJ IDEA**
