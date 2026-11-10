# Bitácora de Proyecto: HydroTech 💧🏔️

**Fecha:** 10 de noviembre de 2026

**Contexto:** Avance de Prototipo Fase 1 y Presentación Intermedia

## 📌 Actividades de la Sesión

### 1. Presentación de Avances y Definición de Roles 📊

Hoy presentamos oficialmente nuestro documento de avance ("HYDROTECH Capstone.pdf"), pasando de la simulación teórica (Wokwi) al primer montaje físico de nuestra red de monitoreo pluviométrico. 

Además, dejamos consolidados los roles del equipo de cara a la Feria Capstone (3 de diciembre):
*   **Maximiliano Ancán:** Lidera el Pitch (problema, solución, impacto y viabilidad).
*   **Lukas Heap:** Encargado del Firmware y datos (lectura, pantalla LCD, semáforo y exportación CSV).
*   **Omar Loayza:** Encargado del Hardware (embudo, celda de carga, montaje físico y seguridad).
*   **María González:** Coordinación general (afiche, recepción de visitantes y logística del stand).

### 2. Dinámica de Trabajo: "Egg Drop Challenge" 🥚🪂

Participamos en un desafío de diseño estructural y amortiguación para poner a prueba nuestra creatividad con materiales limitados.

*   **Objetivo:** Proteger un huevo de una caída libre desde **3 metros** de altura.
*   **Materiales utilizados:** Media botella de plástico (Kem Zero), toalla Nova, papel, goma eva, bombillas, plástico de burbujas, cinta masking tape, bolsa Ziploc y una bolsa de Rappi que adaptamos como paracaídas.
*   **Resultados:** ¡Amortiguación exitosa! El huevo aterrizó completamente **intacto**.
*   **Aprendizajes:** Comprobamos que con pocos materiales bien distribuidos se puede absorber un gran impacto. Como oportunidad de mejora, en una próxima versión colocaríamos el huevo en posición vertical para distribuir mejor las fuerzas.

### 3. Construcción del Prototipo - Fase 1 🌧️💻

Trabajamos intensamente en el ensamblaje de nuestro primer prototipo físico funcional (nodo pluviométrico), logrando integrar la mecánica y la electrónica:

*   **Estructura y Protección:** Armamos una carcasa utilizando cartón piedra de color negro. Esto nos permite proteger el circuito electrónico (microcontrolador y sensores) para que no se moje durante las pruebas de simulación de lluvia.
*   **Sistema de Captación:** Fabricamos el embudo colector cortando una botella plástica reutilizada, la cual guía el agua de manera precisa hacia el recipiente de medición.
*   **Hardware y Electrónica:** 
    *   Integramos la **celda de carga** junto con su módulo amplificador **HX711**.
    *   Conectamos todo al microcontrolador **ESP32**.
    *   Añadimos una **pantalla LCD I2C** que ya muestra la masa actual del agua captada.
    *   Todo el sistema está siendo alimentado de forma autónoma mediante una pila.
*   **Transmisión de Datos:** ¡Logramos telemetría básica! El sistema arroja los datos leídos por la celda de carga directamente a la pantalla LCD y los transmite al teléfono celular en tiempo real, con una latencia muy baja (se demora entre 5 a 10 segundos en reflejar la lectura).

## 🚀 Próximos Pasos

Nuestro objetivo principal ahora es afinar la precisión frente a volúmenes conocidos (buscando un error ≤10%) y comenzar a integrar la lógica de los LEDs (semáforo de estados experimentales) y el almacenamiento local en microSD.
