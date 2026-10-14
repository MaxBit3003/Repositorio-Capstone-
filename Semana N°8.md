# Bitácora de Proyecto - Capstone Intermedio
**Semana:** 8
**Fecha:** Martes, 13 de Octubre de 2026
**Grupo:** HYDROTECH (Maximiliano Ancán, Lukas Heap, María González, Omar Loayza)

## 1. Objetivos de la Sesión
* Evaluar las propuestas conceptuales generadas para el monitoreo pluviométrico.
* Definir y consolidar una propuesta única para la entrega de la Unidad 2, alineada con las exigencias del informe "Capstone Intermedio".
* Analizar opciones técnicas para mejorar la detección de remociones en masa.

## 2. Actividades Realizadas
Durante la jornada de la tarde, el equipo se reunió para discutir el avance del proyecto y tomar decisiones clave de diseño:

### A. Revisión y Consolidación de Propuestas
* Se analizaron las fichas comparativas de las 3 propuestas iniciales (Propuesta 1: Transmisión en tiempo real, Propuesta 2: Resiliencia de datos offline, Propuesta 3: Monitoreo visual/térmico).
* **Decisión técnica:** Acordamos fusionar la Propuesta 1 y la Propuesta 2. La solución final se llamará **"Red de Monitoreo Pluviométrico Resiliente IoT"**.
* **Justificación:** Se concluyó que un sistema robusto necesita tanto la transmisión en tiempo real (vía LoRaWAN) como un plan de contingencia ante caídas de red o cortes eléctricos (guardado local en Micro SD con estampa de tiempo RTC).

### B. Redacción de la Ficha de la Unidad 2
* Trabajamos en estructurar la solución bajo los requerimientos del PDF de Capstone. 
* Definimos el flujo de datos: 
  * Captación del volumen de lluvia mediante un sistema de balanza.
  * Procesamiento en el microcontrolador (ESP32/Arduino).
  * Envío a la nube (AWS IoT o The Things Network) o almacenamiento en el búfer local según la disponibilidad de conexión.
  * Activación del semáforo LED local como alerta social directa.

### C. Brainstorming: Detección de Remociones en Masa
* Discutimos la viabilidad de agregar un sensor de movimiento al pluviómetro para detectar deslizamientos de tierra.
* **Conclusión:** Descartamos los sensores de movimiento infrarrojos (PIR) debido al alto riesgo de falsos positivos (animales, viento).
* **Alternativas evaluadas:** Se planteó la posibilidad de integrar un acelerómetro/inclinómetro (como el MPU6050) en el poste del equipo para detectar la deformación del terreno, y/o retomar el módulo ESP32-CAM para confirmación visual por parte del observador.

## 3. Acuerdos y Próximos Pasos
1. **Documentación:** Copiar la estructura definida hoy en el Google Doc oficial para la entrega de la Unidad 2.
2. **Investigación de Hardware:** Evaluar el costo y la dificultad de integrar un módulo MPU6050 (acelerómetro) al circuito del ESP32.
3. **Lista de Materiales:** Consolidar el listado final de componentes (ESP32, balanza, módulo LoRa, módulo SD, RTC, luces LED y panel solar) para iniciar la factibilidad económica de la Unidad 3.
