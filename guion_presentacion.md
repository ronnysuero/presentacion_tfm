GUION PARA LA DEFENSA DE TFM: DETECCIÓN DE FRAUDES EN TARJETAS DE CRÉDITO
=========================================================================

---

### **Diapositiva 1: Portada (Tiempo: ~30 segundos)**

**(Mientras la diapositiva está en pantalla)**

"Buenos días a todos. Mi nombre es Ronny Zapata y junto con mi compañero Miguel Caballero, estamos aquí para presentar la defensa de nuestro Trabajo de Fin de Máster titulado 'Detección de Fraudes en Tarjetas de Crédito en el Sector Bancario'.

Agradecemos la presencia del jurado, de nuestro tutor, y de todos los asistentes."

---

### **Diapositiva 2: El Problema (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"Comencemos por el problema que nos motivó a realizar este estudio. El fraude con tarjetas de crédito no es solo una cifra en un balance; es una amenaza creciente y cada vez más sofisticada que tiene un triple impacto:

Primero, el **impacto económico directo**, que se traduce en pérdidas millonarias tanto para las instituciones financieras como para los clientes.

Segundo, y quizás más importante, la **erosión de la confianza**. Cada incidente de fraude debilita la seguridad que los consumidores sienten al usar sistemas de pago electrónico, que son la base de la economía digital actual.

Y tercero, esto convierte la detección de fraude en una **necesidad estratégica**. Ya no es suficiente con reaccionar; es imperativo anticiparse. Los métodos tradicionales, a menudo basados en reglas fijas, simplemente ya no son suficientes para combatir a adversarios que adaptan y evolucionan sus tácticas constantemente."

---

### **Diapositiva 3: Nuestra Misión (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"Ante este desafío, nuestra misión con este trabajo fue clara y se centró en tres pilares fundamentales.

Primero, **Implementar**. No nos quedamos en la teoría. Desarrollamos y entrenamos un arsenal diverso de modelos de Machine Learning, desde los más interpretables como los Árboles de Decisión, hasta soluciones de vanguardia como XGBoost y las Redes Neuronales.

Segundo, **Comparar**. El núcleo de nuestra investigación fue una evaluación rigurosa y objetiva. Sometimos a cada modelo a las mismas condiciones y los medimos con métricas específicas para problemas de fraude, como el F1-Score y el AUC PR, que van más allá de la simple exactitud.

Y finalmente, **Recomendar**. Nuestro objetivo último es que este trabajo tenga una aplicación práctica. Queríamos traducir nuestros hallazgos empíricos en una guía clara que pueda ayudar a las instituciones financieras a elegir las herramientas más adecuadas para sus necesidades y estrategias de negocio."

---

### **Diapositiva 4: El Campo de Batalla: El Dataset (Tiempo: ~1.5 minutos)**

**(Mientras el gráfico de barras se anima)**

"Para llevar a cabo nuestra misión, necesitábamos un campo de batalla realista. Por ello, seleccionamos un conocido dataset público de Kaggle, que contiene transacciones reales con tarjetas de crédito europeas durante un periodo de dos días.

Este dataset nos presenta un desafío fundamental, que pueden ver claramente en este gráfico: el **extremo desbalanceo de clases**.

**(Señalar el gráfico)**

Como pueden observar, de más de 280,000 transacciones, menos de 500 son fraudulentas. Esto representa apenas un 0.17% del total. ¿Por qué es esto un problema? Porque un modelo ingenuo podría alcanzar una exactitud del 99.8% simplemente clasificando *todas* las transacciones como legítimas, pero sería completamente inútil en la práctica, ya que no detectaría ni un solo fraude.

Este desbalanceo extremo es el principal obstáculo a superar y la razón por la que se requieren técnicas especializadas, que abordaremos a continuación."

---

### **Diapositiva 5: Nuestro Arsenal: Los Modelos (Tiempo: ~1.5 minutos)**

**(Mientras la diapositiva está en pantalla)**

"Para enfrentar este desafío, seleccionamos un arsenal de algoritmos variado.

En el lado de los **modelos supervisados**, que aprenden de datos previamente etiquetados, incluimos:
- El **Árbol de Decisión**, por su simplicidad e interpretabilidad.
- La **Máquina de Soporte Vectorial o SVM**, por su capacidad para encontrar relaciones no lineales complejas.
- La **Red Neuronal**, que puede aprender patrones extremadamente sutiles y complejos, imitando el funcionamiento del cerebro.
- Y **XGBoost**, un algoritmo basado en árboles que es actualmente un estándar en la industria por su altísimo rendimiento y eficiencia.

