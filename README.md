# 📊 Integración de Datos CRM y Dashboard de Pipeline Comercial

Un proyecto integral (end-to-end) de análisis de datos e inteligencia de negocio. Este proyecto simula un escenario empresarial real donde los datos brutos y fragmentados de un CRM heredado son ingeridos, monitoreados mediante una cola de trabajo y consolidados en un dashboard ejecutivo interactivo construido en Google Sheets.

**[Accede aquí al Dashboard en vivo en Google Sheets](https://docs.google.com/spreadsheets/d/1f30Ax8rafwd7BHR2Mo2u8ivb5ZJk4WpxQEjpvnMVyRI/edit?usp=sharing)**

---

## 🏢 Contexto de Negocio y Visión General
Cuando las empresas migran o actualizan su infraestructura de CRM, a menudo se enfrentan a datos "sucios" y fragmentados en tablas separadas. Este proyecto resuelve exactamente ese problema.

A partir de un dataset relacional en bruto con **8,801 registros**, asumí el rol de Data Analyst responsable de todo el ciclo de onboarding de datos: desde la gestión de la cola de ingesta hasta el modelado de la base de datos y el diseño de la analítica final para negocio.

### Principales Hitos Logrados:
*   **Gestión de Procesos y Cola de Ingesta:** Implementación de un sistema de `Migration_Log` para controlar prioridades, fechas de entrega (ETAs) y estados de ETL de flujos de datos concurrentes, simulando un entorno real de operaciones.
*   **Modelado de Datos Relacionales:** Consolidación de 4 entidades independientes (`sales_pipeline`, `accounts`, `products`, `sales_teams`) mediante el uso de funciones de búsqueda avanzadas (`INDEX/MATCH`).
*   **Limpieza de Datos y Control de Calidad:** Conversión de fechas en formato de texto a estándares limpios, gestión de valores nulos en fechas de cierre y normalización de categorías heterogéneas de la industria.
*   **Diseño de Dashboard con Criterio UI/UX:** Desarrollo de un panel ejecutivo altamente escaneable centrado en la salud del pipeline, la eficiencia del equipo de ventas y el seguimiento de los ingresos.

---

## 🔌 Origen de los Datos
El dataset utilizado para este proyecto ha sido obtenido del *Data Playground* de **Maven Analytics** ([CRM Sales Opportunities](https://mavenanalytics.io/data-playground/crm-sales-opportunities)), una plataforma de referencia global en la formación y desafíos de Business Intelligence. 

Este set de datos en bruto fue seleccionado específicamente porque emula a la perfección la complejidad de un entorno corporativo real, presentando datos fragmentados y relacionales que requieren un proceso riguroso de ingeniería, modelado y limpieza antes de poder extraer cualquier valor analítico.

---

## 🗂️ Cola de Ingesta y Arquitectura de Datos
En lugar de trabajar con un archivo plano pre-cocinado, el proyecto gestiona una estructura de base de datos relacional en bruto utilizando un diccionario de datos.

### 1. Control del Proceso (`Migration_Log`)
Para garantizar una gestión disciplinada en el seguimiento de las cargas, se construyó un registro de migración que controla estados, prioridades y notas operativas del analista:

<img src="https://github.com/Elian-digital/crm-sales-pipeline-analytics/blob/main/images/Migration_Log.png?raw=true" width="900">

### 2. Modelo Relacional
Los datos se mapearon y conectaron a través de cuatro tablas principales:
*   **`sales_pipeline` (Tabla de Hechos):** Seguimiento central de oportunidades, valores de transacciones, etapas del pipeline y comerciales asignados.
*   **`accounts` (Dimensión):** Perfiles de empresas, segmentos de mercado y clasificaciones de la industria.
*   **`products` (Dimensión):** Niveles de software/productos y modelos de precios base.
*   **`sales_teams` (Dimensión):** Jerarquías de ventas internas que conectan a los agentes con sus respectivos mánagers.

---

## 🎨 Diseño del Dashboard y Visualizaciones
El dashboard ejecutivo se diseñó prestando especial atención a las buenas prácticas de visualización de datos y al diseño de interfaces modernas (UI/UX), evitando los estilos saturados y por defecto de las hojas de cálculo:

<img src="https://github.com/Elian-digital/crm-sales-pipeline-analytics/blob/main/images/Dashboard.png?raw=true" width="900">

*   **KPIs Ejecutivos:** Tarjetas de resumen de alto nivel que muestran las Ventas Totales, el Valor del Pipeline, el Win Rate Global y el Tiempo Medio de Cierre para una alineación instantánea de los stakeholders.
*   **Enfoque Operativo:** Gráficos optimizados de rendimiento comercial que destacan únicamente el **Top 5** y el **Bottom 5** de agentes para impulsar estrategias de coaching accionables, en lugar de saturar la vista con filas interminables de nombres.
*   **Controles Interactivos:** Filtros globales (*Slicers*) por Mes y Mánager que permiten realizar análisis exploratorios profundos durante las reuniones de negocio.

---

## 📈 Conclusiones e Insights de Negocio
Se integró una sección dedicada a **Conclusiones Ejecutivas** directamente en el proyecto para entregar hallazgos claros y concisos a perfiles no técnicos, yendo más allá de la simple visualización de gráficos:

<img src="https://github.com/Elian-digital/crm-sales-pipeline-analytics/blob/main/images/Insights.png?raw=true" width="400">

*   **Comportamiento Estable:** El pipeline muestra picos claros de ingresos en junio y septiembre, impulsados por ciclos comerciales trimestrales.
*   **Productos Estrella:** El volumen mensual se mantiene constante entre 600 y 800 oportunidades. *GTXPro* y *GTX Plus Pro* actúan como los motores del negocio, generando más del 60% del revenue total.
*   **Eficiencia del Equipo:** El equipo comercial presenta un win rate global sólido (63,14%), liderado en volumen y eficiencia por los agentes principales, mientras que la distribución por etapas refleja un pipeline sano y equilibrado.

---

## 🛠️ Tecnologías y Fórmulas Utilizadas
*   **Herramienta:** Google Sheets / Excel Power User.
*   **Fórmulas Clave:** `INDEX/MATCH` para el mapeo relacional, lógica con `IFS` para la categorización dinámica, funciones de manipulación de texto y fechas para el proceso ETL, validación de datos para filtros interactivos y formato condicional para la gestión de la cola de procesos.
