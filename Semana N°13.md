# 🪵 Bitácora de Desarrollo: HydroTech 3D (Cajón del Maipo)

> **Bitácora de Proyecto**  
> **Contexto:** Estación de monitoreo hidrológico portátil y autonivelante diseñada para condiciones de terreno complicadas en el Cajón del Maipo.

---

## 📋 1. Resumen del Proyecto
El proyecto **HydroTech 3D** surge de la necesidad de desplegar estaciones de monitoreo de caudal y precipitación autónomas, robustas y de fácil calibración en zonas cordilleranas (Cajón del Maipo). El sistema integra un chasis impreso en 3D, celdas de carga de alta precisión, paneles acrílicos y un sistema innovador de nivelación con anclaje directo a tierra que prescinde de soportes metálicos complejos.

---

## 🛜 2. Prototipado y Validación Conceptual (Claude AI)
En la fase inicial de diseño conceptual y modelado en colaboración con inteligencia artificial, se definieron los siguientes componentes estructurales y electrónicos principales:

*   **Caja principal:** Estructura monolítica de piso y tres paredes optimizada para impresión en **PETG**.
*   **Panel frontal:** Acrílico transparente de $3mm$ cortado por láser, albergando la pantalla LCD y los indicadores de estado (nivel medio, intensidad de $3.0\text{mm/h}$, acumulado de $8.72\text{mm}$, y masa censada de $55.5\text{g}$).
*   **Sistema de pesaje:** Celda de carga de aluminio equipada con galgas extensiométricas para la medición dinámica del volumen de agua recolectado en el embudo superior.
*   **Tapa con falda:** Elemento superior sellado que incorpora un nivel de burbuja integrado para una rápida comprobación visual de la horizontalidad en campo.

---

## 📐 3. Ingeniería de Detalle: Sistema de Nivelación ($17 \times 17$ cm)
Para asegurar lecturas precisas de la celda de carga en terrenos irregulares de montaña, se diseñó un sistema de nivelación integrado directamente en las 4 esquinas de la placa base ($170 \times 170~\text{mm}$).

### Componentes del Sistema Mecánico:
1.  **Esquinero con Tornillo Integrado (Pieza A $\times 4$):**
    *   Ala en escuadra de $35 \times 35~\text{mm}$ con ranura de acople para la placa base ([Grosor] $+ 0.4~\text{mm}$).
    *   Tornillo vertical integrado con rosca macho tipo $M20 \times 3.0~\text{mm}$ (largo útil de $95~\text{mm}$).
2.  **Base Estaca con Rueda Niveladora (Pieza B $\times 4$):**
    *   Plato base circular de $\emptyset 55~\text{mm}$ con rosca hembra pasante $M20$ y rueda moleteada superior para ajuste fino.
    *   Estaca inferior en cruz de $50~\text{mm}$ de longitud con 4 aletas estabilizadoras para evitar la rotación al clavarla en el terreno.

---

## 🖨️ 4. Parámetros de Impresión 3D y Fabricación

Para garantizar la resistencia mecánica a la intemperie y la funcionalidad de las roscas sin soportes, se establecieron los siguientes parámetros en slicer:

| ID | Componente Monolítico | Cant. | Material Recomendado | Orientación en Cama | Relleno / Paredes |
| :---: | :--- | :---: | :---: | :--- | :--- |
| **A** | Esquinero + Tornillo Integrado | 4 | PETG / ASA | Invertida (cuna en cama, rosca hacia arriba) | $35\%$ / 4 paredes |
| **B** | Base Estaca con Rueda Niveladora | 4 | PETG / ASA | Invertida (rueda en cama, estaca hacia arriba) | $40\%$ / 5 paredes |

### ⚙️ Consideraciones de Tolerancia y Roscas:
*   **Impresión 100% sin soportes:** Todas las piezas se diseñaron para apoyarse directamente sobre su cara plana más ancha en la cama caliente.
*   **Holgura de Roscas:** Se aplicó un offset de $-0.18~\text{mm}$ en los flancos de la rosca macho (Pieza A) y $+0.18~\text{mm}$ en la rosca hembra (Pieza B), logrando una holgura total de $0.36~\text{mm}$ idónea para tolerar variaciones térmicas y de humedad en exteriores.

---

## ⛰️ 5. Protocolo de Montaje y Calibración en Terreno
1. **Pre-ensamblaje:** Enroscar las 4 bases estaca (**Pieza B**) a media altura en los esquineros principales (**Pieza A**).
2. **Anclaje:** Encajar los 4 esquineros en la placa objetivo de $17 \times 17~\text{cm}$ y presionar firmemente de forma vertical para clavar las estacas en cruz en la tierra hasta que los platos base de $\emptyset 55~\text{mm}$ hagan tope con el suelo.
3. **Nivelación Fina:** Girar cada rueda moleteada para ajustar la altura de manera independiente hasta centrar la burbuja del nivel integrado en la tapa.
