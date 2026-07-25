# Actividad de Clase: Analizando Agentes de IA con Hugging Face Spaces

## Objetivo

Explorar aplicaciones reales de Inteligencia Artificial en **Hugging
Face Spaces** y analizarlas desde la perspectiva de los **agentes
racionales**.

Al finalizar la actividad, los estudiantes deberán ser capaces de:

- Identificar los componentes **PEAS** de un agente.
- Clasificar las propiedades del entorno.
- Proponer qué tipo de programa de agente podría implementarse detrás
  del sistema.
- Justificar sus respuestas.

---

## Instrucciones

1.  Ingresen a **https://huggingface.co/spaces**.
2.  Exploren diferentes Spaces.
3.  Seleccionen uno que les parezca interesante.
4.  Interactúen con el sistema durante algunos minutos.
5.  Completen la siguiente ficha de análisis.

---

# Ficha de análisis

## 1. Nombre del Space

**Nombre:** Gemma 4 - Vision Token Budget

**Enlace: https://huggingface.co/spaces/google/gemma4_vision_token_budget**

---

## 2. ¿Qué hace el agente?

Describa en dos o tres líneas cuál es la función del sistema.

## El agente reescala una imagen que el usuario ingresa en 5 diferentes tamaños, esto lo hace dividiendo esta misma para intentar preservar la calidad original de la imagen.

## 3. Análisis PEAS

Elemento Respuesta

---

**Performance** ¿Qué significa que el agente haga bien su trabajo?
**R:** El agente reescala las imágenes a 5 diferentes tamaños, ya sea que se busque ver una imagen a menor escala o mayor escala. El agente es más preciso con las imagenes que contienen texto, ya que al probar con una imagen de un personaje no es tan preciso comparado con una foto de texto.
**Environment** ¿Con qué interactúa el agente?
**R:** El agente interactua con las imagenes ingresadas por los usuarios
**Actuators** ¿Qué acciones produce?
**R:** Devuelve la misma imagen que el usuario ingresó pero reescalada a 5 dimensiones diferentes, también adjunta la dimensión de cada imagen y la cantidad de tokens utilizados en cada una. El agente cuenta con dos imágenes predeterminadas como ejemplo de cómo funciona. En la parte inicial cuenta con una explicación del modelo utilizado para realizar el trabajo.
**Sensors** ¿Qué información recibe como entrada?
**R:** Recibe una imagen ingresada por el usuario. Es posible escoger si se desea escalar a una dimensión entre 5 opciones distintas o si se desea reescalar a todas las dimensiones

---

## 4. Clasificación del entorno

Complete la siguiente tabla y justifique brevemente cada respuesta.

Propiedad Clasificación Justificación

---

Observable Total Si: Considero que si porque para la tarea que se desea hacer, que es reescalar una imagen, el agente cuenta con los sensores suficientes para tener la información constantemente (la foto).
Determinista Sí: El entorno no cambia y siempre es el mismo, el agente espera a que el usuario ingrese una foto y realiza su función, no hay ningún evento externo que afecte el proceso.  
 Episódico Sí: Cada vez que se le pide reescalar una imagen diferente es un evento independiente, no va a cambiar el desempeño del agente por cómo lo hizo en cierto intento.  
 Estático Sí: El entorno siempre es el mismo, el agente espera a que el usuario ingrese la imagen y luego realiza su acción.  
 Discreto Sí: El entorno no varía, el agente solamente recibe imagenes y entrega sus diferentes reescalados.  
 Conocido Sí: Considero que si, ya que sin la información (la foto ingresada) el agente no realiza ninguna acción, por lo que el ambiente siempre será conocido.

---

## 5. ¿Qué tipo de programa de agente creen que es?

Seleccione la opción que consideren más adecuada y explique por qué.

- Agente de reflejo simple
- Agente basado en modelo
- Agente basado en objetivos
- Agente basado en utilidad
- Agente con aprendizaje

**Respuesta:** Lo considero un agente de reflejo simple ya que este agente no tiene en cuenta el historial de precepts o alguna otra información externa para cumplir con su trabajo, símplemente recibe la información del precept actual y realiza una tarea simple de reescalar una foto.

> **Importante:** No existe una única respuesta correcta. Lo importante
> es justificar la elección a partir del comportamiento observado.

---

# Discusión en clase

Después de las presentaciones, discutiremos preguntas como:

- ¿Dos Spaces diferentes pueden compartir el mismo tipo de entorno?
  **Respuesta personal:** Considero que si, por ejemplo varios juegos pueden contar con un mismo entorno, por ejemplo un juego de parqués y un juego de cartas, tienen un entorno con caracteristicas muy similares pero son spaces diferentes con diferentes objetivos.

- ¿Es posible saber con certeza qué tipo de agente implementa un Space
  únicamente observándolo?
  **Respuesta personal:** Considero que es posible identificarlo para spaces sencillos que cumplan con tareas básicas, pero entre la tarea sea mas complicada puede hacerse difícil identificar el tipo de agente solamente observandolo.

- ¿Qué diferencia existe entre el comportamiento observable de un
  agente y su implementación interna?
  **Respuesta personal:** Que el comportamiento observable es la salida que da el agente, la respuesta que da a la tarea que se le asigna, mientras que en su implementación interna puede estar evaluando las diferentes entradas con las que cuenta, asi como con la memoria y su razonamiento lógico entre otras cosas que hacen que el agente tome decisiones o realice alguna tarea

---

# Reto adicional

Encuentre un Space que pueda clasificarse como:

1.  **Totalmente observable, determinista y episódico.**
    **Respuesta:** El space mostrado en los anteriores puntos de la actividad (Gemma 4 - Vision Token Budget / **https://huggingface.co/spaces/google/gemma4_vision_token_budget**) ya que su entorno es totalmente observable y el agente cuenta con toda la información necesaria para su trabajo, es determinista ya que siempre se le pide la misma función al agente y realiza una única tarea, además de que es episódico porque cada evento es independiente del siguiente, el desempeño que tenga reescalando una foto no se va a ver afectado por el reescalado de las fotos anteriores.
2.  **Parcialmente observable, estocástico y secuencial.**
    **Respuesta:** No logré encontrar un space específico en huggingface, sin embargo, se puede tomar como ejemplo los sistmas de gps, en donde los agentes no tienen toda la información de su entorno en tiempo real para tomar decisiones, además de que constantemente ocurren eventos estocásticos como por ejemplo, el comportamiento de los conductores, además de esto es secuencial ya que la toma de una decisión puede cambiar totalmente el resto del proceso, por ejemplo el hecho de que ocurra un accidente en medio del recorrido o que el usuario cometa un error y se equivoque de vía, haciendo necesario actualizar la ruta.

Justifique su respuesta.

---

# Rúbrica (10 puntos)

| Criterio                         | Puntos |
| -------------------------------- | :----: |
| Descripción correcta del Space   |   2    |
| Identificación de PEAS           |   3    |
| Clasificación del entorno        |   3    |
| Justificación del tipo de agente |   2    |
| **Total**                        | **10** |

---
