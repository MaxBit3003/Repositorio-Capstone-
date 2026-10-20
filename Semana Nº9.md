# Bitácora de Proyecto - Semana 9

**Proyecto:** Red de Monitoreo Pluviométrico Resiliente IoT – HYDROTECH  
**Equipo:** Maximiliano Ancán, Lukas Heap, María González, Omar Loayza  
**Fecha de registro:** 20 de octubre de 2026  

## Objetivos de la Semana
* Afinar la propuesta técnica del prototipo.
* Integrar formalmente componentes de ingeniería civil e hidrología en la arquitectura del sistema.
* Definir los parámetros de alerta, actores involucrados y la ubicación exacta de la prueba piloto.

## Actividades Realizadas y Acuerdos Técnicos

### 1. Integración Técnica del Geófono en el Diseño
Se formalizó la inclusión de un **geófono** acoplado al terreno como elemento diferenciador de nuestra propuesta. Este instrumento de ingeniería captará las vibraciones acústicas de baja frecuencia (10 Hz - 50 Hz) generadas por el desplazamiento de masa antes de que el evento sea visible. 
* **Acuerdo de instalación:** Se determinó que el geófono no irá en el mástil principal. Para evitar falsos positivos por la vibración del panel solar a causa del viento, se instalará de forma desacoplada en un pozo somero de 20 cm aproximadamente y a 3 metros de distancia del nodo ESP32.

### 2. Definición de Umbrales Hídricos para el Semáforo LED
Se establecieron los parámetros técnicos que activarán la alerta visual in situ, basándonos en la capacidad de infiltración y saturación del suelo en cuencas de alta pendiente:
* 🟢 **Nivel Estable (Verde): < 2 mm/hora.** Lluvia absorbida naturalmente. Sin anomalías sísmicas.
* 🟡 **Nivel Crítico (Amarillo): 2 a 5 mm/hora.** Saturación de la capacidad de infiltración (aumento de presión de poros). Ruido basal difuso en el geófono. Sugiere precaución y alejamiento del cauce.
* 🔴 **Nivel de Peligro (Rojo): > 5 mm/hora (o > 3 mm en 30 min).** Superación del esfuerzo de corte del suelo. Si se acompaña de lectura acústica de baja frecuencia en el geófono, indica un flujo de detritos inminente. Riesgo extremo; sugiere evacuación preventiva del radio visual.

### 3. Mapeo de Usuarios y Actores
Se clarificó la división entre quienes operan la plataforma y quienes reciben el beneficio en terreno:
* **Usuarios directos:** Instituciones como SERNAGEOMIN, SENAPRED, cuadrillas de emergencia y observadores locales, quienes accederán a los registros estructurados en nuestra base de datos SQLite para la toma de decisiones macro.
* **Usuarios indirectos (locales):** Vecinos, turistas, arrieros y comunidad residente que transite por la zona. Ellos serán los principales beneficiarios de la alerta temprana visual y directa (Semáforo LED), ganando tiempo vital de reacción.

### 4. Ubicación del Piloto de Prueba
Tras analizar los antecedentes, se definió que la instalación y validación del prototipo se llevará a cabo en la **Quebrada de San Alfonso** (San José de Maipo). Esta decisión se fundamenta técnicamente en su clasificación como una zona de alto riesgo, de acuerdo con el mapa de peligro de flujos en la cuenca alta del río Maipo.
