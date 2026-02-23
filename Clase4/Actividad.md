### Actividad de discusión guiada 4 (por grupos)

Tomar el **mismo caso de uso** elegido en la Actividad de la clase 1 (y refinado en las Actividades de las clases 2 y 3) y proponer una **versión conceptual basada en LLM, alineamiento y agentes** para ese problema, definiendo qué hace el modelo, cómo se controla su comportamiento, cómo usaría herramientas y qué riesgos mínimos deben considerarse antes de una primera implementación.

#### Uso de Copilot/ChatGPT (apoyo permitido)

Se permite usar Copilot o ChatGPT para:

* organizar ideas,
* aclarar conceptos,
* revisar coherencia técnica,
* resumir para diapositivas.

**No se permite** copiar texto sin entenderlo. El grupo debe poder explicar cada decisión.

#### Instrucciones para cada grupo

Usando su caso de uso de las actividades previas, respondan de forma breve:

#### 1. Rol del LLM en su caso (qué parte sí usa LLM y qué parte no)

Definan **dónde entra el LLM** en su pipeline (no todo el sistema tiene que ser LLM).

* ¿Qué tarea hace el LLM? (clasificar, extraer, resumir, generar, explicar, recomendar)
* ¿Qué parte queda fuera del LLM? (reglas, base de datos, validaciones, humano)
* ¿Qué salida produce exactamente?

> Si su caso no requiere generación de texto, expliquen si el LLM **no** es la primera opción y dónde sí podría aportar (asistente, explicación, interfaz, resumen).

**Prompt sugerido (Copilot/ChatGPT):**

```text
Nuestro caso de uso es [caso] y el problema es [problema].
En las actividades anteriores propusimos [solución base/Transformer].
Ayúdanos a definir el rol del LLM:
1) qué parte del pipeline usaría LLM,
2) qué tarea haría exactamente,
3) qué parte NO debe hacer (reglas, BD, decisión humana),
4) qué salida produciría.
Responde en viñetas, breve y técnico.
```

#### 2. Modelos de lenguaje causales, tokenización y ventana de contexto

Expliquen cómo aterrizarían un **LLM causal (decoder-only)** en su dominio.

Incluyan:

* ¿Por qué su tarea encaja (o no) con un modelo causal?

* ¿Qué sería un "token" importante en su caso? (palabra, código, log, evento, registro, etc.)

* ¿Qué problema puede causar la **ventana de contexto** en su caso?

  * prompts largos,
  * pérdida de información relevante,
  * costo/latencia,
  * historial demasiado grande.

* ¿Qué harían en una primera versión para manejar contexto largo?

  * truncado,
  * resumen de historial,
  * chunking,
  * recuperación de contexto (RAG simple).

**Prompt sugerido (Copilot/ChatGPT):**

```text
Explica cómo aplicar un LLM causal (decoder-only) a nuestro caso [caso].
Incluye:
1) por qué encaja o no,
2) qué tipo de tokenización importa en este dominio,
3) qué riesgo hay con la ventana de contexto,
4) una estrategia simple para manejar contexto largo (truncado, resumen, chunks o RAG).
No inventes números; razona de forma práctica.
```

#### 3. Instrucción y ajuste fino (instruct tuning) sobre modelo preentrenado

Comparen **modelo base preentrenado** vs. **modelo instruido** en su caso.

Expliquen:

* ¿Qué diferencia esperan en comportamiento?

* ¿Qué mejoraría con *instruct tuning*?

  * seguir instrucciones,
  * respetar formato,
  * tono,
  * rechazar pedidos no válidos,
  * pedir aclaración.

* ¿Qué tipo de ejemplos necesitarían para ajustar?

  * instrucción + respuesta ideal,
  * ejemplos de formato,
  * casos ambiguos,
  * casos que deben rechazarse.

> Si no harán fine-tuning real todavía, indiquen cómo lo aproximarían con **prompting estructurado** y **few-shot**.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Para nuestro caso [caso], compara:
- modelo base preentrenado
- modelo instruido (instruct tuned)

Explica:
1) qué diferencia de comportamiento esperaríamos,
2) qué mejoraría con instruct tuning,
3) qué ejemplos de entrenamiento necesitaríamos,
4) cómo aproximarlo con prompting/few-shot si aún no haremos fine-tuning.
Responde en viñetas claras.
```

#### 4. Alineamiento: RLHF, DPO/ORPO y modelos de preferencia (idea conceptual)

Hagan una comparación **conceptual** (sin fórmulas largas) de enfoques de alineamiento.

Incluyan:

* ¿Qué significa "alinear" el modelo en su caso?

* ¿Qué preferencias humanas importan más?

  * utilidad,
  * precisión,
  * seguridad,
  * formato,
  * tono,
  * no inventar datos.

* Comparen brevemente:

  * **RLHF**
  * **DPO/ORPO**
  * **modelo de preferencia** (cómo definir "mejor" vs. "peor" respuesta)

* ¿Cuál enfoque usarían como marco conceptual inicial y por qué?

> No se espera implementación matemática; sí criterio técnico y conexión con su dominio.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Ayúdanos a explicar alineamiento para nuestro caso [caso].
Necesitamos una comparación conceptual de:
- RLHF
- DPO/ORPO
- modelos de preferencia

Incluye:
1) qué significa "alinear" en este problema,
2) qué preferencias humanas importan,
3) qué enfoque usaríamos como marco conceptual y por qué.
Sin fórmulas largas.
```

#### 5. Razonamiento (salida útil y verificable)

Definan cómo pedirían respuestas con **razonamiento útil** (sin depender de respuestas "mágicas").

Incluyan:

