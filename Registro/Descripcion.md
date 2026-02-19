Queremos crear una plataforma para que cientificos de datos registren sus experimentos. 

Un experimento utiliza un modelo específico, se entrena con un archivo de datos concreto y genera una métrica de acierto (Accuracy). 

Además, cada experimento debe guardar la fecha en la que se realizó para poder compararlos después.

Se pide.

- Identificar las clases necesarias y dibujar su estructura.
- Enumerar los atributos necesarios para que el experimento esté completo.
- Definir los métodos necesarios para poder cumplir con las especificaciones del enunciado.
- Dibujar tres Objetos (instancias) que representen tres pruevas distintas.
-   Ej: Una con una RRNN, otra con un árbol de decisión, SVM, etc)

````mermaid
---
title: Experimentos
config:
    class:
      hideEmptyMembersBox: true
---
classDiagram

class Experimento{
  -int  ID
  +Date fecha

  +entrena(Training_Data, Modelo_Usado) void
  -BLOB status

  +Float accuracy
  +ComputeAccuracy() Float

  }

class Modelo{
    +String nombre
    -Actualización() void
    }

class Training_Data{
  +String path
  +Bool checked
  }


Experimento "1" --> "1"  Training_Data : trains_on
Experimento "1" --> "1"  Modelo : uses
   
````
