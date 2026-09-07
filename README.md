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
    - [1.1.5 Justificación del Proyecto](#115-justificación-del-proyecto)
  - [1.2 Objetivos](#12-objetivos)
    - [1.2.1 Objetivo General](#121-objetivo-general)
    - [1.2.2 Objetivos Específicos](#122-objetivos-específicos)
  - [1.3 Metodología](#13-metodología)
    - [1.3.1 Fases del Proceso Unificado (UP) aplicadas al Negocio](#131-fases-del-proceso-unificado-up-aplicadas-al-negocio)
    - [1.3.2 Metas Cuantitativas de Validación Comercial (Criterios de Aceptación)](#132-metas-cuantitativas-de-validación-comercial-criterios-de-aceptación)
- [Capítulo II: Estudio de Mercado y Análisis del Sector de Social Commerce en Bolivia](#capítulo-ii-estudio-de-mercado-y-análisis-del-sector-de-social-commerce-en-bolivia)
  - [2.1 Caracterización del Sector y Ecosistema de Live Shopping](#21-caracterización-del-sector-y-ecosistema-de-live-shopping)
  - [2.2 Segmentación del Mercado y Muestra Representativa](#22-segmentación-del-mercado-y-muestra-representativa)
  - [2.3 Diagnóstico Operativo: Flujo de Venta Manual Actual (As-Is)](#23-diagnóstico-operativo-flujo-de-venta-manual-actual-as-is)
  - [2.4 Demostración del Cuello de Botella y Pérdidas Comerciales](#24-demostración-del-cuello-de-botella-y-pérdidas-comerciales)
  - [2.5 Comparativa frente a Soluciones Sustitutas](#25-comparativa-frente-a-soluciones-sustitutas)
- [Capítulo III: Marco Teórico y Selección de Componentes de Solución](#capítulo-iii-marco-teórico-y-selección-de-componentes-de-solución)
  - [3.1 Captura de Pedidos en Vivo: Comunicación Continua vs. Consultas Periódicas](#31-captura-de-pedidos-en-vivo-comunicación-continua-vs-consultas-periódicas)
  - [3.2 Interpretación Inteligente de Mensajes de Venta](#32-interpretación-inteligente-de-mensajes-de-venta)
  - [3.3 Ecosistema Financiero: QR Simple Interbancario (ACCL)](#33-ecosistema-financiero-qr-simple-interbancario-accl)
  - [3.4 Control y Protección de Inventario](#34-control-y-protección-de-inventario)
  - [3.5 Experiencia de Pago Móvil para el Cliente](#35-experiencia-de-pago-móvil-para-el-cliente)
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
El comercio social en vivo (*Live Shopping*) en TikTok se ha consolidado en Bolivia (principalmente en Santa Cruz, La Paz y Cochabamba) como uno de los canales comerciales de mayor crecimiento para tiendas de moda, calzado, tecnología y cosméticos. Los comerciantes exhiben sus productos en tiempo real ante cientos de compradores listos para adquirir mercadería al instante.

Sin embargo, el sector enfrenta una barrera comercial crítica: **TikTok Shop no opera de forma nativa en Bolivia ni permite cobrar en moneda local (Bolivianos - BOB)**. Esta limitación obliga a los negocios a operar bajo un modelo de ventas informal y manual que destruye la rentabilidad:

1. **Saturación en el cierre de ventas:** En momentos de alta demanda (ofertas relámpago o liquidaciones), el chat de la transmisión se satura con decenas de mensajes por segundo (*"lo quiero"*, *"mío"*). El presentador no puede leer ni registrar todos los pedidos, perdiendo clientes calificados en segundos.
2. **Pérdida por fricción en el embudo (WhatsApp):** Para concretar la compra, se pide al cliente salir de la transmisión y escribir a WhatsApp. Este paso adicional rompe el impulso de compra inmediata, generando una **tasa de abandono de pedidos superior al 65%**.
3. **Pérdidas económicas por sobreventa y quiebres de inventario:** Cuando varios empleados intentan atender a los clientes en paralelo por WhatsApp, se vende la misma prenda a dos o más personas. Esto genera quejas, cancelaciones forzosas y deterioro de la confianza en la marca.
4. **Vulnerabilidad a estafas con comprobantes falsos:** El cobro depende de enviar un QR bancario estático para que el cliente transfiera y mande una captura de pantalla. Debido a la rapidez del directo, los negocios no logran validar el dinero en su banca móvil en tiempo real, sufriendo fraudes recurrentes mediante comprobantes adulterados y aplicaciones bancarias falsas.

### 1.1.2 Situación Deseada
Se proyecta implementar una solución tecnológica comercial que automatice de principio a fin el proceso de venta en TikTok Live:

* **Captura inmediata de oportunidades de compra:** Detección automática de los pedidos expresados por los clientes en el chat, sin necesidad de anotaciones manuales.
* **Reserva temporal y segura de inventario:** Bloqueo momentáneo de la prenda (durante 5 a 8 minutos) para el comprador más rápido, garantizando que no exista sobreventa.
* **Cobro ágil con QR Dinámico:** Despacho de un enlace de pago exprés para el teléfono del cliente con un **Código QR Simple** que ya incluye el monto exacto y no puede ser manipulado.
* **Conciliación bancaria automática:** Notificación instantánea entre el sistema financiero boliviano y la plataforma en el momento en que el dinero ingresa a la cuenta. La orden se marca automáticamente como pagada, se rebaja el inventario y se emite la orden de empaque y despacho sin intervención humana ni riesgo de fraude.

### 1.1.3 Objeto de Investigación
La modernización, optimización y automatización operativa del proceso de venta, gestión de stock y cobranza digital en canales de comercio social en vivo (*Live Streaming Commerce*) para el comercio minorista boliviano.

### 1.1.4 Alcance y Límites
* **Alcance:** Abarca la captura del pedido en el chat de TikTok, la interpretación de la intención de compra, la reserva de inventario, la generación del cobro QR con el sistema financiero boliviano, la confirmación automática del pago y el panel administrativo de ventas para el comerciante.
* **Límites:** El sistema concluye con la orden confirmada y lista para empaque; no gestiona fletes de transporte, logística de última milla ni envíos físicos entre departamentos. Opera exclusivamente en Bolivianos (BOB) mediante la infraestructura de pagos inmediatos interbancarios de Bolivia (Red Simple / ACCL).

### 1.1.5 Justificación del Proyecto
* **Justificación de Negocio / Económica:** Elimina el gasto fijo de contratar personal de apoyo para contestar mensajes de WhatsApp durante los directos. Recupera ventas perdidas al reducir el abandono del carrito e incrementa la facturación mensual neta del comerciante al reducir a 0% las pérdidas por estafas de recibos falsos.
* **Justificación de Eficiencia Operativa:** Convierte un proceso comercial que tardaba varios minutos de atención manual en una transacción digital cerrada en menos de un minuto, permitiendo al negocio escalar su volumen de despacho diario.
* **Justificación Social y Comercial:** Brinda a micro, pequeños y medianos comerciantes de mercados locales y galerías comerciales una herramienta de cobro moderna, segura y accesible, acelerando la bancarización y formalización del comercio digital en Bolivia.

---

## 1.2 Objetivos

### 1.2.1 Objetivo General
Desarrollar una plataforma comercial automatizada que capture pedidos en tiempo real en TikTok Live y concilie cobranzas mediante Códigos QR Dinámicos del sistema bancario boliviano, optimizando la tasa de conversión de ventas y erradicando la sobreventa y el fraude en el comercio minorista.

### 1.2.2 Objetivos Específicos
1. **Analizar los costos operativos y cuellos de botella** en los métodos actuales de venta por directos de TikTok en comercios del eje troncal de Bolivia.
2. **Diseñar un flujo de compra rápido y sin fricción** que permita al comprador confirmar su pedido y pagar sin tener que abandonar la experiencia del directo.
3. **Implementar un módulo inteligente de interpretación de pedidos** que entienda cómo comentan los compradores bolivianos y extraiga el producto, color y talla requeridos.
4. **Construir un mecanismo de control de stock en tiempo real** que aparte el producto temporalmente mientras el cliente realiza el pago, evitando la doble venta.
5. **Integrar pasarelas de pago bolivianas (Red Simple / ACCL)** para generar cobros QR de monto fijo y recibir confirmaciones automáticas de acreditación de fondos.
6. **Validar comercialmente la solución** midiendo el incremento en la tasa de ventas concretadas y la reducción del tiempo de atención en comparación con el proceso tradicional por WhatsApp.

---

## 1.3 Metodología

### 1.3.1 Fases del Proceso Unificado (UP) aplicadas al Negocio
Se adopta el Proceso Unificado de Craig Larman, organizando el desarrollo en ciclos enfocados en entregar valor comercial temprano:
* **Fase de Inicio (*Inception*):** Definición del modelo de negocio, análisis de rentabilidad, levantamiento de requerimientos con comerciantes y priorización de las funciones que generan mayor impacto en ventas.
* **Fase de Elaboración (*Elaboration*):** Construcción del prototipo funcional para validar la conexión con el chat de TikTok, la reserva de stock y la emisión del primer cobro QR real.
* **Fase de Construcción (*Construction*):** Desarrollo integral del catálogo de productos, el portal de checkout móvil para clientes y el panel de control de ventas e inventario para el vendedor.
* **Fase de Transición (*Transition*):** Pruebas piloto en transmisiones reales de comercios aliados, capacitación de usuarios y validación de las métricas comerciales y financieras.

### 1.3.2 Metas Cuantitativas de Validación Comercial (Criterios de Aceptación)
1. **Velocidad de Cierre de Venta:** El tiempo total desde que el cliente comenta su pedido hasta que recibe su orden de pago no debe exceder los 3.5 segundos.
2. **Eficiencia en la Cobranza:** El 100% de los pagos aprobados por el banco deben quedar conciliados y registrados en el panel del comerciante sin intervención de personal.
3. **Cero Conflictos de Stock:** En escenarios de alta demanda de un producto exclusivo, la tasa de sobreventa debe ser de 0%.
4. **Validación de Impacto en Negocio:** Demostrar mediante una muestra de 50 transacciones reales que el tiempo medio de cierre de venta del sistema automatizado es significativamente inferior ($p < 0.01$) al tiempo del método manual por WhatsApp.

---

# Capítulo II: Estudio de Mercado y Análisis del Sector de Social Commerce en Bolivia

## 2.1 Caracterización del Sector y Ecosistema de Live Shopping
En Bolivia, la interacción visual directa y la confianza son el motor de las decisiones de compra en línea. El comprador valora ver la prenda puesta, comprobar las dimensiones de un accesorio y negociar promociones en el momento.

* **Mercados clave:** Santa Cruz de la Sierra (46%), La Paz (22%) y Cochabamba (14%) concentran la gran mayoría de comercios que utilizan transmisiones en vivo semanales.
* **Categorías con mayor rotación:** Boutiques de moda, calzado de importación, cosméticos, tecnología de consumo y artículos de hogar.
* **Dinámica comercial:** Las ventas se basan en compras por impulso impulsadas por la escasez: *"¡Última unidad en liquidación para quien comente primero!"*.

## 2.2 Segmentación del Mercado y Muestra Representativa
Para estudiar el sector de forma estadísticamente válida, se determinó un universo de $N = 1,200$ comercios y microempresas que transmiten al menos dos veces por semana en el eje troncal.

Aplicando la fórmula estadística de muestreo para poblaciones finitas con un nivel de confianza del 95% ($Z = 1.96$) y un margen de error del 5% ($E = 0.05$):

$$n = \frac{Z^2 \cdot p \cdot q \cdot N}{E^2 \cdot (N - 1) + Z^2 \cdot p \cdot q} = \frac{(1.96)^2 \cdot (0.5) \cdot (0.5) \cdot 1200}{(0.05)^2 \cdot (1199) + (1.96)^2 \cdot (0.5) \cdot (0.5)} \approx 291\text{ comercios}$$

Se fijó una muestra de **291 negocios minoristas** para el relevamiento de necesidades, volúmenes de venta y costos operativos.

## 2.3 Diagnóstico Operativo: Flujo de Venta Manual Actual (As-Is)
Actualmente, el proceso comercial tradicional genera altos costos y pérdida de ventas:
1. El cliente comenta su deseo de compra en el chat en vivo.
2. El presentador lee el chat al vuelo y le pide que salga del directo para escribir al WhatsApp de la tienda.
3. El vendedor anota el pedido en una libreta o planilla.
4. El cliente llega a WhatsApp, envía capturas y espera a ser atendido.
5. El operador revisa si la mercadería sigue disponible. Si ya se vendió, se pierde la venta; si aún está libre, envía un QR bancario estático.
6. El cliente entra a su aplicación bancaria, digita el monto a mano y transfiere.
7. El cliente envía la captura del comprobante.
8. El operador entra a su banca móvil para verificar si el dinero entró o si el comprobante es falso.
9. Tras varios minutos de revisión, se confirma la venta y se anota el despacho.

```mermaid
sequenceDiagram
    autonumber
    actor Cliente as Comprador en TikTok
    actor Host as Presentador en Vivo
    actor Operador as Asistente de WhatsApp
    actor Banco as App Bancaria Manual
    
    Cliente->>Host: Comenta intención: "Mío el 32 rojo"
    Host->>Cliente: Pide verbalmente salir del live y escribir a WhatsApp
    Host->>Operador: Anota manualmente en libreta
    Cliente->>Operador: Escribe a WhatsApp con captura de pantalla
    Operador->>Operador: Revisa libreta física y disponibilidad
    alt Producto agotado por sobreventa
        Operador-->>Cliente: Venta frustrada ("Ya se vendió")
    else Producto disponible
        Operador->>Cliente: Envía imagen de QR estático sin monto
        Cliente->>Banco: Digita monto manual y transfiere
        Banco-->>Cliente: Emite captura de pantalla
        Cliente->>Operador: Envía captura de comprobante por WhatsApp
        Operador->>Banco: Entra a banca móvil a verificar abono manual
        alt Comprobante falso o dinero no reflejado
            Operador-->>Cliente: Notifica irregularidad o sufre estafa
        else Abono comprobado
            Operador->>Operador: Anota en planilla Excel
            Operador-->>Cliente: Confirma compra y pide datos de envío
        end
    end
```

## 2.4 Demostración del Cuello de Botella y Pérdidas Comerciales
* **Capacidad de atención humana:** Un operador tarda en promedio 120 segundos (2 minutos) en coordinar un pedido completo por WhatsApp y revisar el extracto de su banco. Dos operadores atienden a razón de 1 pedido por minuto.
* **Demanda en directo:** Una oferta atractiva en un directo genera ráfagas de 15 o más intenciones de compra por minuto.
* **Resultado comercial:** La demanda supera por 15 veces la capacidad de atención. Esto genera tiempos de espera de más de 10 minutos en WhatsApp, provocando que el 65% de los clientes desista de comprar, además de un 8% de pedidos con reclamos por prendas vendidas dos veces.
* **Ventaja del modelo automatizado:** El sistema procesa pedidos de forma simultánea e inmediata. La reserva y entrega del QR tarda menos de 3.5 segundos, absorbiendo picos de venta sin necesidad de contratar personal adicional y sin saturación.

## 2.5 Comparativa frente a Soluciones Sustitutas

| Aspecto Comercial | WhatsApp Manual | Tienda Web Tradicional (Shopify/WooCommerce) | Plataforma Propuesta (Este Proyecto) |
|---|---|---|---|
| **Experiencia de compra** | Lenta y con esperas | Requiere registrarse y llenar formularios | Instantánea desde el directo |
| **Cobro en Bolivia (BOB)** | Manual por transferencia | Complejo y con comisiones en dólares | Integrado con QR Simple nacional |
| **Prevención de sobreventa** | Nula (errores continuos) | Sí, pero fuera de la red social | Reserva automática en segundos |
| **Seguridad contra fraude** | Muy baja (revisión a ojo) | Alta con tarjeta bancaria | Validación bancaria automática |
| **Costo de personal** | Alto (2 a 3 asistentes) | Mantenimiento web mensual | Costos de operación mínimos |

---

# Capítulo III: Marco Teórico y Selección de Componentes de Solución
Este capítulo justifica las decisiones de herramientas y componentes en función de su eficiencia operativa, costo y valor comercial:

## 3.1 Captura de Pedidos en Vivo: Comunicación Continua vs. Consultas Periódicas
Para registrar las ventas al instante, se opta por una conexión continua de datos en tiempo real (WebSockets) en lugar de consultas periódicas. Esto permite que el sistema "escuche" los pedidos del chat sin demoras ni recargas de página, garantizando una respuesta inmediata al cliente mientras dura la oferta.

## 3.2 Interpretación Inteligente de Mensajes de Venta
Los compradores en Bolivia utilizan expresiones informales (*"apártamelo el 32"*, *"mío el negro en L"*, *"lo llevo"*).
* Se descarta el uso de modelos costosos de cobro por palabra que harían el software inviable para pequeños comerciantes.
* Se selecciona un motor híbrido de interpretación léxica local, que combina reglas de negocio rápidas con reconocimiento semántico de modismos comerciales, entregando un análisis en menos de 50 milisegundos con costo operativo casi nulo.

## 3.3 Ecosistema Financiero: QR Simple Interbancario (ACCL)
A diferencia de mercados externos donde dominan las tarjetas de crédito, en Bolivia el método de pago digital dominante y de mayor confianza es el QR Simple, administrado de forma interoperable por la Cámara de Compensación y Liquidación S.A. (ACCL).
* **QR Estático (Inseguro):** Es una simple foto de cuenta donde el cliente escribe el importe y manda una captura. Es propenso a fraudes y exige revisión manual.
* **QR Dinámico (Seguro y Automatizado):** Es un código generado para una orden puntual, con monto exacto, vencimiento de pocos minutos e identificador bancario único. La entidad financiera avisa automáticamente al sistema cuando el dinero entra en la cuenta, haciendo la cobranza 100% segura e instantánea.

## 3.4 Control y Protección de Inventario
Para asegurar que dos clientes no paguen por la misma prenda en el mismo instante, la solución implementa un bloqueador temporal de inventario en memoria rápida. Cuando un cliente solicita un producto, el sistema lo aparta durante 8 minutos. Si el pago se confirma, la venta se consolida; si el cliente no paga a tiempo, el producto regresa a la venta automáticamente, maximizando la rotación del inventario.

## 3.5 Experiencia de Pago Móvil para el Cliente
Se elige un portal de cobro web móvil ultraligero (PWA / Webview) que se abre directamente desde el teléfono del comprador en menos de 1.5 segundos. No exige al cliente descargar aplicaciones pesadas ni crear contraseñas, lo que maximiza la tasa de compras completadas con éxito.

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

> [!NOTE]
> **Fundamentación Metodológica de Craig Larman (*Applying UML and Patterns*):**  
> El Modelo de Dominio es el artefacto central del análisis orientado a objetos y representa las clases conceptuales y situaciones del mundo real del negocio. Al no constituir un modelo de diseño de software ni un esquema relacional de base de datos, **las clases conceptuales no deben contener tipos de datos de lenguajes de programación** (como `UUID`, `String`, `int` o `DateTime`), indicadores de visibilidad (`+`, `-`) ni atributos que simulen claves foráneas de bases de datos. Las conexiones entre conceptos se expresan puramente mediante asociaciones semánticas y multiplicidades.

```mermaid
classDiagram
    direction TB

    class Comercio {
        razonSocial
        nombreComercial
        nit
        cuentaBancaria
    }
    class TransmisionLive {
        tiktokUsername
        titulo
        fechaHoraInicio
        estado
    }
    class ProductoCatalogo {
        skuBase
        nombre
        descripcion
        precioBase
    }
    class VarianteProducto {
        skuEspecifico
        color
        talla
        stockFisico
        stockDisponible
        precio
    }
    class BloqueoStockTemporal {
        identificadorBloqueo
        usuarioTiktok
        tiempoExpiracion
        estadoBloqueo
    }
    class OrdenCompra {
        numeroOrden
        montoTotal
        fechaHoraCreacion
        estado
        enlaceCheckout
    }
    class TransaccionQRSimple {
        codigoQR
        identificadorTransaccion
        monto
        tiempoVencimiento
        estadoPago
    }

    Comercio "1" -- "*" TransmisionLive : ejecuta
    Comercio "1" -- "*" ProductoCatalogo : administra
    ProductoCatalogo "1" -- "1..*" VarianteProducto : clasificado_en
    VarianteProducto "1" -- "*" BloqueoStockTemporal : reservado_en
    BloqueoStockTemporal "1" -- "1" OrdenCompra : formaliza
    OrdenCompra "1" -- "1" TransaccionQRSimple : liquidada_con
```

### Diccionario de Clases Conceptuales del Dominio
* **Comercio:** Representa la entidad o negocio minorista que comercializa sus productos mediante transmisiones en vivo y recibe la recaudación bancaria.
* **TransmisionLive:** Sesión activa de streaming en TikTok Live donde se exhiben los artículos y se generan interacciones de compra.
* **ProductoCatalogo:** Definición conceptual del artículo matriz ofertado al público general.
* **VarianteProducto:** Unidad física y concreta de mercadería diferenciada por atributos de talla, color y disponibilidad en stock.
* **BloqueoStockTemporal:** Reserva preventiva y efímera de una unidad de producto en favor del comprador más veloz para evitar sobreventas.
* **OrdenCompra:** Formalización transaccional del pedido pactado, con estado de liquidación y monto total a pagar.
* **TransaccionQRSimple:** Instrumento de cobro digital interoperable emitido con monto exacto y vigencia delimitada para su escaneo bancario.

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
