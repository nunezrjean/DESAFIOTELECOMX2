🚀 Análisis de Evasión de Clientes (Churn) en Telecom X
Este repositorio contiene un análisis exhaustivo y un modelo predictivo para identificar los factores que influyen en la evasión de clientes (Churn) en la empresa de telecomunicaciones Telecom X.

📋 Contenido
Introducción
Objetivo del Proyecto
Metodología
Factores Clave de Evasión
Modelos Predictivos
Conclusiones y Recomendaciones
Estructura del Repositorio
📝 Introducción
La retención de clientes es un pilar fundamental para la sostenibilidad y el crecimiento de cualquier empresa, especialmente en el sector de las telecomunicaciones, donde la adquisición de nuevos clientes es significativamente más costosa que la retención de los existentes. Este proyecto se enfoca en comprender y predecir el comportamiento de los clientes de Telecom X que deciden cancelar sus servicios, con el fin de desarrollar estrategias proactivas de retención.

🎯 Objetivo del Proyecto
El objetivo principal de este proyecto es:

Identificar los factores clave que impulsan la evasión de clientes (Churn) en Telecom X.
Desarrollar modelos predictivos de Machine Learning capaces de anticipar qué clientes tienen una alta probabilidad de cancelar su servicio.
Proponer estrategias de retención basadas en los hallazgos del análisis para mitigar el churn y mejorar la lealtad del cliente.
🛠️ Metodología
El proyecto siguió un enfoque estructurado de análisis de datos y modelado predictivo:

Extracción de Datos: Carga de datos desde una API pública (TelecomX_Data.json) y conversión a un DataFrame de Pandas.
Exploración y Limpieza de Datos (EDA):
Identificación y tratamiento de valores ausentes (ej. cargo_total).
Normalización de nombres de columnas y estandarización de valores de texto.
Conversión de tipos de datos (churn a binario, numéricos).
Creación de nuevas características (Cuentas_Diarias).
Análisis Descriptivo y Visualización:
Estadísticas descriptivas de variables numéricas y categóricas.
Análisis de la tasa general de churn y su distribución.
Visualizaciones detalladas de la relación entre variables clave y el churn.
Preparación de Datos para Modelado:
Eliminación de columnas sin valor predictivo (ej. id_cliente).
Codificación One-Hot de variables categóricas (pd.get_dummies).
Análisis del balance de clases de la variable objetivo (churn).
Escalado de variables numéricas (StandardScaler, MinMaxScaler) para diferentes tipos de modelos.
División del dataset en conjuntos de entrenamiento y prueba (80/20, estratificado).
Entrenamiento y Evaluación de Modelos Predictivos:
Regresión Logística: Modelo lineal interpretado con StandardScaler y class_weight='balanced'.
Árbol de Decisión: Modelo basado en árboles sin escalado, con max_depth limitado y class_weight='balanced'.
Evaluación basada en métricas clave para problemas de clasificación desbalanceados (Recall, Precision, F1-Score, AUC-ROC).
Análisis de matrices de confusión y feature importance/coeficientes.
Validación cruzada para evaluar la estabilidad de los modelos.
📊 Factores Clave de Evasión
El análisis reveló los siguientes factores como los más influyentes en la probabilidad de que un cliente cancele su servicio:

Antigüedad del Cliente (meses_contrato): Los clientes con menor antigüedad (< 12-18 meses) son los más propensos a la evasión (correlación negativa fuerte).
Tipo de Contrato (tipo_contrato): Los clientes con contratos mes a mes tienen una tasa de churn significativamente más alta (42.7%) en comparación con contratos de 1 o 2 años.
Tipo de Servicio de Internet (tipo_internet_Fiber optic): Los usuarios de fibra óptica muestran una tasa de churn elevada (41.9%), sugiriendo posibles problemas con el servicio.
Método de Pago (metodo_pago_Electronic check): El cheque electrónico está fuertemente asociado con una alta tasa de churn (45.3%).
Cargos Mensuales (Cuentas_Diarias): Clientes con cargos mensuales más altos tienden a cancelar más, lo que puede indicar una percepción de bajo valor por el precio.
Facturación Digital (factura_digital_Yes): Una mayor tasa de churn entre quienes usan factura digital (33.6%).
Adulto Mayor (adulto_mayor): Los adultos mayores tienen una tasa de churn casi el doble que otros segmentos.
🤖 Modelos Predictivos
Se evaluaron dos modelos principales, con el siguiente rendimiento en el conjunto de prueba:

Modelo	Accuracy	Precision	Recall	F1-Score	AUC-ROC
Regresión Logística	0.7395	0.5060	0.7834	0.6149	0.8432
Árbol de Decisión	0.7324	0.4975	0.8048	0.6149	0.8332
Veredicto: La Regresión Logística se selecciona como el modelo principal debido a su mejor balance entre AUC-ROC (capacidad discriminatoria general) y Precision, además de su interpretabilidad (los coeficientes permiten entender el impacto de cada variable). El Árbol de Decisión es un buen complemento por su interpretabilidad y Recall ligeramente superior.

✅ Conclusiones y Recomendaciones
Los hallazgos de este análisis subrayan la importancia de la proactividad en la gestión de clientes. Se proponen las siguientes estrategias de retención:

Programas de Fidelización Temprana: Dirigidos a clientes nuevos durante sus primeros 12-18 meses, periodo de alto riesgo.
Incentivos para Contratos a Largo Plazo: Promocionar activamente los contratos de 1 o 2 años para reducir la volatilidad de los clientes mes a mes.
Optimización del Servicio de Fibra Óptica: Investigar y mejorar la calidad del servicio, el soporte técnico y la competitividad de precios para usuarios de fibra óptica.
Promoción de Métodos de Pago Automáticos: Fomentar la adopción de transferencias bancarias y tarjetas de crédito automáticas, alejando a los clientes del cheque electrónico.
Experiencia Mejorada para Adultos Mayores: Diseñar productos y soporte técnico adaptados a las necesidades específicas de este segmento.
Revisión de Facturación Digital: Mejorar la claridad y facilidad de uso de la factura digital.
Análisis de Cargos Mensuales: Ofrecer revisiones periódicas de planes para clientes con altos cargos mensuales, asegurando que perciban un buen valor.
📂 Estructura del Repositorio
├── README.md
├── telecomx_churn_categoricas.png
├── telecomx_gasto_churn.png
├── telecomx_train_test_split.png
├── telecomx_correlacion_completa.png
├── telecomx_meses_churn.png
├── telecomx_churn_numericas.png
├── telecomx_correlacion_top15.png
├── telecomx_evaluacion_modelos.png
├── telecomx_correlacion_barplot.png
├── telecomx_clean.csv
├── telecomx_modelos.png
├── telecomx_churn_distribucion.png
├── telecomx_escalado.png
├── telecomx_balance_clases.png
└── ... (otros archivos y datos)
