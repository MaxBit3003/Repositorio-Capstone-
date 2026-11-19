# 🪵 Bitácora de Desarrollo: HydroTech 3D (Cajón del Maipo)

> **Bitácora 17 de Noviembre**  
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

## Bitácora — 19 de noviembre de 2026

### Resumen del avance
Hoy se trabajó en el diseño paramétrico en CadQuery (en Google Colab), validación geométrica con `trimesh`, visualización de mallas en ViewSTL y definición funcional de componentes clave para el nodo pluviométrico **HydroTech**.

### Actividades y decisiones técnicas
* **Base de la caja con ranura deslizable para acrílico**: se ajustó el diseño para mantener el piso, las 3 paredes (laterales y trasera), el pedestal para la celda de carga y la parte frontal abierta con una ranura inferior donde desliza el panel acrílico de 3 mm.
* **Platos de pata para feria (sin estaca)**: se evaluó el uso de platos planos para apoyo en mesa durante ferias/presentaciones, recomendando mejorar la sujeción del tornillo M20 y añadir base antideslizante para mayor estabilidad lateral.
* **Subconjunto superior (poste central, faldita tipo paraguas y plataforma superior)**: se definió mantener el poste y la plataforma superior por separado para facilitar el montaje, la orientación/resistencia en impresión 3D y la impresión sin soportes, y se modeló la faldita tipo paraguas como botaguas sin contacto con la tapa para no interferir en la medición de la celda de carga.
* **Nivel de burbuja**: se documentó su rol para verificar la horizontalidad del equipo tanto en terreno como en feria y lograr lecturas consistentes y buena alineación del conjunto.
* **Reparación de `Pieza_A_Esquinero_Tornillo_M20.stl`**: se reemplazó el barrido helicoidal que generaba malla abierta (`Cerrada: False`) y volumen anómalo (`1.6 cm³`) por una construcción sólida con filetes anulares, logrando `Cerrada: True` y un volumen de `31.5 cm³`.
* **Cálculo de volumen, gramaje estimado y dimensiones**: se instaló `trimesh` en Google Colab y se verificaron volúmenes, pesos teóricos sólidos, estimaciones orientativas al ~45% y dimensiones en mm de los 8 archivos `.stl` generados.

### Archivos `.stl` validados en Colab (`Cerrada: True`)
| Archivo STL | Volumen ($\text{cm}^3$) | Peso sólido (100%) | Estimación (~45%) | Estado malla |
| :--- | :---: | :---: | :---: | :---: |
| `Pieza_1_Base_Caja.stl` | `254.2` | `317.7 g` | `143.0 g` | `True` |
| `Pieza_2_Tapa_Falda.stl` | `96.4` | `120.5 g` | `54.2 g` | `True`|
| `Pieza_5_Plato_Pata_Feria.stl` | `21.7` | `27.1 g` | `12.2 g` | `True`|
| `Pieza_A_Esquinero_Tornillo_M20.stl` | `31.5` | `39.3 g` | `17.7 g` | `True`|
| `Pieza_B_Base_Estaca_Rueda_M20.stl` | `40.0` | `50.0 g` | `22.5 g` | `True` |
| `Plataforma_Superior.stl` | `44.2` | `55.2 g` | `24.9 g` | `True`|
| `Poste_Central.stl` | `16.8` | `21.0 g` | `9.5 g` | `True`|
| `Faldita_Paraguas.stl` | `5.4` | `6.7 g` | `3.0 g` | `True`|

### Próximos pasos
* Preparar las piezas restantes del listado final y avanzar con la impresión y pruebas de encaje.