* ¿Qué tipo de razonamiento necesita su caso?

  * clasificación con justificación,
  * comparación de opciones,
  * extracción con evidencia,
  * planificación paso a paso,
  * generación con restricciones.

* ¿Qué formato de salida usarían para mejorar calidad?

  * viñetas,
  * pasos numerados,
  * tabla textual,
  * JSON,
  * respuesta + evidencia.

* ¿Cómo reducirían errores/alucinaciones?

  * pedir evidencia del contexto,
  * permitir "no sé",
  * validación por reglas,
  * revisión humana en casos críticos.

> En esta actividad se evalúa **estructura de salida y verificabilidad**, no "pensamiento oculto".

**Prompt sugerido (Copilot/ChatGPT):**

```text
Nuestro caso [caso] requiere respuestas útiles y verificables.
Propón una estrategia de prompting para mejorar el razonamiento práctico:
1) formato de salida recomendado,
2) cómo pedir evidencia o justificación,
3) cómo reducir errores/alucinaciones,
4) cuándo debe decir "no sé" o pedir aclaración.
Responde en viñetas operativas.
```

#### 6. LLM como agente (uso de herramientas)

Conviertan su LLM en un **agente** (asistente con herramientas) a nivel conceptual.

Definan qué herramientas externas usaría, por ejemplo:

* buscador interno/web,
* base de datos,
* hoja de cálculo,
* API institucional,
* repositorio documental,
* sistema de tickets,
* calculadora o motor de reglas.

Para cada herramienta, indiquen:

* ¿qué consulta hace el agente?
* ¿qué devuelve la herramienta?
* ¿cómo usa eso el LLM para responder?

> No hace falta implementar APIs; se espera diseño operativo claro.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Convierte nuestro LLM para [caso] en un agente con herramientas.
Define 3-5 herramientas posibles y para cada una indica:
1) qué consulta haría el agente,
2) qué devuelve la herramienta,
3) cómo usaría el LLM ese resultado en la respuesta final.
Usa viñetas concretas.
```

#### 7. Memoria y planificación del agente

Definan cómo organizarían **memoria** y **planificación**.

##### 7.1 Memoria

Distingan:

* **Memoria corta** (turnos recientes)
* **Memoria de sesión** (objetivo actual)
* **Memoria persistente** (preferencias, reglas de dominio, historial resumido)

Indiquen también:

* qué **sí** conviene guardar,
* qué **no** debería guardarse (datos sensibles innecesarios).

##### 7.2 Planificación

Propongan una secuencia simple del agente:

1. entender pedido,
2. hacer plan corto,
3. llamar herramienta(s),
4. integrar resultados,
5. validar formato/reglas,
6. responder o escalar a humano.

> Si quieren, agreguen un paso de "reintento" cuando falle una herramienta.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Para nuestro caso [caso], diseña memoria y planificación de un agente LLM.
Incluye:
1) memoria corta, de sesión y persistente,
2) qué información sí/no guardar,
3) plan de ejecución paso a paso,
4) qué hacer si una herramienta falla,
5) dónde entra supervisión humana.
Responde en viñetas claras.
```

#### 8. Riesgos, sesgos y consideraciones éticas básicas

Identifiquen riesgos **reales** de su caso (no genéricos).

Incluyan al menos:

* **1 riesgo de sesgo** (datos, lenguaje, cobertura)
* **1 riesgo de alucinación o error factual**
* **1 riesgo de privacidad/uso indebido**
* **1 riesgo operativo** (latencia, costo, dependencia de herramientas, fallos)

Para cada riesgo, definan un control mínimo:

* reglas/restricciones,
* validación automática,
* trazabilidad (fuente/evidencia),
* revisión humana,
* mensajes de incertidumbre,
* límites de uso.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Para nuestro caso [caso], identifica riesgos y controles mínimos en un sistema LLM/agente.
Incluye:
1) sesgo,
2) alucinación/error factual,
3) privacidad/uso indebido,
4) riesgo operativo (latencia/costo/falla),
5) control práctico para cada uno.
Sé específico al dominio.
```
#### 9. Mini plan de evaluación (modelo + comportamiento + agente)

Definan una validación mínima para su propuesta de LLM/agente.

Incluyan:

* **1 métrica técnica** (accuracy, F1, exact match, ROUGE, etc.)
* **1 métrica de comportamiento** (cumplimiento de formato, tasa de respuestas útiles, tasa de alucinación)
* **1 métrica operativa** (latencia, número de llamadas a herramientas, costo por tarea)
* **1 riesgo crítico a monitorear**
* **1 criterio mínimo de versión aceptable**

> No inventen resultados; solo diseñen cómo evaluarían la versión inicial.

**Prompt sugerido (Copilot/ChatGPT):**

```text
Ayúdanos a definir una mini-validación para nuestro caso [caso] en una versión con LLM/agente.
Incluye:
1) una métrica técnica,
2) una métrica de comportamiento,
3) una métrica operativa,
4) un riesgo crítico,
5) un criterio mínimo de éxito.
No inventes resultados; solo propone validación razonable.
```

#### 10. Entregable

Cada grupo entrega **3 o 4 diapositivas o 1 hoja** con este formato:

**Plantilla rápida**

1. **Caso de uso y problema (mismo de Actividad 1).**
2. **Rol del LLM en el pipeline (qué hace/qué no hace).**
3. **LLM causal + tokenización + ventana de contexto.**
4. **Instruct tuning (o aproximación con prompting/few-shot).**
5. **Alineamiento (RLHF/DPO-ORPO/preferencias).**
6. **Razonamiento: formato de salida + control de errores.**
7. **Agente: herramientas.**
8. **Agente: memoria + planificación + supervisión humana.**
9. **Riesgos/sesgos/ética + controles mínimos.**
10. **Métricas + riesgo crítico + criterio mínimo.**