Adicionalmente, exploramos **modelos no supervisados** como **Isolation Forest** y **DBSCAN**. Estos no aprenden de etiquetas, sino que buscan anomalías o 'puntos raros' en los datos. Su rol no es tanto ser la primera línea de defensa, sino actuar como un sistema complementario, capaz de detectar tipos de fraude completamente nuevos que los modelos supervisados nunca han visto."

---

### **Diapositiva 6: Táctica Clave: Manejo del Desbalanceo (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"Como mencionamos, el desbalanceo de datos es nuestro principal enemigo. Para combatirlo, no podíamos entrenar nuestros modelos con los datos en crudo. Necesitábamos nivelar el terreno de juego.

Para ello, aplicamos dos tácticas avanzadas:

La primera es **SMOTE**. De forma sencilla, SMOTE mira los pocos ejemplos de fraude que tenemos y crea "clones" sintéticos, pero muy realistas. Es una forma inteligente de generar más datos de la clase minoritaria para que el modelo tenga más ejemplos de los que aprender.

La segunda técnica, más sofisticada, son las **GANs** o Redes Generativas Adversarias. Aquí, tenemos dos redes neuronales compitiendo. Una, el 'Generador', actúa como un falsificador, creando datos de fraude cada vez más convincentes. La otra, el 'Discriminador', actúa como un detective que intenta diferenciar los datos falsos de los reales. A través de esta competencia, el generador aprende a crear datos sintéticos de una calidad excepcional.

Estas dos técnicas nos permitieron crear conjuntos de datos de entrenamiento balanceados, un paso crucial para el éxito de nuestros modelos."

---

### **Diapositiva 7: Resultados con SMOTE (Tiempo: ~2 minutos)**

**(Mientras el gráfico de barras se anima)**

"Pasemos a los resultados. Primero, veamos el rendimiento de nuestros modelos entrenados con datos balanceados mediante SMOTE.

En este gráfico comparamos cuatro modelos a través de tres métricas clave: Recall (azul), que mide cuántos fraudes reales se detectaron; Precision (verde), que mide qué tan fiables son nuestras alertas; y F1-Score (naranja), que es un balance entre ambas.

**(Analizar el gráfico)**

- El **Árbol de Decisión** nos sirve como una línea base, con un rendimiento modesto.
- El **SVM** sorprende con un Recall muy alto, del 83%, pero su precisión es inviablemente baja, de solo el 10%. Esto significa que, aunque detecta muchos fraudes, genera una cantidad masiva de falsas alarmas.
- La **Red Neuronal** base ya muestra un excelente equilibrio, con un F1-Score de 0.75.
- Sin embargo, el claro ganador en este escenario es **XGBoost Optimizado**. Como pueden ver, no solo tiene el Recall más alto y equilibrado con un 79%, sino que también mantiene una Precision muy sólida del 77%, logrando el F1-Score más alto.

Esto posiciona a XGBoost como el modelo supervisado más robusto y efectivo cuando se utiliza SMOTE."

---

### **Diapositiva 8: El Poder de las GANs (Tiempo: ~1.5 minutos)**

**(Mientras las matrices de confusión están en pantalla)**

"Ahora, ¿qué ocurrió cuando usamos las GANs para aumentar los datos de nuestra Red Neuronal? El resultado fue sorprendente y revela una ventaja clave de esta técnica.

Aquí vemos dos 'matrices de confusión'. A la izquierda, el rendimiento de la Red Neuronal con SMOTE; a la derecha, con GANs. Estas matrices nos dicen exactamente en qué acierta y en qué falla el modelo. Nos enfocaremos en los 'Falsos Positivos', que son las transacciones legítimas que el modelo marcó incorrectamente como fraude.

**(Señalar los Falsos Positivos)**

El modelo con SMOTE generó 26 falsas alarmas. Sin embargo, el modelo entrenado con datos de GAN, en su versión optimizada, **redujo este número a solo 12**. ¡Es una disminución de más del 50%!

Esto se traduce en una **precisión excepcional del 86%**, la más alta de todo nuestro estudio. La conclusión es clara: las GANs son una herramienta increíblemente poderosa para enseñar al modelo a ser más 'cuidadoso', minimizando las alertas incorrectas y, por tanto, reduciendo costes operativos y mejorando la experiencia del cliente."

