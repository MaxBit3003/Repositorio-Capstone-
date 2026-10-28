# Bitácora de Proyecto - Semana 10

**Proyecto:** Red de Monitoreo Pluviométrico Resiliente IoT – HYDROTECH  
**Equipo:** Maximiliano Ancán, Lukas Heap, María González, Omar Loayza  
**Fecha de registro:** 27 de octubre de 2026  

## Objetivos de la Semana
- Consolidar la investigación, el diseño técnico y el modelo operativo en el Informe Intermedio de Capstone.
- Sintetizar la propuesta de valor, la arquitectura IoT y el plan de implementación en un Pitch a presentar el 27 de Octubre 
- Defender exitosamente la viabilidad técnica y económica del proyecto.
- Definir los requerimientos materiales, digitales e institucionales para el inicio de la fase de construcción en noviembre.

## Actividades Realizadas y Acuerdos Técnicos

### 1. Redacción y Estructuración del Informe Intermedio (26 páginas)
Se consolidó todo el trabajo del semestre en el documento oficial de ingeniería (Capstone Intermedio). Las secciones clave desarrolladas y pulidas incluyeron:
- **Modelo de uso e implementación:** Definición de los roles comunitarios (observadores locales) e institucionales (GRD municipal, SENAPRED, SERNAGEOMIN).
- **Diseño Técnico:** Detalle exhaustivo de la capa física (ESP32, pluviómetro HX711, geófono desacoplado para evitar falsos positivos por viento, RTC DS1307, módulo LoRaWAN y MicroSD para resiliencia offline).
- **Plan de Validación:** Establecimiento de los 8 indicadores de éxito (P1 a P8) para certificar el hardware en noviembre, incluyendo precisión ≤ 10%, autonomía de 72 h, y resiliencia de datos al 100%.
- **Matriz de Riesgos y Factibilidad:** Evaluación económica que confirma el costo <$100 USD por nodo, contrastando con soluciones comerciales inaccesibles para el municipio.

### 2. Diseño del Pitch Deck Comercial y Técnico (9 diapositivas)
Se elaboró el material de apoyo visual para la presentación de Capstone, logrando resumir la complejidad del proyecto en un flujo claro:
- **Contexto y Evidencia:** Uso de líneas de tiempo y mapas oficiales de peligro (SERNAGEOMIN) para justificar la necesidad en San José de Maipo y priorizar las 5 zonas críticas (Z1 a Z5, empezando por el piloto en San Alfonso).
- **Arquitectura de la Solución:** Diagramación visual del ecosistema (Captación, Procesamiento local, Transmisión doble vía, Gestión centralizada y Alerta in-situ).
- **Evidencia del Prototipo Digital:** Inclusión de las validaciones lógicas desarrolladas en simulador (Wokwi) y los dashboards de prueba generados mediante scripts de Python y SQLite (Google Colab).

### 3. Defensa del Proyecto (Hito Capstone Intermedio)
El equipo presentó oficialmente el proyecto HYDROTECH ante la comisión de la universidad. 
- **Resultado:** Defensa exitosa. Se logró comunicar efectivamente el altísimo valor social y la robustez ingenieril de la propuesta, obteniendo luz verde para avanzar hacia la fase de construcción y ensamble de hardware.

### 4. Resolución de Recursos y Permisos Indispensables para el Arranque
Se dio respuesta estructurada a los requerimientos críticos para iniciar las actividades prácticas:
- **Hardware Fundamental:** Se determinó que lo primero y más urgente es adquirir la balanza (celda de carga) y el microcontrolador ESP32. 
- **Componentes de Soporte:** A la par, se requiere contar con el geófono, el reloj RTC, el módulo MicroSD y el panel solar para la autonomía energética.
- **Software y Normativa:** Es indispensable disponer de las líneas de código en Python (para el pipeline de datos) y alinear la instalación con los protocolos oficiales de SERNAGEOMIN.
- **Acuerdo de Instalación:** La obtención y calibración de todos estos recursos permitirá proceder con la instalación física del prototipo en terreno durante la última semana del mes (noviembre).

## Próximos Pasos (Plan de Noviembre)
- **Fase de Hardware:** Transición del prototipo digital (Wokwi) al nodo físico, asegurando la adquisición de los componentes listados.
- **Calibración:** Armado de la balanza (celda HX711) con pesas patrón y acondicionamiento del sensor piezoeléctrico.
- **Pruebas de Terreno:** Validación del firmware v1.1, test de autonomía energética con panel solar y prueba de enlace LoRaWAN in situ.
