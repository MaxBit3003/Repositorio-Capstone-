# Registro de Actividades - Grupo HydroTech
**Semana:** 6
**Fase del Proyecto:** Definición de Soluciones, Componentes y Diseño Conceptual

Durante la sesión de esta semana, el equipo trabajó en la estructuración técnica de nuestras soluciones para el desafío asignado. Se definió que la **Propuesta 1** será el sistema núcleo de nuestro proyecto, mientras que las **Propuestas 2 y 3** funcionarán como módulos complementarios que fortalecerán y escalarán la propuesta principal en etapas posteriores. 

A continuación, se detalla el diseño conceptual y los componentes de cada propuesta desarrollados en clase:

## 1. Propuesta Principal (Núcleo): Pluviómetro de Pesaje IoT
Esta solución busca el fortalecimiento del sistema de recarga para mantener una constancia de datos en tiempo real, implementando un puesto de recarga solar. Se contempla una fase de prueba instalando entre 3 a 5 unidades en puestos donde ya existen pluviómetros. 

**Diseño Conceptual y Físico:** 
*   El dispositivo es de carácter portátil.
*   Estará fabricado utilizando materiales reciclables.
*   El sistema de medición se basa en una balanza interna que mide el peso del agua para, a partir de este, calcular el volumen (V) de precipitación.

**Arquitectura de Hardware y Transmisión:**
*   El procesamiento local estará a cargo de un microcontrolador, que puede ser un ESP32 o un Arduino.
*   El sistema de transmisión contará con un módulo para enviar la información a la nube.
*   Integra un semáforo LED exterior que indica visualmente el nivel de peligro mediante los colores verde, amarillo y rojo.
*   Se utilizará tecnología LoRaWAN para conectar los sensores a internet a larga distancia.

**Arquitectura de Datos y Software:**
*   **Recepción:** Los datos de la nube serán recibidos por un observador.
*   **Alojamiento en la Nube:** La información llegará a plataformas de IoT como AWS IoT o The Things Network.
*   **Procesamiento (ETL):** Se emplearán scripts automatizados escritos en Python que se encargarán de leer los datos, limpiarlos e insertarlos como registros estructurados.
*   **Base de Datos:** Los registros estructurados se almacenarán en motores de bases de datos relacionales como SQLite, PostgreSQL o MySQL.

---

## 2. Propuestas Complementarias (Módulos de Expansión)
Estas soluciones están diseñadas para sumarse a la Propuesta 1, dotándola de mayor resiliencia y capacidad de monitoreo.

### 2.1. Propuesta 2: Sistema de Red "Offline" con Transmisión Diferida
Este módulo resuelve la pérdida de conectividad en zonas remotas, integrando un módulo de resiliencia de datos directamente al pluviómetro.

**Componentes del Módulo:**
*   Lector de tarjeta Micro SD o memoria flash interna para el almacenamiento local seguro.
*   Módulo de reloj en tiempo real (RTC) para establecer y estampar la hora exacta de cada medición.
*   Microcontrolador configurado con capacidad de gestión de búfer de datos para retener y enviar los paquetes una vez se recupere la señal.

### 2.2. Propuesta 3: Monitoreo Visual y Térmico 24/7
Este sistema complementario añade una capa de validación visual instalando cámaras en los pluviómetros ya existentes.

**Diseño Conceptual y Operación:**
*   Utiliza un módulo ESP32-CAM programado para entrar en modo de suspensión y despertarse cada 15 a 30 minutos.
*   Al despertar, toma una fotografía de las condiciones y la transmite a un servidor.
*   Para la operación nocturna, el sistema hace uso de los sensores infrarrojos integrados en la misma cámara.
*   **Flujo de Alerta:** Las imágenes llegan a una nube donde un observador las analiza; en caso de anomalías, esta información se enviaría a Sernageomin.

---

## 3. Iniciativa Adicional: Conciencia Social
Como línea de acción paralela, el equipo planteó la interrogante: *"¿Por qué no hay un pluviómetro por casa?"*. 
*   **Acción propuesta:** Generar una encuesta comunitaria y diseñar una campaña de persuasión para incentivar la adopción de pluviómetros domiciliarios.

## 4. Esbozo Conceptual del Prototipo Físico (Propuesta 1)
Para materializar la arquitectura física de la solución principal, se desarrolló un esquema preliminar que detalla la disposición de los componentes del pluviómetro de pesaje IoT. Este modelo ilustra la integración mecánica y energética del equipo:

*   **Sistema de Captación y Medición:** El núcleo del dispositivo consta de una carcasa que alberga un embudo receptor superior, estabilizado por una cruceta de soporte central (como se observa en la vista en planta del dibujo). Este embudo tiene la función de canalizar el flujo de precipitación hacia un recipiente de contención suspendido en el interior.
*   **Mecanismo de Celda de Carga:** El recipiente de almacenamiento cuelga directamente de un anclaje superior que funciona como el mecanismo de pesaje principal. Esta disposición permite registrar las variaciones de masa del fluido para calcular de forma volumétrica la acumulación de agua.
*   **Módulo de Alimentación y Autonomía:** El diagrama detalla una línea de cableado de interconexión (representada en color azul) que enlaza el cuerpo central del pluviómetro con una estación de carga externa. Esta estación independiente está equipada con un arreglo de paneles solares fotovoltaicos en su cubierta, lo que garantiza la recarga continua de las baterías para sostener la operación del microcontrolador y la transmisión ininterrumpida de datos a la nube.
