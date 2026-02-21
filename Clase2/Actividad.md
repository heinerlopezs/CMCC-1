### Actividad de discusión guiada 2 (por grupos)

Tomar el **mismo caso de uso** elegido en la Actividad 1 y proponer una **primera solución con aprendizaje profundo** (a nivel conceptual, sin necesidad de programar).

#### Uso de Copilot / ChatGPT (apoyo permitido)

Se permite usar Copilot o ChatGPT para:

* organizar ideas,
* aclarar conceptos,
* revisar coherencia técnica,
* resumir para diapositivas.

**No se permite** copiar texto sin entenderlo. El grupo debe poder explicar cada decisión.

#### Instrucciones para cada grupo

Usando su caso de uso de la Actividad 1, respondan de forma breve:

#### 1. ¿Qué entra y qué sale del modelo?

* **Entrada (input):** texto, imagen, audio, series de tiempo, tabular, etc.
* **Salida (output):** clase, probabilidad, valor numérico, texto generado, recomendación, etc.

> Ejemplo: "Entrada: historiales de sensores. Salida: probabilidad de falla en 24 horas."

**Prompt sugerido (Copilot/ChatGPT):**

```text
Nuestro caso de uso es [caso]. El problema es [problema].
Ayúdanos a definir claramente el input y output del modelo (tipo de dato, formato, y qué queremos predecir o generar).
Responde en viñetas, de forma breve.
```

#### 2. Primera arquitectura simple (Perceptrón / MLP)

Propongan una arquitectura inicial:

* ¿Usarían **Perceptrón** o **MLP**?
* ¿Qué activación usarían? (ReLU, GELU, sigmoid, tanh)
* ¿Qué función de pérdida usarían? (CrossEntropy, MSE, BCE, etc.)

**Explicar en 2-3 líneas por qué.**

**Prompt sugerido (Copilot/ChatGPT):**

```text
Para este caso de uso [caso], con datos [tipo de datos] y salida [salida],
¿conviene usar Perceptrón o MLP como primera versión?
Sugiere una activación y una función de pérdida adecuadas.
Explica la elección en 2-3 líneas, con lenguaje claro.
```

#### 3. Entrenamiento y retropropagación (idea básica)

Sin fórmulas largas:

* ¿Cómo aprende el modelo?
* ¿Qué rol cumplen los **gradientes**?
* ¿Qué pasaría si los gradientes son muy pequeños o muy grandes?

> Aquí solo se espera una explicación conceptual.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Explica de forma conceptual cómo aprende una red neuronal en nuestro caso:
pérdida, gradientes, retropropagación y actualización de pesos.
Incluye qué ocurre si los gradientes son muy pequeños o muy grandes.
Sin fórmulas largas.
```

#### 4. Regularización y generalización

Elijan **2 o 3 técnicas** y digan por qué las usarían:

* **L2 (weight decay)**
* **Dropout**
* **Batch Normalization** (o LayerNorm si quieren conectar con Transformers)
* **Early stopping**

> Ejemplo: "Usamos dropout para reducir sobreajuste y early stopping para evitar seguir entrenando cuando validación empeora."

**Prompt sugerido (Copilot/ChatGPT):**

```text
Propón 2 o 3 técnicas de regularización para este caso [caso].
Considera L2, dropout, batch normalization (o layer norm) y early stopping.
Explica brevemente para qué sirve cada una y por qué conviene en este problema.
```

#### 5. Optimizador y tasa de aprendizaje

Elijan una configuración inicial:

* **SGD + momentum** o **Adam/AdamW**
* ¿Usarían una programación de tasa de aprendizaje? (por ejemplo: reducir LR o cosine)

**Explicar por qué la eligieron para su caso.**

**Prompt sugerido (Copilot/ChatGPT):**

```text
Compara SGD con momentum vs Adam/AdamW para este caso [caso].
¿Cuál conviene como primera versión y por qué?
Sugiere una estrategia simple de learning rate (fijo, reducción, cosine, etc.).
```

#### 6. ¿RNN/LSTM o Atención? (puente a Transformers)

Si tu caso tiene **secuencias** (texto, audio, series de tiempo, logs, historial):

* ¿Qué limitación tendría RNN/LSTM? (secuencias largas, contexto lejano, entrenamiento)
* ¿Cómo ayudaría un **mecanismo de atención**?
* Si aplica, ¿usarían Transformer/LLM directamente?

> Si tu caso **no** es secuencial (por ejemplo, tabular simple), indiquen:
> "Atención no es necesaria en la primera versión", o cómo podría aparecer después (por ejemplo, atención sobre variables importantes).

**Prompt sugerido (Copilot/ChatGPT):**

```text
Nuestro problema usa [texto/audio/series/logs/tabular].
Explica si tiene sentido usar RNN/LSTM o no.
Si hay secuencias largas, explica cómo ayudaría un mecanismo de atención.
Indica si usaríamos Transformer/LLM directamente o no, y por qué.
```

#### 7. Mini plan de validación

Definan de forma simple:

* 1 métrica principal (accuracy, F1, MAE, etc.)
* 1 riesgo técnico (sobreajuste, datos desbalanceados, ruido)
* 1 criterio de "versión inicial aceptable"

**Prompt sugerido (Copilot/ChatGPT):**

```text
Ayúdanos a definir una mini-validación para este caso [caso]:
1) una métrica principal,
2) un riesgo técnico importante,
3) un criterio mínimo de éxito para una versión inicial.
No inventes resultados; solo propone una validación razonable.
```

#### 8. Entregable

Cada grupo entrega **2 o 3 diapositivas o 1 hoja** con este formato:

**Plantilla rápida**

1. **Caso de uso y problema**
2. **Input / Output**
3. **Modelo inicial (Perceptrón/MLP)**
4. **Activación + pérdida**
5. **Cómo aprende (gradientes/retropropagación)**
6. **Regularización elegida**
7. **Optimizador + LR**
8. **¿Atención/Transformer? (sí/no y por qué)**
9. **Métrica + riesgo + criterio mínimo**

**Prompt sugerido para armar la diapositiva final (Copilot/ChatGPT):**

```text
Convierte nuestro borrador en una exposición de 2-3 diapositivas (o 1 hoja) con estos bloques:
1) Caso de uso y problema
2) Input/Output
3) Modelo inicial
4) Activación + pérdida
5) Retropropagación y gradientes
6) Regularización
7) Optimizador + LR
8) Atención/Transformer
9) Métrica + riesgo + criterio mínimo

Usa viñetas breves, lenguaje técnico claro y sin inventar datos.
```

#### Prompt general opcional (para todo el trabajo)

Si quieren usar un solo prompt desde el inicio:

```text
Estamos haciendo una actividad de discusión guiada (sin puntaje) sobre aprendizaje profundo.
Nuestro caso de uso es [caso] y el problema es [problema].
Tipo de datos: [texto/imagen/audio/tabular/series].
Salida esperada: [clase/probabilidad/valor/texto/recomendación].

Ayúdanos a proponer una primera solución conceptual con:
1) input/output,
2) Perceptrón o MLP,
3) activación y función de pérdida,
4) retropropagación y gradientes (explicación conceptual),
5) regularización,
6) optimizador y learning rate,
7) RNN/LSTM vs atención (si aplica),
8) métrica, riesgo y criterio mínimo.

Responde en formato de viñetas, breve, claro y sin inventar resultados.
```
