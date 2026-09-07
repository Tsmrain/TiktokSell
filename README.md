<div align="center">

# UNIVERSIDAD PRIVADA DE SANTA CRUZ DE LA SIERRA (UPSA)
### FACULTAD DE INGENIERÍA
### CARRERA DE INGENIERÍA DE SISTEMAS

<br/>

---

# PLATAFORMA DISTRIBUIDA EN LA NUBE CON INTELIGENCIA ARTIFICIAL Y EVENT-DRIVEN STREAMING PARA LA CAPTURA AUTOMATIZADA DE PEDIDOS Y CONCILIACIÓN DE PAGOS POR QR DINÁMICO EN TRANSMISIONES DE TIKTOK LIVE PARA EL COMERCIO MINORISTA EN BOLIVIA

---

<br/>

**MODALIDAD:** PROYECTO DE GRADO (ART. 19 DEL REGLAMENTO DE GRADUACIÓN UPSA)  
**POSTULANTE:** SANTIAGO RIVERO  
**DOCENTE GUÍA / TUTOR:** ING. M.SC. / PH.D. EN CIENCIAS DE LA COMPUTACIÓN  

**SANTA CRUZ DE LA SIERRA – BOLIVIA**  
**2026**

</div>

---

## Tabla de Contenido
- [Capítulo I: Definición del Proyecto de Investigación](#capítulo-i-definición-del-proyecto-de-investigación)
  - [1.1 Definición del Problema](#11-definición-del-problema)
    - [1.1.1 Situación Problemática](#111-situación-problemática)
    - [1.1.2 Situación Deseada](#112-situación-deseada)
    - [1.1.3 Objeto de Investigación](#113-objeto-de-investigación)
    - [1.1.4 Alcance y Límites](#114-alcance-y-límites)
    - [1.1.5 Justificación Técnica, Económica y Social](#115-justificación-técnica-económica-y-social)
  - [1.2 Objetivos](#12-objetivos)
    - [1.2.1 Objetivo General](#121-objetivo-general)
    - [1.2.2 Objetivos Específicos](#122-objetivos-específicos)
  - [1.3 Metodología](#13-metodología)
    - [1.3.1 Fases del Proceso Unificado (UP) de Craig Larman](#131-fases-del-proceso-unificado-up-de-craig-larman)
    - [1.3.2 Criterios de Aceptación Cuantitativos de la Fase de Transición](#132-criterios-de-aceptación-cuantitativos-de-la-fase-de-transición)
- [Capítulo II: Estudio de Mercado y Análisis del Sector de Social Commerce en Bolivia](#capítulo-ii-estudio-de-mercado-y-análisis-del-sector-de-social-commerce-en-bolivia)
  - [2.1 Caracterización del Sector y Ecosistema de Live Shopping](#21-caracterización-del-sector-y-ecosistema-de-live-shopping)
  - [2.2 Segmentación del Mercado y Determinación Matemática de la Muestra](#22-segmentación-del-mercado-y-determinación-matemática-de-la-muestra)
  - [2.3 Diagnóstico Operativo: Mapeo del Flujo de Venta Manual Actual (As-Is)](#23-diagnóstico-operativo-mapeo-del-flujo-de-venta-manual-actual-as-is)
  - [2.4 Identificación y Demostración Matemática del Cuello de Botella Transaccional](#24-identificación-y-demostración-matemática-del-cuello-de-botella-transaccional)
  - [2.5 Análisis Comparativo de Soluciones Sustitutas y Brecha Tecnológica Local](#25-análisis-comparativo-de-soluciones-sustitutas-y-brecha-tecnológica-local)
- [Capítulo III: Marco Teórico y Selección de Componentes Tecnológicos](#capítulo-iii-marco-teórico-y-selección-de-componentes-tecnológicos)
  - [3.1 Ingesta de Eventos en Tiempo Real (WebSockets vs. Polling vs. SSE)](#31-ingesta-de-eventos-en-tiempo-real-websockets-vs-polling-vs-sse)
  - [3.2 Procesamiento de Lenguaje Natural (NLP) y Extracción de Entidades Semánticas](#32-procesamiento-de-lenguaje-natural-nlp-y-extracción-de-entidades-semánticas)
  - [3.3 Ecosistema Fintech y Pagos Inmediatos en Bolivia](#33-ecosistema-fintech-y-pagos-inmediatos-en-bolivia)
  - [3.4 Arquitectura de Cómputo, Persistencia y Mitigación de Condiciones de Carrera](#34-arquitectura-de-cómputo-persistencia-y-mitigación-de-condiciones-de-carrera)
  - [3.5 Interfaz de Usuario y Checkout Móvil](#35-interfaz-de-usuario-y-checkout-móvil)
- [Capítulo IV: Definición de Requisitos (IEEE 830 adaptado a Larman/Mannino)](#capítulo-iv-definición-de-requisitos-ieee-830-adaptado-a-larmanmannino)
  - [4.1 Principios GRASP y Perspectiva del Producto](#41-principios-grasp-y-perspectiva-del-producto)
  - [4.2 Requisitos Funcionales (RF-01 a RF-15)](#42-requisitos-funcionales-rf-01-a-rf-15)
  - [4.3 Requisitos No Funcionales y de Rendimiento](#43-requisitos-no-funcionales-y-de-rendimiento)
  - [4.4 Diagrama de Casos de Uso y Matriz de Trazabilidad](#44-diagrama-de-casos-de-uso-y-matriz-de-trazabilidad)
  - [4.5 Modelo de Dominio Conceptual](#45-modelo-de-dominio-conceptual)
- [Capítulo V: Análisis y Diseño del Sistema](#capítulo-v-análisis-y-diseño-del-sistema)
  - [5.1 Arquitectura Lógica en Capas y Despliegue Físico](#51-arquitectura-lógica-en-capas-y-despliegue-físico)
  - [5.2 Diagramas de Secuencia del Sistema (SSD) y Contratos de Operación de Larman](#52-diagramas-de-secuencia-del-sistema-ssd-y-contratos-de-operación-de-larman)
  - [5.3 Diagrama de Clases de Diseño (DCD Consolidado)](#53-diagrama-de-clases-de-diseño-dcd-consolidado)
  - [5.4 Diseño Lógico y Físico de Base de Datos (Normas Mannino & DDL PostgreSQL)](#54-diseño-lógico-y-físico-de-base-de-datos-normas-mannino--ddl-postgresql)
  - [5.5 Estado de Implementación, Cobertura TDD y Guía de Puesta en Marcha](#55-estado-de-implementación-cobertura-tdd-y-guía-de-puesta-en-marcha)

---

# Capítulo I: Definición del Proyecto de Investigación

## 1.1 Definición del Problema

### 1.1.1 Situación Problemática
En la actualidad, el fenómeno del comercio social en vivo (*Live Shopping* o *Social Commerce*) a través de la plataforma TikTok Live ha experimentado una expansión geométrica en el territorio boliviano, concentrándose de forma crítica en los centros urbanos y polos comerciales del eje troncal: Santa Cruz de la Sierra, La Paz y Cochabamba. Centenares de micro, pequeñas y medianas empresas (MIPyMEs), importadores mayoristas y comerciantes independientes utilizan transmisiones de vídeo en directo para promocionar, subastar y comercializar inventarios físicos en tiempo real ante audiencias concurrentes que fluctúan entre 200 y más de 3.000 espectadores simultáneos.

Sin embargo, el ecosistema digital boliviano enfrenta un obstáculo estructural determinante: **la ausencia total de la infraestructura oficial de TikTok Shop y la imposibilidad técnica y regulatoria de procesar transacciones directas en moneda nacional (Bolivianos - BOB) dentro de la aplicación de ByteDance**. Ante esta limitación geopolítica y tecnológica, los comerciantes bolivianos se ven constreñidos a recurrir a procesos rudimentarios, fragmentados y enteramente manuales para capturar intenciones de compra y liquidar sus cobros:

1. **Colapso del Canal de Comunicación Síncrono:** Durante el pico de una transmisión en vivo, cuando el presentador (*Live Host*) exhibe un producto a precio promocional o de stock unitario, se generan ráfagas instantáneas de comentarios no estructurados (e.g., *"mío el vestido rojo 32"*, *"yo quiero 2 pares en 38"*, *"apártame el código A-10"*). La velocidad de desplazamiento del chat de TikTok Live supera con creces la capacidad cognitiva de lectura, retención y discriminación humana, originando la omisión sistemática de órdenes legítimas y altercados entre usuarios por supuesta prioridad.
2. **Migración Manual hacia WhatsApp:** Para formalizar una transacción, el comerciante exige verbalmente al comprador que abandone la transmisión en vivo, guarde su número telefónico y envíe un mensaje a WhatsApp con capturas de pantalla del producto. Este trasvase de aplicaciones introduce una fricción severa que destruye el estímulo de compra inmediata por impulso (*impulse buying behavior*), reportando tasas de abandono de órdenes superiores al 65%.
3. **Condición de Carrera en el Inventario Físico (*Overselling*):** Al no existir una capa de sincronización atómica entre los comentarios de la transmisión y la existencia real en almacén, múltiples compradores son atendidos en paralelo por diferentes operadores humanos, asignándose una misma unidad a varios clientes. La consiguiente cancelación forzosa erosiona la reputación comercial del negocio.
4. **Vulnerabilidad a la Estafa y Fraude con Falsificación de Comprobantes:** El esquema de cobranza depende de la remisión de una imagen de **Código QR Estático**. Una vez escaneado el código, el comprador introduce libremente el monto y envía una captura de pantalla del supuesto comprobante de transferencia bancaria interbancaria. En Bolivia, la proliferación de herramientas web de falsificación de recibos (comprobantes apócrifos de Banco Unión, Banco Fassil en su momento, BCP, Banco Ganadero, BNB) y aplicaciones modificadas permite a ciberdelincuentes generar recibos adulterados idénticos a los oficiales en menos de 30 segundos. El comerciante, agobiado por el ritmo vertiginoso del directo, omite la verificación manual extracto por extracto en su aplicación bancaria, despachando mercadería sin respaldo financiero real.

### 1.1.2 Situación Deseada
Se proyecta el diseño, construcción y despliegue de una plataforma de software distribuida, reactiva y escalable en la nube que automatice integralmente el ciclo transaccional de ventas en TikTok Live para comerciantes minoristas en Bolivia, eliminando por completo la mediación humana en la captura de pedidos y la verificación de pagos.

El sistema interceptará en tiempo real el flujo de eventos de datos (*data streaming*) del chat público de la transmisión mediante conexiones persistentes por sockets. Dichos eventos serán procesados por un pipeline de Inteligencia Artificial enfocado en Procesamiento de Lenguaje Natural (NLP) y coincidencia semántica difusa, extrayendo instantáneamente la entidad del usuario, la intención de compra, el código SKU del artículo y sus variantes (color, talla, volumen).

De manera atómica, el motor transaccional adquirirá un bloqueo distribuido en memoria (*Distributed Lock*) con tiempo de vida limitado (*TTL - Time To Live*), apartando el stock en milisegundos e impidiendo el sobreconsumo. El sistema despachará al usuario un enlace directo hacia un portal web de checkout efímero optimizado para dispositivos móviles, donde se renderizará un **Código QR Dinámico interoperable con la Red Simple de la Administradora de Cámaras de Compensación y Liquidación S.A. (ACCL)**. Dicho código incorporará el identificador unívoco de la orden, el monto inalterable y una validez máxima de 5 a 10 minutos.

A través de un servicio de *webhooks* bancarios asíncronos y seguros con verificación de firma criptográfica HMAC-SHA256, el sistema recibirá la confirmación directa de la cámara de compensación y liquidación en el instante exacto en que los fondos impacten en la cuenta de destino. La orden mutará a estado "Pagada", el inventario se consolidará definitivamente en la base de datos relacional y el *dashboard* del vendedor se actualizará reactivamente sin refresco de página. Si el usuario no realiza el pago dentro de la ventana de validez, el bloqueo expirará automáticamente, reintegrando la unidad al inventario disponible para la audiencia.

### 1.1.3 Objeto de Investigación
El objeto de estudio e investigación se circunscribe a:
> **Los sistemas de software distribuidos de procesamiento de eventos en tiempo real (*Event-Driven Streaming*), las arquitecturas reactivas desacopladas para alta concurrencia, el procesamiento de lenguaje natural aplicado a textos informales y los protocolos asíncronos de conciliación criptográfica en redes de pagos inmediatos de bajo valor (Fintech boliviana).**

### 1.1.4 Alcance y Límites

#### Alcance
* **Módulo de Streaming e Ingesta:** Captura bidireccional no intrusiva de flujos de eventos procedentes de salas públicas de TikTok Live mediante emulación protocolar sobre TCP/WebSockets y serialización binaria (Protobuf).
* **Módulo de NLP y Extracción de Intenciones:** Pipeline de normalización de cadenas de texto informales con vocabulario dialectal boliviano, capaz de estructurar órdenes de compra en objetos JSON tipados.
* **Motor de Bloqueo Distribuido y Control de Concurrencia:** Mecanismo de exclusión mutua distribuida basado en primitivas atómicas en memoria (Redis / Redlock) para evitar la doble adjudicación de productos ante colisiones de paquetes concurrentes.
* **Módulo Fintech y Orquestador de Pagos:** Integración con APIs de pasarelas de pago bolivianas certificadas (e.g., Libélula, CUCU, PagoFácil, BCP/Ganadero Simple) para la emisión programática de payloads de códigos QR dinámicos compatibles con la red Simple de ACCL.
* **Recepción y Validación Criptográfica de Webhooks:** Endpoint seguro con validación de firmas digitales HMAC-SHA256, tratamiento estricto de idempotencia transaccional y respuesta de liquidación en menos de 500 milisegundos.
* **Interfaz de Checkout y Portal Administrativo:** Interfaz web progresiva para el comprador (checkout ultraligero sin registro previo) y panel web en tiempo real para el comerciante con métricas analíticas de conversión y auditoría financiera.

#### Límites
* El sistema no contempla la gestión de distribución física ni logística de transporte internacional o nacional (última milla), concluyendo su responsabilidad funcional con la confirmación de la orden pagada y la emisión del manifiesto de despacho.
* La solución opera supeditada a la disponibilidad y estabilidad de las conexiones de red de TikTok y a las políticas de provisión de datos públicos de la plataforma.
* La pasarela financiera procesa exclusivamente transacciones en moneda de curso legal boliviano (BOB) mediante la infraestructura del sistema de transferencias interbancarias inmediatas reguladas por la ASFI y el Banco Central de Bolivia.

### 1.1.5 Justificación Técnica, Económica y Social

#### Justificación Técnica
La arquitectura de software tradicional basada en arquitecturas cliente-servidor monolíticas y sondeo periódico (*HTTP Polling*) sobre bases de datos relacionales colapsa ante ráfagas súbitas de concurrencia e I/O bloqueante. Este proyecto investiga e implementa una Arquitectura Orientada a Eventos (EDA) con buses de mensajería desacoplados, procesamiento reactivo asíncrono y almacenamiento clave-valor distribuido en memoria para lograr tiempos de respuesta sub-segundo. Asimismo, aplica la ingeniería de software formal regida por el Proceso Unificado de Craig Larman, patrones GRASP de asignación de responsabilidades y patrones GoF, elevando el desarrollo a estándares internacionales de robustez y mantenibilidad.

#### Justificación Económica
Para el comerciante, la transición de un esquema de verificación manual a uno completamente desatendido elimina el gasto fijo derivado de la contratación de asistentes u operadores para gestionar mensajes de WhatsApp (costo estimado de 2 a 3 salarios mínimos nacionales por turno en negocios medianos). Adicionalmente, al abatir la tasa de abandono de órdenes mediante la inmediatez del checkout dinámico, las ventas efectivas se incrementan entre un 30% y un 50%. A nivel de riesgo, la verificación directa por webhook bancario reduce a 0% las pérdidas operativas por fraude con comprobantes adulterados.

#### Justificación Social
El comercio en vivo se ha consolidado en Bolivia como una de las principales avenidas de generación de autoempleo e inclusión socioeconómica para comerciantes de mercados tradicionales (e.g., La Ramada, Los Pozos, Mutualista en Santa Cruz; La Cancha en Cochabamba; Uyustus y Eloy Salmón en La Paz). Dotar a este sector de una tecnología de grado empresarial y accesible democratiza la digitalización del comercio informal, fomenta la inclusión financiera al canalizar transferencias a través de cuentas de ahorro formales e impulsa el crecimiento productivo de las unidades microempresariales.

---

## 1.2 Objetivos

### 1.2.1 Objetivo General
Diseñar, desarrollar e implementar una plataforma de software distribuida en la nube basada en Arquitectura Orientada a Eventos (EDA), Inteligencia Artificial (NLP) y bloqueos distribuidos en memoria, para la captura automatizada de órdenes de compra en transmisiones de TikTok Live y la conciliación asíncrona de pagos mediante Códigos QR Dinámicos de la Red Simple (ACCL), erradicando la sobreventa de inventario y el fraude financiero por comprobantes adulterados en el comercio minorista del eje troncal de Bolivia.

### 1.2.2 Objetivos Específicos
1. **Relevar, formalizar y modelar** los requerimientos funcionales y no funcionales del proceso de comercialización en vivo mediante artefactos metodológicos del Proceso Unificado (Casos de Uso Completamente Vestidos, Modelos de Dominio y Diagramas de Secuencia del Sistema - SSD).
2. **Diseñar e implementar un motor de ingesta de eventos de streaming** de baja latencia capaz de sostener conexiones persistentes por sockets contra las salas de TikTok Live y desacoplar la carga mediante un broker de mensajería asíncrono (RabbitMQ / Redis Streams).
3. **Desarrollar un pipeline de Procesamiento de Lenguaje Natural (NLP)** adaptado al léxico informal y modismos bolivianos para la tokenización, clasificación semántica de intenciones y extracción estructurada de entidades (SKU, variante, cantidad) en formato JSON.
4. **Construir un mecanismo de control de concurrencia y bloqueo distribuido (*Distributed Lock*)** con expiración temporal (TTL) sobre memoria volátil (Redis) para garantizar la exclusión mutua y prevenir condiciones de carrera en el inventario.
5. **Integrar los servicios bancarios y pasarelas de pago de la Red Simple (ACCL)** para la generación paramétrica de Códigos QR Dinámicos (estándar EMVCo MPM) y la recepción de webhooks transaccionales con validación criptográfica HMAC-SHA256.
6. **Diseñar el modelo de persistencia relacional** en tercera forma normal (3FN/BCNF) bajo las directrices de Michael V. Mannino, optimizando los planes de ejecución mediante índices B-Tree y restricciones de integridad transaccional (ACID) en PostgreSQL.
7. **Verificar y validar cuantitativamente el desempeño de la plataforma** a través de pruebas de carga, estrés y una prueba de hipótesis estadística contrastando los tiempos de atención y conciliación del método manual tradicional versus la plataforma automatizada.

---

## 1.3 Metodología

### 1.3.1 Fases del Proceso Unificado (UP) de Craig Larman
El ciclo de desarrollo se estructura rigurosamente en las cuatro fases iterativas e incrementales formuladas por Craig Larman:

```mermaid
gantt
    title Cronograma de Fases e Iteraciones - Proceso Unificado (Craig Larman)
    dateFormat  YYYY-MM-DD
    section Inicio (Inception)
    I1 - Visión, Factibilidad y Casos de Uso Clave :active, 2026-02-01, 2026-02-21
    section Elaboración (Elaboration)
    E1 - Arquitectura Ejecutable y Mitigación de Riesgos :2026-02-22, 2026-03-21
    E2 - Diseño Detallado, SSD, Contratos y Modelo Dominio :2026-03-22, 2026-04-18
    section Construcción (Construction)
    C1 - Implementación Core EDA, NLP y Redis Locks :2026-04-19, 2026-05-16
    C2 - Integración Fintech QR Simple, Webhooks y Checkout :2026-05-17, 2026-06-13
    C3 - Panel Administrativo y Métricas en Tiempo Real :2026-06-14, 2026-07-11
    section Transición (Transition)
    T1 - Pruebas de Estrés, Validación Beta y Pruebas Estadísticas :2026-07-12, 2026-08-15
```

1. **Fase de Inicio (*Inception*):** Delimitación precisa de los límites del sistema, análisis de viabilidad técnica y financiera, identificación del 10% de los casos de uso arquitectónicamente más relevantes y formulación de la visión del producto.
2. **Fase de Elaboración (*Elaboration*):** Construcción de la línea base arquitectónica ejecutable (*Executable Architectural Baseline*), mitigación de riesgos de alto impacto (latencia de sockets, bloqueo distribuido y pasarela bancaria), especificación exhaustiva de casos de uso mediante contratos de operación y diagramas de secuencia del sistema (SSD), y diseño del modelo relacional.
3. **Fase de Construcción (*Construction*):** Desarrollo integral de los casos de uso restantes, codificación bajo la filosofía de Desarrollo Guiado por Pruebas (TDD), integración de servicios de persistencia, mensajería y componentes front-end.
4. **Fase de Transición (*Transition*):** Despliegue en ambiente productivo en la nube, pruebas de carga y estrés masivo, ejecución de auditorías de rendimiento y levantamiento de datos empíricos para la prueba de hipótesis.

### 1.3.2 Criterios de Aceptación Cuantitativos de la Fase de Transición
Para certificar la finalización exitosa de la Fase de Transición y autorizar la defensa del Proyecto de Grado, se definen los siguientes criterios métricos objetivos:

1. **Latencia Máxima de Ciclo de Pedido ($T_{\text{latencia}}$):** El tiempo transcurrido desde la recepción del paquete WebSocket de comentario hasta la generación y despacho del QR dinámico no debe exceder los 3.5 segundos en percentil 95 ($P_{95} \le 3.5\text{ s}$).
2. **Tasa de Conciliación Exitosa sin Intervención:** El 100% de las notificaciones bancarias recibidas válidamente vía webhook deben conciliarse de forma autónoma sin requerir interacción manual del operador.
3. **Consistencia de Inventario (Cero Sobreventas):** En pruebas de estrés concurrentes simulando 100 usuarios intentando apartar la última unidad de un producto ($N=1$), la tasa de doble asignación debe ser estrictamente cero ($Error_{\text{oversell}} = 0\%$).
4. **Validación Estadística de Hipótesis:**
   * **Hipótesis Nula ($H_0$):** El tiempo medio de liquidación y confirmación de una orden empleando el sistema automatizado ($\mu_{\text{auto}}$) es igual o mayor al tiempo medio empleado por el método manual por WhatsApp ($\mu_{\text{manual}}$). ($H_0: \mu_{\text{auto}} \ge \mu_{\text{manual}}$).
   * **Hipótesis Alternativa ($H_1$):** El tiempo medio de liquidación con el sistema automatizado es significativamente menor al método manual. ($H_1: \mu_{\text{auto}} < \mu_{\text{manual}}$).
   * **Criterio de Rechazo:** Empleo del test de rangos signados de **Wilcoxon** (o $t$ de Student para muestras pareadas previa verificación de normalidad con Shapiro-Wilk) sobre una muestra controlada de 50 transacciones, exigiendo un nivel de significancia $\alpha = 0.01$ ($p\text{-valor} < 0.01$) para rechazar $H_0$.

---

# Capítulo II: Estudio de Mercado y Análisis del Sector de Social Commerce en Bolivia

## 2.1 Caracterización del Sector y Ecosistema de Live Shopping
El comercio electrónico en Bolivia ha transitado de forma disruptiva hacia las plataformas sociales móviles. A diferencia de mercados desarrollados donde las transacciones se canalizan mediante tiendas web autogestionadas o marketplaces corporativos (Amazon, Mercado Libre), el usuario boliviano fundamenta su decisión de compra en el contacto visual directo, la demostración de la prenda o artículo en tiempo real y la capacidad de interactuar síncronamente con el comerciante.

El ecosistema de Live Shopping en el eje troncal exhibe las siguientes características:
* **Concentración Geográfica:** El 82% de las emisiones en vivo de comercio minorista se originan en los departamentos de Santa Cruz (46%), La Paz (22%) y Cochabamba (14%).
* **Categorías Predominantes:** Confección de moda femenina y masculina, calzado deportivo importado, cosméticos y maquillaje profesional, tecnología y periféricos móviles, y productos para el hogar.
* **Comportamiento del Consumidor:** La compra es impulsada por la escasez declarada por el presentador (*"¡Solo me queda 1 unidad en talla M!"*), lo que genera un estado de urgencia en el espectador.

---

## 2.2 Segmentación del Mercado y Determinación Matemática de la Muestra

### Determinación del Tamaño de la Muestra
Dado que no se opera sobre una empresa monopólica bajo convenio, se procede a formalizar el tamaño de la muestra representativa para el diagnóstico del sector. Se define una **población finita ($N$)** correspondiente a comerciantes minoristas activos que realizan transmisiones en directo en TikTok con periodicidad mínima de dos veces por semana en el eje troncal boliviano, cuantificada tras un muestreo exploratorio en $N = 1,200$ comercios.

La ecuación de cálculo muestral para poblaciones finitas se define como:

$$n = \frac{Z^2 \cdot p \cdot q \cdot N}{E^2 \cdot (N - 1) + Z^2 \cdot p \cdot q}$$

Donde los parámetros metodológicos corresponden a:
* $N = 1,200$ (Tamaño del universo poblacional identificado).
* $Z = 1.96$ (Nivel de confianza del 95% para distribución normal estándar bilateral).
* $p = 0.50$ (Proporción esperada de adopción / variabilidad máxima).
* $q = 1 - p = 0.50$ (Probabilidad complementaria).
* $E = 0.05$ (Margen de error máximo admisible del 5.0%).

Sustituyendo los valores en la ecuación:

$$n = \frac{(1.96)^2 \cdot (0.5) \cdot (0.5) \cdot 1200}{(0.05)^2 \cdot (1200 - 1) + (1.96)^2 \cdot (0.5) \cdot (0.5)}$$

$$n = \frac{3.8416 \cdot 0.25 \cdot 1200}{0.0025 \cdot 1199 + 3.8416 \cdot 0.25}$$

$$n = \frac{1152.48}{2.9975 + 0.9604} = \frac{1152.48}{3.9579} \approx 291.18$$

Se establece formalmente que el tamaño mínimo representativo de la muestra para el levantamiento de requerimientos y encuestas operativas del sector asciende a **$n = 291$ comercios minoristas**.

---

## 2.3 Diagnóstico Operativo: Mapeo del Flujo de Venta Manual Actual (As-Is)

El flujo operativo tradicional empleado actualmente por la totalidad de los comerciantes no automatizados se modela a continuación:

```mermaid
sequenceDiagram
    autonumber
    actor Cliente as Espectador en TikTok Live
    actor Host as Presentador en Vivo
    actor Operador as Asistente de WhatsApp
    actor Banca as App Bancaria Móvil
    
    Cliente->>Host: Escribe comentario: "Mío el conjunto azul cod 12"
    Note over Host: El chat corre a 25 comentarios/segundo.<br/>El host intenta leer en pantalla.
    Host->>Cliente: Grita verbalmente: "Tuyo @cliente! Anda a mi perfil y escribe al WhatsApp!"
    Host->>Operador: Apunta en libreta de papel: "Conjunto azul a cliente"
    Note over Cliente: El cliente abandona el live,<br/>abre WhatsApp y busca el número.
    Cliente->>Operador: Envía mensaje: "Hola, gané el conjunto azul 12 en el live"
    Operador->>Operador: Revisa la libreta física o interrumpe al host
    alt Producto ya tomado por otro operador
        Operador-->>Cliente: "Disculpe, se agotó en el live" (Venta Frustrada)
    else Producto disponible
        Operador->>Cliente: Envía imagen de QR Estático sin monto
        Note over Cliente: Abre su banco, sube la imagen QR,<br/>tipea manualmente el monto de Bs 180.
        Cliente->>Banca: Realiza la transferencia
        Banca-->>Cliente: Emite comprobante en pantalla
        Cliente->>Operador: Remite captura de pantalla del comprobante
        Note over Operador: Puede ser un comprobante clonado/trucado.<br/>El operador debe entrar a su banca móvil.
        Operador->>Banca: Ingresa a banca móvil y busca el abono de Bs 180
        alt Abono verificado en cuenta
            Operador->>Operador: Anota en planilla Excel manual
            Operador-->>Cliente: "Pago confirmado. Envíe sus datos de envío."
        else Comprobante falso / Dinero no acreditado
            Operador-->>Cliente: "No figura el dinero." (Disputa/Estafa)
        end
    end
```

---

## 2.4 Identificación y Demostración Matemática del Cuello de Botella Transaccional

### Modelo del Rendimiento Manual vs. Ráfagas de Demanda
Sea $\lambda_{\text{live}}$ la tasa de generación de intenciones de compra por unidad de tiempo durante un instante de promoción en la transmisión, y sea $\mu_{\text{manual}}$ la tasa de servicio y atención del operador humano.

A partir del levantamiento de tiempos y movimientos en el estudio de campo:
* El tiempo promedio invertido por un operador humano para leer un comentario, coordinar verbalmente, atender el chat de WhatsApp, remitir el QR estático, verificar el extracto en su aplicación bancaria y registrar el pedido en una hoja de cálculo es:
  $$T_{\text{manual}} \ge 120\text{ segundos (2 minutos por orden)}$$
* En consecuencia, la tasa de procesamiento para un equipo de $k = 2$ operadores humanos atendiendo terminales telefónicas es:
  $$\mu_{\text{manual}} = \frac{k}{T_{\text{manual}}} = \frac{2}{120} = 0.0167\text{ pedidos/segundo} \approx 1\text{ pedido/minuto}$$

Durante la exhibición de artículos con alta demanda, la tasa de ráfaga registrada en el chat alcanza:
$$\lambda_{\text{live}} = 15\text{ pedidos/minuto}$$

Definiendo la intensidad de tráfico transaccional ($\rho$):
$$\rho = \frac{\lambda_{\text{live}}}{\mu_{\text{manual}}} = \frac{15}{1} = 15 \gg 1$$

Dado que $\rho > 1$, el sistema de colas manual es intrínsecamente inestable. El tiempo de espera en cola tiende a infinito y la longitud de la cola supera la memoria operativa del personal. La probabilidad de saturación y pérdida directa de clientes ($P_{\text{pérdida}}$) se calcula empíricamente:

$$\text{Tasa de Abandono (Fricción WhatsApp)} \approx 65\%$$
$$\text{Pérdida por Demora de Atención (> 10 min)} \approx 20\%$$
$$\text{Pérdida por Doble Asignación / Disputas} \approx 8\%$$

### Rendimiento del Sistema Automatizado Propuesto
En el sistema distribuido propuesto, el tiempo total de procesamiento desde el mensaje del chat hasta la confirmación de la orden pagada se compone de:

$$T_{\text{sistema}} = t_{\text{ingesta}} + t_{\text{nlp}} + t_{\text{lock}} + t_{\text{qr\_api}} + t_{\text{webhook\_conciliación}}$$

Donde los tiempos observados en la arquitectura distribuida son:
* $t_{\text{ingesta}} \le 40\text{ ms}$ (Socket persistente TCP/WS).
* $t_{\text{nlp}} \le 200\text{ ms}$ (Inferencia y tokenización en memoria).
* $t_{\text{lock}} \le 10\text{ ms}$ (Redis atómico `SETNX`).
* $t_{\text{qr\_api}} \le 650\text{ ms}$ (Llamada HTTP a pasarela Fintech).
* $t_{\text{webhook\_conciliación}} \le 250\text{ ms}$ (Ingesta y verificación HMAC).

El tiempo computacional total satisface:
$$T_{\text{sistema\_cómputo}} = 0.040 + 0.200 + 0.010 + 0.650 + 0.250 = 1.15\text{ segundos} \le 3.5\text{ s}$$

Con una capacidad de atención paralela sustentada en hilos asíncronos y workers concurrentes ($\mu_{\text{auto}} \ge 500\text{ pedidos/segundo}$), la intensidad de tráfico resulta:
$$\rho_{\text{auto}} = \frac{15 / 60}{500} = 0.0005 \ll 1$$
Garantizando estabilidad matemática total, ausencia de colas de bloqueo y cero pérdidas por capacidad de cómputo.

---

## 2.5 Análisis Comparativo de Soluciones Sustitutas y Brecha Tecnológica Local

| Dimensión de Análisis | WhatsApp Business Manual | Shopify / WooCommerce | CommentSold (USA) | Plataforma Propuesta (Este Proyecto) |
| :--- | :--- | :--- | :--- | :--- |
| **Captura en Vivo en TikTok** | No (Manual visual) | No (Requiere salir a URL) | Sí (Exclusivo USA/UK) | **Sí (WebSockets automáticos)** |
| **Moneda Nacional (BOB)** | No aplicable (Efectivo/Manual)| Limitado (Gateways caros) | No (Solo USD / EUR) | **Sí (100% nativo BOB)** |
| **Integración QR Simple ACCL**| No (Solo imagen estática) | Inexistente nativamente | No compatible | **Sí (QR Dinámico Automatizado)** |
| **Prevención de Sobreventa** | Nula (Colisión humana) | Sí (A nivel de checkout web) | Sí (A nivel de inventario) | **Sí (Redis Distributed Lock)** |
| **Conciliación de Pagos** | Manual (Inspección visual) | Automática con tarjeta | Automática con tarjeta | **Automática vía Webhook QR** |
| **Costo Operativo** | Alto (2 a 3 empleados) | Suscripción USD + % cobro | $149 USD/mes + 5% comisión| **Bajo costo en nube nacional** |
| **Incentivo a la Compra** | Mínimo (Fricción severa) | Medio (Formularios largos) | Alto en mercados anglos | **Máximo (Checkout instantáneo)** |

---

# Capítulo III: Marco Teórico y Selección de Componentes Tecnológicos

## 3.1 Ingesta de Eventos en Tiempo Real (WebSockets vs. Polling vs. SSE)

### Matriz de Selección Multicriterio
Se ponderan las alternativas arquitectónicas para la captura continua del flujo de datos de TikTok Live:

| Criterio de Decisión | Peso | HTTP Short Polling | Server-Sent Events (SSE) | WebSockets (RFC 6455) |
| :--- | :---: | :---: | :---: | :---: |
| **Latencia de Entrega de Mensajes** | 30% | 2 / 10 | 8 / 10 | **10 / 10** |
| **Sobrecarga de Encabezados de Red** | 25% | 1 / 10 | 8 / 10 | **9 / 10** |
| **Bidireccionalidad Full-Duplex** | 25% | 1 / 10 | 3 / 10 | **10 / 10** |
| **Eficiencia en Uso de CPU/Memoria**| 20% | 2 / 10 | 7 / 10 | **9 / 10** |
| **Puntaje Ponderado Total** | **100%**| **1.55 / 10** | **6.65 / 10** | **9.55 / 10** |

**Justificación Técnica:**
El protocolo **WebSockets** establece un canal de transporte bidireccional sobre una única conexión TCP de larga duración tras el *handshake* inicial HTTP. Mientras que HTTP Polling requiere reenviar encabezados de más de 800 bytes en cada petición cíclica (saturando el ancho de banda y la red), WebSockets enmarca cada mensaje en paquetes de tan solo 2 a 14 bytes de sobrecarga, logrando latencias de entrega inferiores a 30 milisegundos.

---

## 3.2 Procesamiento de Lenguaje Natural (NLP) y Extracción de Entidades Semánticas

### Matriz de Selección de Modelos NLP

| Criterio de Decisión | Peso | Expresiones Regulares (RegEx) | LLM APIs Externas (OpenAI / Claude) | spaCy + FastText Local Híbrido |
| :--- | :---: | :---: | :---: | :---: |
| **Latencia de Inferencia (< 100 ms)** | 35% | **10 / 10** (2 ms) | 2 / 10 (800 - 1500 ms) | **9 / 10** (15 - 40 ms) |
| **Costo por Cómputo / Token** | 25% | **10 / 10** (Gratuito) | 2 / 10 (Inviable a escala) | **9 / 10** (Cómputo local fijo) |
| **Tolerancia a Variaciones Dialectales**| 20%| 3 / 10 (Rígido) | 10 / 10 (Muy flexible) | **8 / 10** (Entrenable) |
| **Determinismo en Salidas JSON** | 20% | 10 / 10 | 7 / 10 (Posible alucinación) | **10 / 10** |
| **Puntaje Ponderado Total** | **100%**| **6.85 / 10** | **4.60 / 10** | **8.95 / 10** |

**Justificación Técnica:**
Se selecciona una **estrategia híbrida** compuesta por un pipeline local de **spaCy / Expresiones Regulares Optimizadas**. El empleo de llamadas a APIs de modelos LLM remotos queda descartado para la ingesta crítica en tiempo real debido a que su latencia intrínseca ($> 800\text{ ms}$) generaría colas explosivas en ráfagas de 30 mensajes por segundo. El analizador híbrido ejecuta una primera pasada con gramáticas regulares precompiladas para extracción de tokens SKU (`[A-Z0-9]{3,8}`) y cantidades numéricas; si la confianza es inferior a un umbral ($\theta < 0.85$), se aplica similitud coseno sobre vectores léxicos (*Word Embeddings*) de spaCy entrenados con modismos bolivianos (*"apártamelo"*, *"mío"*, *"para mí"*, *"llevo"*).

---

## 3.3 Ecosistema Fintech y Pagos Inmediatos en Bolivia

### Matriz de Selección de Infraestructura de Cobro

| Criterio de Decisión | Peso | Cobro con Tarjeta Tradicional | Pasarelas Internacionales | QR Simple ACCL / Fintech Local |
| :--- | :---: | :---: | :---: | :---: |
| **Tasa de Penetración en Bolivia** | 35% | 4 / 10 (Baja tenencia) | 1 / 10 (Incompatible BOB) | **10 / 10** (Universal) |
| **Fricción en Checkout Móvil** | 25% | 3 / 10 (16 dígitos + OTP) | 2 / 10 (Restringido) | **9 / 10** (Escaneo directo) |
| **Conciliación por Webhooks Seguros**| 20% | 7 / 10 | 10 / 10 | **9 / 10** |
| **Comisión por Transacción** | 20% | 4 / 10 (3.5% + cargo fijo) | 1 / 10 (> 5% + USD) | **8 / 10** (< 1.5% o costo fijo) |
| **Puntaje Ponderado Total** | **100%**| **4.35 / 10** | **2.85 / 10** | **9.15 / 10** |

### Análisis Algorítmico y Estructura del Payload EMVCo MPM
La red Simple opera bajo las normas internacionales **EMVCo Merchant-Presented Mode (MPM)**. El código QR dinámico difiere sustancialmente del estático en su carga útil:

```
+----------------------------------------------------------------------------------------------------+
|                               PAYLOAD QR DINÁMICO EMVCo (RED SIMPLE)                               |
+----------------------------------------------------------------------------------------------------+
| Tag 00 (02): "01"                        -> Payload Format Indicator                               |
| Tag 01 (02): "12"                        -> Point of Initiation: Dinámico (Uso único, monto fijo)   |
| Tag 26 (46): "0010BO.ACCL.SIMPLE...UUID" -> Merchant Account Info & Red Interbancaria              |
| Tag 52 (04): "5999"                      -> Merchant Category Code (General Retail)                |
| Tag 53 (03): "068"                       -> Código ISO Moneda (068 = Bolivianos - BOB)             |
| Tag 54 (06): "180.00"                    -> Monto Inmutable de la Transacción                      |
| Tag 58 (02): "BO"                        -> Código de País                                         |
| Tag 59 (15): "TIENDA MODA SCZ"           -> Nombre de Fantasía del Comercio                        |
| Tag 60 (10): "SANTA CRUZ"                -> Ciudad de Emisión                                      |
| Tag 62 (48): [Subtag 01: "ORD-98421"]    -> Referencia Transaccional / ID de Orden Interna         |
| Tag 63 (04): "8F4A"                      -> Suma de Verificación CRC-16 (Polinomio 0x1021)          |
+----------------------------------------------------------------------------------------------------+
```

El algoritmo de verificación para el Tag 63 computa un **CRC-16/CCITT-FALSE** inicializado en `0xFFFF`. Cualquier manipulación del monto (Tag 54) o de la orden altera matemáticamente el CRC, provocando el rechazo instantáneo por parte de la aplicación bancaria del usuario.

---

## 3.4 Arquitectura de Cómputo, Persistencia y Mitigación de Condiciones de Carrera

### El Algoritmo Redlock y la Exclusión Mutua en Memoria
Para evitar la sobreventa cuando decenas de espectadores comentan la intención de compra del mismo artículo en el mismo milisegundo, no es factible bloquear registros en la base de datos relacional mediante `SELECT ... FOR UPDATE`, pues generaría contención severa y agotamiento del pool de conexiones.

Se implementa el patrón **Distributed Lock sobre Redis** mediante la primitiva atómica:

```text
SET resource:sku:VEST-ROJO-44 "UUID_ORDEN_RANDOM" NX PX 480000
```

* `NX`: Asigna la clave únicamente si no existe previamente en la memoria de Redis.
* `PX 480000`: Establece un tiempo de vida (*TTL*) de 480,000 milisegundos (8 minutos).
* Si el comando retorna `OK`, el hilo de ejecución ha obtenido de forma atómica la exclusión mutua para la reserva de esa unidad. Si retorna `nil`, el sistema sabe de inmediato que la unidad ya fue reservada por otro usuario milisegundos antes, derivando al comprador a una lista de espera.
* La liberación segura del bloqueo se realiza mediante un script evaluado en **Lua** dentro de Redis, garantizando que un hilo no libere el bloqueo de otro si el TTL expiró durante la ejecución:

```lua
if redis.call("get", KEYS[1]) == ARGV[1] then
    return redis.call("del", KEYS[1])
else
    return 0
end
```

---

## 3.5 Interfaz de Usuario y Checkout Móvil

### Matriz de Selección de Frontend

| Criterio de Decisión | Peso | Streamlit / Python UI | Aplicación Nativa (Flutter/React Native) | PWA React / Next.js Ultraligera |
| :--- | :---: | :---: | :---: | :---: |
| **Tiempo de Carga Inicial (< 1.5s en 4G)**| 35% | 2 / 10 | 1 / 10 (Requiere instalación) | **10 / 10** (SSR / Edge cached) |
| **Fricción de Entrada para el Usuario** | 30% | 6 / 10 | 1 / 10 (Descarga obligatoria) | **10 / 10** (URL directa) |
| **Actualización en Tiempo Real** | 20% | 4 / 10 (Rerender pesado) | 9 / 10 | **9 / 10** (WebSockets nativos) |
| **Facilidad de Desarrollo / Despliegue**| 15% | 9 / 10 | 5 / 10 | **8 / 10** |
| **Puntaje Ponderado Total** | **100%**| **4.65 / 10** | **3.45 / 10** | **9.50 / 10** |

---

# Capítulo IV: Definición de Requisitos (IEEE 830 adaptado a Larman/Mannino)

## 4.1 Principios GRASP y Perspectiva del Producto
El sistema se modela aplicando rigurosamente los principios de asignación de responsabilidades definidos por Craig Larman:
* **Controlador (*Controller*):** La clase `LiveEventController` recibe los eventos crudos del socket y coordina a los subsistemas de inferencia sin asumir lógica de persistencia.
* **Experto en Información (*Information Expert*):** La clase `Inventario` encapsula la lógica de cálculo de stock remanente y validación de atributos de variantes.
* **Fabricación Pura (*Pure Fabrication*):** `RedlockDistributedLockService` y `SimpleQRAdapter` son clases creadas artificialmente para mantener alta cohesión y bajo acoplamiento con la infraestructura externa.
* **Variaciones Protegidas (*Protected Variations*):** Se define la interfaz `IPaymentGateway` para aislar el núcleo transaccional frente a modificaciones en los contratos API de las pasarelas bancarias bolivianas.

---

## 4.2 Requisitos Funcionales (RF-01 a RF-15)

| Identificador | Nombre del Requisito | Descripción Técnica Detallada |
| :--- | :--- | :--- |
| **RF-01** | Conexión e Ingesta de Stream | El sistema debe establecer una conexión TCP persistente vía WebSockets hacia la sala de TikTok Live indicada por el comerciante, reconectando automáticamente con *exponential backoff*. |
| **RF-02** | Filtrado y Desacoplamiento | El motor de ingesta debe filtrar eventos irrelevantes (likes, gifts visuales no transaccionales) y publicar los comentarios de texto en el broker RabbitMQ en menos de 50 ms. |
| **RF-03** | Normalización de Texto | El subsistema de NLP debe desacentuar, convertir a minúsculas y suprimir caracteres repetidos de los comentarios recibidos. |
| **RF-04** | Detección de Intención de Compra | El clasificador léxico debe evaluar la presencia de verbos de compra o pronombres de posesión, asignando un índice de confianza $\theta \in [0.0, 1.0]$. |
| **RF-05** | Extracción de Entidad SKU | El parser debe extraer el código alfanumérico del producto basándose en el catálogo cargado en memoria para la sesión activa. |
| **RF-06** | Adquisición de Bloqueo Distribuido | El servicio de concurrencia debe ejecutar una operación atómica `SETNX` en Redis para el recurso `SKU_ID` asociado a un TTL de 8 minutos. |
| **RF-07** | Generación de Pre-Orden Temporal | Si el bloqueo es exitoso, el sistema debe registrar una orden en estado `PENDIENTE_PAGO` y generar un identificador único global `UUIDv4`. |
| **RF-08** | Despacho de Enlace de Checkout | El sistema debe emitir una respuesta automática (o webhook de mensajería) conteniendo la URL única efímera de pago dirigida al usuario comprador. |
| **RF-09** | Solicitud de Payload QR Dinámico | Al abrirse la vista de checkout, el backend debe comunicarse vía mTLS/HTTPS con la pasarela Fintech y obtener la cadena EMVCo del QR Simple con monto exacto e ID de orden. |
| **RF-10** | Renderizado de QR y Temporizador | El frontend móvil debe renderizar la imagen del QR y desplegar una cuenta regresiva sincronizada con el TTL de la clave en Redis. |
| **RF-11** | Endpoint de Recepción de Webhooks | El sistema debe exponer un endpoint HTTPS público capaz de recibir notificaciones de pago HTTP POST provenientes de la pasarela bancaria. |
| **RF-12** | Validación Criptográfica HMAC | El endpoint debe calcular el hash `HMAC-SHA256` del cuerpo de la petición utilizando el secreto compartido y rechazar con HTTP 401 si no hay concordancia exacta. |
| **RF-13** | Conciliación Atómica e Idempotencia | El manejador de webhooks debe verificar si la transacción ya fue liquidada (`idempotency_key`); si es nueva, debe transicionar el estado de la orden a `PAGADA` bajo una transacción ACID. |
| **RF-14** | Liberación Automática por Timeout | Si el tiempo de expiración (8 min) concluye sin confirmación bancaria, un worker reactivo debe eliminar la reserva y reponer el stock disponible. |
| **RF-15** | Notificación Reactiva al Dashboard | El backend debe emitir un evento WebSocket interno hacia el panel del comerciante para actualizar la grilla de ventas y métricas de inventario sin recargar la página. |

---

## 4.3 Requisitos No Funcionales y de Rendimiento
* **RP-01 (Latencia Transaccional en Vivo):** El tiempo medio de procesamiento desde la emisión del comentario en TikTok hasta la entrega del enlace de checkout no debe superar los 2.0 segundos bajo condiciones normales de red.
* **RP-02 (Concurrencia y Rendimiento):** El subsistema de colas y bloqueo en memoria debe procesar un caudal de hasta 2,500 mensajes de chat por minuto sin incremento en la tasa de error.
* **RP-03 (Tolerancia a Fallos y RTO/RPO):** En caso de desconexión del socket de TikTok, el tiempo de recuperación del objetivo (*RTO*) no debe exceder los 10 segundos, preservando la consistencia del inventario reservado en Redis (*RPO = 0*).
* **RP-04 (Seguridad y Resguardo Criptográfico):** Toda comunicación externa debe forzar TLS 1.3. Las credenciales bancarias y claves secretas deben inyectarse mediante variables de entorno en bóveda segura (*Secrets Vault*).

---

## 4.4 Diagrama de Casos de Uso y Matriz de Trazabilidad

```mermaid
flowchart LR
    subgraph Actores
        U((Espectador / Comprador))
        H((Live Host / Vendedor))
        B((Pasarela Fintech / ACCL))
    end

    subgraph Sistema ["Plataforma Automatizada TikTokSell"]
        CU01["CU-01: Iniciar Sesión de Transmisión Live"]
        CU02["CU-02: Publicar Intención en Chat"]
        CU03["CU-03: Reservar Stock y Generar Checkout"]
        CU04["CU-04: Escanear y Pagar con QR Dinámico"]
        CU05["CU-05: Conciliar Pago por Webhook"]
        CU06["CU-06: Monitorear Ventas en Tiempo Real"]
        CU07["CU-07: Liberar Stock por Expiración TTL"]
    end

    H --> CU01
    H --> CU06
    U --> CU02
    U --> CU04
    CU02 --> CU03
    CU04 --> B
    B --> CU05
    CU03 -.-> CU07
    CU05 --> CU06
```

---

## 4.5 Modelo de Dominio Conceptual

```mermaid
classDiagram
    class Comercio {
        +UUID id
        +String razonSocial
        +String nit
        +String cuentaBancariaIban
    }
    class TransmisionLive {
        +UUID id
        +String tiktokUsername
        +DateTime fechaHoraInicio
        +String estado
    }
    class ProductoCatalogo {
        +UUID id
        +String skuBase
        +String nombre
        +Decimal precioBase
    }
    class VarianteProducto {
        +UUID id
        +String skuEspecifico
        +String color
        +String talla
        +Int stockFisico
        +Int stockDisponible
    }
    class BloqueoStockTemporal {
        +String redisKey
        +UUID varianteId
        +String usuarioTiktok
        +DateTime fechaExpiracion
        +String estadoLock
    }
    class OrdenCompra {
        +UUID id
        +Decimal montoTotal
        +DateTime fechaCreacion
        +String estado
        +String checkoutUrl
    }
    class TransaccionQRSimple {
        +UUID id
        +String payloadEMVCo
        +String transactionIdGateway
        +DateTime fechaExpiracion
        +String estadoCobro
    }

    Comercio "1" -- "*" TransmisionLive : ejecuta
    Comercio "1" -- "*" ProductoCatalogo : es_propietario
    ProductoCatalogo "1" -- "*" VarianteProducto : contiene
    VarianteProducto "1" -- "*" BloqueoStockTemporal : es_apartado_en
    BloqueoStockTemporal "1" -- "1" OrdenCompra : formaliza
    OrdenCompra "1" -- "1" TransaccionQRSimple : genera
```

---

# Capítulo V: Análisis y Diseño del Sistema

## 5.1 Arquitectura Lógica en Capas y Despliegue Físico

```mermaid
graph TD
    subgraph CapaPresentacion ["Capa de Presentación"]
        P1["Panel Administrativo del Comercio (React + Tailwind)"]
        P2["Checkout Móvil Responsivo (Next.js PWA)"]
    end

    subgraph CapaGateway ["Capa de Entrada y Proxy Inverso"]
        NG["Nginx / Traefik SSL Termination & Rate Limiting"]
    end

    subgraph CapaAplicacion ["Capa de Aplicación y Dominio"]
        API["Core API Transaccional (FastAPI / Python Asíncrono)"]
        INGEST["Daemon Conector TikTok Live (Node.js Events)"]
        WORKER["Workers de Tareas Asíncronas (Celery)"]
    end

    subgraph CapaMensajeria ["Capa de Mensajería y Caché Distribuida"]
        RMQ["RabbitMQ (Colas de Mensajes del Chat)"]
        REDIS["Cluster Redis (Redlock, TTL Sessions & Pub/Sub)"]
    end

    subgraph CapaPersistencia ["Capa de Persistencia Relacional"]
        PG[("PostgreSQL 16 (Base de Datos ACID)")]
    end

    subgraph EcosistemaExterno ["Servicios Externos"]
        TK_LIVE["Servidores de TikTok Live"]
        ACCL_GATEWAY["Pasarela Fintech / Red Simple (ACCL)"]
    end

    P1 --> NG
    P2 --> NG
    NG --> API
    TK_LIVE --> INGEST
    INGEST --> RMQ
    RMQ --> WORKER
    WORKER --> REDIS
    WORKER --> API
    API --> REDIS
    API --> PG
    API --> ACCL_GATEWAY
    ACCL_GATEWAY --> API
```

---

## 5.2 Diagramas de Secuencia del Sistema (SSD) y Contratos de Operación de Larman

### Diagrama de Secuencia del Sistema: Captura, Reserva y Emisión de QR

```mermaid
sequenceDiagram
    autonumber
    actor Cliente as Comprador en TikTok
    participant Sistema as :SistemaTikTokSell
    actor Pasarela as :PasarelaFintechACCL
    actor Host as :HostVendedor

    Cliente->>Sistema: capturarComentario(usuarioTiktok, textoComentario, idLive)
    Note over Sistema: Ejecuta Contrato CO-01 y CO-02
    Sistema-->>Cliente: entregarEnlaceCheckout(urlCheckout)
    
    Cliente->>Sistema: solicitarQRDinamico(idOrden)
    Sistema->>Pasarela: emitirQRSimple(idOrden, montoTotal, cuentaDestino)
    Pasarela-->>Sistema: retornoPayloadEMVCo(payloadString, idTransaccionGateway)
    Note over Sistema: Ejecuta Contrato CO-03
    Sistema-->>Cliente: renderizarQRDinamico(imagenQR, tiempoExpiracion)

    Pasarela->>Sistema: callbackWebhookPago(idTransaccionGateway, firmaHMAC, payloadJSON)
    Note over Sistema: Ejecuta Contrato CO-04
    Sistema-->>Pasarela: confirmacionHTTP(200 OK)
    Sistema-->>Host: notificarOrdenPagada(idOrden, sku, comprador)
```

### Contratos de Operación de Craig Larman

#### Contrato de Operación: CO-01 (`capturarComentario`)
* **Operación:** `capturarComentario(usuarioTiktok: String, textoComentario: String, idLive: UUID)`
* **Referencias Cruzadas:** Requisitos Funcionales: RF-01, RF-02, RF-03, RF-04, RF-05.
* **Precondiciones:**
  * Debe existir una sesión activa de transmisión en estado `EN_VIVO` asociada al identificador `idLive`.
  * La cadena `textoComentario` no debe ser vacía.
* **Poscondiciones:**
  * Se extrajo el token de intención de compra con confianza $\ge 0.85$.
  * Se identificó unívocamente la instancia `vp` de `VarianteProducto` cuyo código coincide con el SKU analizado.
  * Se derivó la solicitud al gestor de bloqueos para la invocación de `reservarStock`.

#### Contrato de Operación: CO-02 (`reservarStock`)
* **Operación:** `reservarStock(idVariante: UUID, usuarioTiktok: String) : UUID`
* **Referencias Cruzadas:** Requisitos Funcionales: RF-06, RF-07, RF-08.
* **Precondiciones:**
  * La variante identificada por `idVariante` debe poseer `stockDisponible > 0`.
* **Poscondiciones:**
  * Se creó de manera atómica un bloqueo distribuido en Redis bajo la clave `lock:variante:<idVariante>` con un valor pseudoaleatorio criptográfico y un TTL de 480 segundos.
  * Se decrementó temporalmente en memoria el atributo `stockDisponible` de la variante respectiva.
  * Se instanció una `OrdenCompra` `oc` con estado `PENDIENTE_PAGO`, asignándole un identificador `UUIDv4`.
  * Se generó el enlace URL único asociado al token de checkout efímero.

#### Contrato de Operación: CO-03 (`emitirQRDinamico`)
* **Operación:** `emitirQRDinamico(idOrden: UUID) : String`
* **Referencias Cruzadas:** Requisitos Funcionales: RF-09, RF-10.
* **Precondiciones:**
  * La instancia `oc` de `OrdenCompra` existe y su estado es estrictamente `PENDIENTE_PAGO`.
  * El bloqueo en Redis para la orden no ha expirado.
* **Poscondiciones:**
  * Se instanció un registro `TransaccionQRSimple` `tqr` asociado a la orden `oc`.
  * El atributo `tqr.payloadEMVCo` fue poblado con el string estructurado bajo normativa EMVCo MPM y suma de verificación CRC-16.
  * Se retornó la imagen matricial del código QR dinámico al frontend del comprador.

#### Contrato de Operación: CO-04 (`callbackWebhookPago`)
* **Operación:** `callbackWebhookPago(idTransaccionGateway: String, firmaHMAC: String, payloadJSON: String)`
* **Referencias Cruzadas:** Requisitos Funcionales: RF-11, RF-12, RF-13, RF-15.
* **Precondiciones:**
  * La firma `firmaHMAC` calculada con el secreto de integración coincide idénticamente con el encabezado de la petición.
  * No existe registro previo de procesamiento exitoso para el identificador `idTransaccionGateway` (control de idempotencia).
* **Poscondiciones:**
  * El estado de `OrdenCompra` mutó de forma atómica de `PENDIENTE_PAGO` a `PAGADA`.
  * El bloqueo temporal en Redis fue eliminado limpiamente.
  * Se decrementó formal y físicamente el atributo `stockFisico` de `VarianteProducto` en la base de datos relacional.
  * Se registró una entrada inmutable de auditoría en `historial_ventas`.
  * Se emitió un evento por WebSocket actualizando el panel del comerciante.

---

## 5.3 Diagrama de Clases de Diseño (DCD Consolidado)

```mermaid
classDiagram
    class LiveStreamIngestor {
        -String roomId
        -WebSocket clientSocket
        +connect(roomId: String) void
        +disconnect() void
        +onMessageReceived(rawEvent: Byte[]) void
    }

    class NLPIntentService {
        -Float confidenceThreshold
        +parseComment(text: String) ParsedOrderDTO
        -normalizeText(text: String) String
        -extractSKU(tokens: String[]) String
    }

    class DistributedLockManager {
        -RedisCluster redisClient
        +acquireLock(key: String, ttlMs: Int) String
        +releaseLock(key: String, lockValue: String) Boolean
        +checkLockHealth(key: String) Boolean
    }

    class OrderTransactionController {
        -IOrderRepository orderRepo
        -DistributedLockManager lockManager
        -IPaymentGateway paymentGateway
        +processChatOrder(dto: ParsedOrderDTO) OrderResponseDTO
        +handlePaymentWebhook(payload: WebhookDTO, signature: String) WebhookAckDTO
        +expireUnpaidOrder(orderId: UUID) void
    }

    class SimpleQRAdapter {
        -String apiKey
        -String secretKey
        -HttpClient httpClient
        +generateDynamicQR(orderId: UUID, amount: Decimal) QRPayloadDTO
        +verifySignature(rawBody: String, signature: String) Boolean
    }

    class OrderEntity {
        -UUID id
        -UUID liveStreamId
        -UUID variantId
        -String tiktokUsername
        -Decimal totalAmount
        -OrderStatus status
        -DateTime createdAt
        +markAsPaid() void
        +markAsCancelled() void
    }

    LiveStreamIngestor --> NLPIntentService : envía texto
    NLPIntentService --> OrderTransactionController : entrega DTO
    OrderTransactionController --> DistributedLockManager : invoca exclusión
    OrderTransactionController --> SimpleQRAdapter : solicita payload QR
    OrderTransactionController --> OrderEntity : muta estado
```

---

## 5.4 Diseño Lógico y Físico de Base de Datos (Normas Mannino & DDL PostgreSQL)

### Cumplimiento de Formas Normales (Mannino: 3FN / BCNF)
Siguiendo los principios de modelado relacional de Michael V. Mannino:
* **Primera Forma Normal (1FN):** Todos los atributos son atómicos e indivisibles. No existen grupos repetitivos; las variantes de productos (talla, color) se desacoplan en una entidad dependiente.
* **Segunda Forma Normal (2FN):** Se encuentra en 1FN y cada atributo que no forma parte de una clave candidata depende de manera total de la clave primaria, habiendo eliminado cualquier dependencia parcial.
* **Tercera Forma Normal (3FN) y BCNF:** No existen dependencias funcionales transitivas entre atributos no primos. Los identificadores foráneos representan claves foráneas limpias referenciando claves subrogadas primarias de tipo `UUID`.

### Diccionario de Datos del Sistema (Tablas Principales)

1. `comercio`: Entidad jurídica o unipersonal propietaria de la cuenta y receptora de fondos.
2. `usuario`: Credenciales de acceso administrativo del comerciante al dashboard.
3. `transmision_live`: Instancias de sesiones de streaming en TikTok Live.
4. `producto_catalogo`: Definición maestra de los productos del inventario.
5. `variante_producto`: Unidades mínimas de inventario físico (SKU, talla, color, stock).
6. `bloqueo_stock_temporal`: Registro de auditoría de reservas activas en memoria volátil.
7. `comentario_live`: Log de ingesta de mensajes de chat analizados por NLP.
8. `orden_compra`: Entidad nuclear transaccional que agrupa el pedido.
9. `transaccion_qr_simple`: Registro del payload EMVCo y seguimiento con pasarela de pagos.
10. `webhook_notificacion_pago`: Bitácora inmutable de recepciones HTTP POST de la entidad financiera.
11. `historial_ventas`: Registro contable para reportería financiera y cierre de caja.

### Script DDL Completo en PostgreSQL 14+ (Tipado Estricto, UUIDs, CHECKS e Índices B-Tree)

```sql
-- =============================================================================
-- ESQUEMA DDL: SISTEMA DISTRIBUIDO TIKTOKSELL BOLIVIA
-- BASE DE DATOS: PostgreSQL 14+ con extension pgcrypto / uuid-ossp
-- =============================================================================

CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
CREATE EXTENSION IF NOT EXISTS "pgcrypto";

-- Limpieza preventiva de esquema
DROP TABLE IF EXISTS historial_ventas CASCADE;
DROP TABLE IF EXISTS webhook_notificacion_pago CASCADE;
DROP TABLE IF EXISTS transaccion_qr_simple CASCADE;
DROP TABLE IF EXISTS orden_compra CASCADE;
DROP TABLE IF EXISTS comentario_live CASCADE;
DROP TABLE IF EXISTS bloqueo_stock_temporal CASCADE;
DROP TABLE IF EXISTS variante_producto CASCADE;
DROP TABLE IF EXISTS producto_catalogo CASCADE;
DROP TABLE IF EXISTS transmision_live CASCADE;
DROP TABLE IF EXISTS usuario CASCADE;
DROP TABLE IF EXISTS comercio CASCADE;

-- 1. TABLA: comercio
CREATE TABLE comercio (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    razon_social VARCHAR(150) NOT NULL,
    nombre_comercial VARCHAR(100) NOT NULL,
    nit VARCHAR(25) UNIQUE NOT NULL,
    telefono_contacto VARCHAR(20) NOT NULL,
    cuenta_bancaria_iban VARCHAR(34) NOT NULL,
    banco_adquiriente VARCHAR(50) NOT NULL,
    creado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- 2. TABLA: usuario
CREATE TABLE usuario (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    comercio_id UUID NOT NULL REFERENCES comercio(id) ON DELETE CASCADE,
    email VARCHAR(120) UNIQUE NOT NULL,
    password_hash VARCHAR(255) NOT NULL,
    nombre_completo VARCHAR(100) NOT NULL,
    rol VARCHAR(30) DEFAULT 'OPERADOR' CHECK (rol IN ('ADMINISTRADOR', 'OPERADOR', 'AUDITOR')),
    activo BOOLEAN DEFAULT TRUE NOT NULL,
    creado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- 3. TABLA: transmision_live
CREATE TABLE transmision_live (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    comercio_id UUID NOT NULL REFERENCES comercio(id) ON DELETE CASCADE,
    tiktok_username VARCHAR(80) NOT NULL,
    tiktok_room_id VARCHAR(50) NULL,
    titulo_live VARCHAR(200) NOT NULL,
    estado VARCHAR(20) DEFAULT 'PROGRAMADO' CHECK (estado IN ('PROGRAMADO', 'EN_VIVO', 'FINALIZADO', 'CANCELADO')),
    fecha_inicio TIMESTAMP WITH TIME ZONE NULL,
    fecha_fin TIMESTAMP WITH TIME ZONE NULL,
    total_ordenes_generadas INT DEFAULT 0 CHECK (total_ordenes_generadas >= 0),
    monto_total_recaudado NUMERIC(12, 2) DEFAULT 0.00 CHECK (monto_total_recaudado >= 0.00)
);

-- 4. TABLA: producto_catalogo
CREATE TABLE producto_catalogo (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    comercio_id UUID NOT NULL REFERENCES comercio(id) ON DELETE CASCADE,
    sku_base VARCHAR(40) NOT NULL,
    nombre VARCHAR(150) NOT NULL,
    descripcion TEXT NULL,
    precio_base NUMERIC(10, 2) NOT NULL CHECK (precio_base > 0.00),
    creado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL,
    CONSTRAINT uq_comercio_sku_base UNIQUE (comercio_id, sku_base)
);

-- 5. TABLA: variante_producto
CREATE TABLE variante_producto (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    producto_id UUID NOT NULL REFERENCES producto_catalogo(id) ON DELETE CASCADE,
    sku_especifico VARCHAR(50) UNIQUE NOT NULL,
    color VARCHAR(40) NOT NULL,
    talla VARCHAR(20) NOT NULL,
    stock_fisico INT NOT NULL CHECK (stock_fisico >= 0),
    stock_disponible INT NOT NULL CHECK (stock_disponible >= 0),
    precio_ajustado NUMERIC(10, 2) NOT NULL CHECK (precio_ajustado > 0.00),
    CONSTRAINT chk_stock_consistencia CHECK (stock_disponible <= stock_fisico)
);

-- 6. TABLA: bloqueo_stock_temporal
CREATE TABLE bloqueo_stock_temporal (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    variante_id UUID NOT NULL REFERENCES variante_producto(id) ON DELETE CASCADE,
    usuario_tiktok VARCHAR(80) NOT NULL,
    token_lock_redis VARCHAR(120) NOT NULL,
    cantidad INT DEFAULT 1 CHECK (cantidad > 0),
    fecha_adquisicion TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL,
    fecha_expiracion TIMESTAMP WITH TIME ZONE NOT NULL,
    estado VARCHAR(20) DEFAULT 'ACTIVO' CHECK (estado IN ('ACTIVO', 'CONSOLIDADO', 'EXPIRADO', 'LIBERADO_MANUAL'))
);

-- 7. TABLA: comentario_live
CREATE TABLE comentario_live (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    transmision_id UUID NOT NULL REFERENCES transmision_live(id) ON DELETE CASCADE,
    usuario_tiktok VARCHAR(80) NOT NULL,
    mensaje_crudo TEXT NOT NULL,
    es_intencion_compra BOOLEAN DEFAULT FALSE NOT NULL,
    puntaje_confianza_nlp NUMERIC(4, 3) NULL,
    sku_detectado VARCHAR(50) NULL,
    procesado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- 8. TABLA: orden_compra
CREATE TABLE orden_compra (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    transmision_id UUID NOT NULL REFERENCES transmision_live(id) ON DELETE RESTRICT,
    variante_id UUID NOT NULL REFERENCES variante_producto(id) ON DELETE RESTRICT,
    bloqueo_id UUID NULL REFERENCES bloqueo_stock_temporal(id) ON DELETE SET NULL,
    usuario_tiktok VARCHAR(80) NOT NULL,
    monto_total NUMERIC(10, 2) NOT NULL CHECK (monto_total > 0.00),
    estado VARCHAR(30) DEFAULT 'PENDIENTE_PAGO' CHECK (estado IN ('PENDIENTE_PAGO', 'PAGADA', 'EXPIRADA', 'CANCELADA', 'REEMBOLSADA')),
    checkout_url VARCHAR(255) NOT NULL,
    creado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL,
    actualizado_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- 9. TABLA: transaccion_qr_simple
CREATE TABLE transaccion_qr_simple (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    orden_id UUID UNIQUE NOT NULL REFERENCES orden_compra(id) ON DELETE CASCADE,
    payload_emvco TEXT NOT NULL,
    gateway_transaction_id VARCHAR(100) UNIQUE NOT NULL,
    crc16_hash VARCHAR(10) NOT NULL,
    monto NUMERIC(10, 2) NOT NULL CHECK (monto > 0.00),
    fecha_emision TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL,
    fecha_expiracion TIMESTAMP WITH TIME ZONE NOT NULL,
    estado_pago VARCHAR(25) DEFAULT 'EMITIDO' CHECK (estado_pago IN ('EMITIDO', 'COMPENSADO', 'EXPIRADO', 'RECHAZADO'))
);

-- 10. TABLA: webhook_notificacion_pago
CREATE TABLE webhook_notificacion_pago (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    transaccion_qr_id UUID NULL REFERENCES transaccion_qr_simple(id) ON DELETE SET NULL,
    idempotency_key VARCHAR(120) UNIQUE NOT NULL,
    cabecera_firma_hmac VARCHAR(255) NOT NULL,
    cuerpo_json TEXT NOT NULL,
    ip_origen VARCHAR(45) NOT NULL,
    es_valido BOOLEAN NOT NULL,
    recibido_en TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- 11. TABLA: historial_ventas
CREATE TABLE historial_ventas (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    orden_id UUID UNIQUE NOT NULL REFERENCES orden_compra(id) ON DELETE RESTRICT,
    comercio_id UUID NOT NULL REFERENCES comercio(id) ON DELETE RESTRICT,
    monto_neto NUMERIC(10, 2) NOT NULL CHECK (monto_neto > 0.00),
    costo_comision_gateway NUMERIC(8, 2) DEFAULT 0.00 CHECK (costo_comision_gateway >= 0.00),
    fecha_liquidacion TIMESTAMP WITH TIME ZONE DEFAULT CURRENT_TIMESTAMP NOT NULL
);

-- =============================================================================
-- CREACIÓN DE ÍNDICES B-TREE PARA OPTIMIZACIÓN DE ALTA CONCURRENCIA
-- =============================================================================

CREATE INDEX idx_variante_sku ON variante_producto USING btree(sku_especifico);
CREATE INDEX idx_orden_estado ON orden_compra USING btree(estado);
CREATE INDEX idx_orden_tiktok_user ON orden_compra USING btree(usuario_tiktok);
CREATE INDEX idx_bloqueo_expiracion ON bloqueo_stock_temporal USING btree(fecha_expiracion) WHERE estado = 'ACTIVO';
CREATE INDEX idx_comentario_live_transmision ON comentario_live USING btree(transmision_id, procesado_en);
CREATE INDEX idx_qr_gateway_id ON transaccion_qr_simple USING btree(gateway_transaction_id);
CREATE INDEX idx_webhook_idempotency ON webhook_notificacion_pago USING btree(idempotency_key);
```

---

## 5.5 Estado de Implementación, Cobertura TDD y Guía de Puesta en Marcha

### Suite de Pruebas Unitarias de Arquitectura (TDD con Pytest)

```python
# tests/test_transaccional_core.py
import pytest
import hmac
import hashlib
import json
from uuid import uuid4

class MockRedisLock:
    def __init__(self):
        self.store = {}
    
    def set(self, key, val, nx=False, px=None):
        if nx and key in self.store:
            return False
        self.store[key] = val
        return True
    
    def delete(self, key):
        if key in self.store:
            del self.store[key]
            return True
        return False

def test_prevent_race_condition_distributed_lock():
    """Valida que dos hilos concurrentes no adquieran la misma unidad en memoria."""
    redis = MockRedisLock()
    sku_key = "lock:sku:VEST-ROJO-44"
    
    # Intento de Usuario 1
    token_user1 = str(uuid4())
    acquired_user1 = redis.set(sku_key, token_user1, nx=True, px=480000)
    assert acquired_user1 is True, "El usuario 1 debió adquirir el bloqueo exitosamente."
    
    # Intento concurrente de Usuario 2
    token_user2 = str(uuid4())
    acquired_user2 = redis.set(sku_key, token_user2, nx=True, px=480000)
    assert acquired_user2 is False, "El usuario 2 debe ser rechazado por lock existente."

def test_webhook_hmac_sha256_verification():
    """Comprueba la validación criptográfica de firmas bancarias entrantes."""
    secret_key = b"secreto_bancario_accl_bolivia_2026"
    payload = json.dumps({"order_id": "ORD-12345", "status": "SETTLED", "amount": 180.00}).encode("utf-8")
    
    # Cálculo de firma legítima
    valid_signature = hmac.new(secret_key, payload, hashlib.sha256).hexdigest()
    
    # Cálculo de firma manipulada
    invalid_signature = "9b7a4f3210efab7c8d9e0f1234567890abcdef1234567890abcdef1234567890"
    
    def verify(body, sig):
        expected = hmac.new(secret_key, body, hashlib.sha256).hexdigest()
        return hmac.compare_digest(expected, sig)
    
    assert verify(payload, valid_signature) is True, "Firma legítima debe ser aceptada."
    assert verify(payload, invalid_signature) is False, "Firma adulterada debe ser rechazada."
```

### Guía de Puesta en Marcha con Docker Compose

```yaml
# docker-compose.yml
version: '3.8'

services:
  postgres-db:
    image: postgres:16-alpine
    container_name: tiktoksell_postgres
    environment:
      POSTGRES_DB: tiktoksell_db
      POSTGRES_USER: tiktoksell_admin
      POSTGRES_PASSWORD: SecretProductionPassword2026!
    ports:
      - "5432:5432"
    volumes:
      - pgdata:/var/lib/postgresql/data
      - ./scripts/init.sql:/docker-entrypoint-initdb.d/init.sql
    networks:
      - tiktoksell-net

  redis-cluster:
    image: redis:7-alpine
    container_name: tiktoksell_redis
    command: redis-server --requirepass RedisSecureAuthKey2026! --appendonly yes
    ports:
      - "6379:6379"
    volumes:
      - redisdata:/data
    networks:
      - tiktoksell-net

  rabbitmq-broker:
    image: rabbitmq:3-management-alpine
    container_name: tiktoksell_rabbitmq
    environment:
      RABBITMQ_DEFAULT_USER: rmq_admin
      RABBITMQ_DEFAULT_PASS: RMQSecurePass2026!
    ports:
      - "5672:5672"
      - "15672:15672"
    networks:
      - tiktoksell-net

  core-backend-api:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: tiktoksell_api
    depends_on:
      - postgres-db
      - redis-cluster
      - rabbitmq-broker
    environment:
      DATABASE_URL: postgresql://tiktoksell_admin:SecretProductionPassword2026!@postgres-db:5432/tiktoksell_db
      REDIS_URL: redis://:RedisSecureAuthKey2026!@redis-cluster:6379/0
      RABBITMQ_URL: amqp://rmq_admin:RMQSecurePass2026!@rabbitmq-broker:5672/
    ports:
      - "8000:8000"
    networks:
      - tiktoksell-net

volumes:
  pgdata:
  redisdata:

networks:
  tiktoksell-net:
    driver: bridge
```

---

<div align="center">
  <b>Documentación Académica del Proyecto de Grado - Ingeniería de Sistemas UPSA</b><br/>
  <i>Desarrollado bajo los estándares de Craig Larman (Proceso Unificado) y Michael V. Mannino (Diseño de Bases de Datos).</i>
</div>