---

### **Diapositiva 9: El Veredicto (Tiempo: ~1.5 minutos)**

**(Mientras la diapositiva está en pantalla)**

"Entonces, ¿cuál es el veredicto final? ¿Qué modelo es el mejor defensor contra el fraude? La respuesta, como suele ocurrir, es: **depende de la estrategia**.

Hemos identificado dos campeones, cada uno con una fortaleza distinta.

Por un lado, tenemos a **XGBoost con SMOTE**. Este es el 'todoterreno'. Ofrece el mejor rendimiento global, especialmente en la métrica AUC PR, que mide la calidad de la predicción a través de todos los umbrales. Es la elección ideal si la prioridad del banco es **maximizar la cantidad total de fraudes detectados**, asumiendo un coste razonable de revisión de falsas alarmas.

Por otro lado, tenemos la **Red Neuronal con GANs**. Este es el 'francotirador'. Su fortaleza es una precisión quirúrgica, inigualada por los otros modelos. Es la opción perfecta si el objetivo primordial es **minimizar el impacto en el cliente y los costes operativos** asociados a la gestión de falsos positivos.

La elección entre uno y otro no es técnica, sino estratégica."

---

### **Diapositiva 11: Conclusiones Clave (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"Para concluir, nuestro estudio nos deja cuatro mensajes clave:

- Primero: El **manejo del desbalanceo de datos no es un paso más, es el paso fundamental**. Sin técnicas como SMOTE o GANs, es imposible construir un modelo de detección de fraude efectivo.
- Segundo: **XGBoost Optimizado** se confirma como una solución extremadamente robusta y equilibrada, siendo una apuesta segura para un alto rendimiento general.
- Tercero: Las **GANs** emergen como una tecnología de vanguardia con un potencial inmenso, especialmente para mejorar la **precisión** y reducir los costes operativos.
- Y finalmente, la mejor solución no es universal. La elección del modelo debe ser una **decisión de negocio informada por los datos**, alineada con la prioridad estratégica de la institución, ya sea maximizar la detección o minimizar las falsas alarmas."

---

### **Diapositiva 12: Implicaciones Prácticas (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"¿Qué significan estos hallazgos en la práctica para una institución financiera?

Significa que es hora de **adoptar modelos avanzados**. Los sistemas basados en reglas simples ya no son suficientes. Herramientas como XGBoost y Redes Neuronales tienen la capacidad de aprender y adaptarse a patrones de fraude mucho más complejos.

Significa también que debemos **usar las métricas correctas**. La 'exactitud' es una métrica peligrosa en este campo. El éxito debe medirse con indicadores como el F1-Score y el AUC PR, que reflejan el verdadero rendimiento en la detección de la clase minoritaria, que es la que nos importa.

Y finalmente, implica **implementar estrategias de datos robustas**. El ciclo de vida de un modelo de fraude debe incluir, por defecto, una fase dedicada al manejo inteligente del desbalanceo de datos."

---

### **Diopositiva 13: Trabajo Futuro (Tiempo: ~1 minuto)**

**(Mientras la diapositiva está en pantalla)**

"Este trabajo abre la puerta a líneas de investigación futuras muy emocionantes.

Una de ellas es el uso de **Modelos de Grafos**, que no ven las transacciones como eventos aislados, sino como una red interconectada, permitiendo descubrir complejas redes de fraude coordinado.

Otra es el **Despliegue en Tiempo Real**. Investigar las arquitecturas necesarias para que estos modelos puedan operar en milisegundos es el paso crucial para llevarlos del laboratorio a la producción.

Y finalmente, la **IA Explicable o XAI**. Integrar herramientas que nos digan *por qué* un modelo toma una decisión es clave para empoderar a los analistas de fraude, aumentar la confianza en el sistema y cumplir con futuras regulaciones."

---

### **Diopositiva 14: Agradecimientos y Contacto (Tiempo: ~30 segundos)**

**(Mientras la diapositiva está en pantalla)**

"Para finalizar, queremos expresar nuestro más sincero agradecimiento a nuestro tutor por su guía, a la universidad por la oportunidad, y a todos ustedes por su tiempo y atención.

Ha sido un placer presentarles nuestro trabajo. Quedamos a su disposición para cualquier pregunta que puedan tener."

**(Pausa para preguntas)**
