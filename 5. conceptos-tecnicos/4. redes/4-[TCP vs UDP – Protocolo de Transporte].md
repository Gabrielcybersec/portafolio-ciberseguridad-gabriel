# 🚀 TCP vs UDP – Protocolo de Transporte (Capa 4 OSI)

---

## 🧠 ¿Para qué sirven TCP y UDP?

El protocolo IP (Capa 3) permite llegar a un host.  
Pero para que los **procesos dentro de ese host** (como navegadores, apps o servicios) se comuniquen entre sí, necesitamos los **protocolos de transporte**, ubicados en la **Capa 4 del modelo OSI**.

✅ Los dos principales protocolos de transporte son:

- **TCP (Transmission Control Protocol)**  
- **UDP (User Datagram Protocol)**

---

## 📦 UDP – Protocolo sin conexión

### 🔹 Características principales

- No establece conexión previa
- No garantiza entrega ni orden
- No hay verificación ni retransmisión de paquetes
- Más rápido y eficiente en términos de recursos que TCP

### 🔹 Ejemplo de la vida real

> 📨 Es como enviar una carta sin acuse de recibo.  
> Nunca sabrás si fue recibida.

### 🔹 Identificación de procesos

- Usa **números de puerto** (rango: `1–65535`, puerto `0` reservado)

### 🔹 Usos típicos de UDP

- 🎥 **Streaming** (YouTube, Twitch, Spotify)
- 🎮 Juegos en línea
- 🌐 DNS (Domain Name System)
- 📡 DHCP (Dynamic Host Configuration Protocol)
- 📞 VoIP (Llamadas por Internet)

---

## 🔐 TCP – Protocolo orientado a conexión

### 🔹 Características principales

- Establece conexión antes de enviar datos (confiable)
- Garantiza la entrega **completa**, **en orden** y **sin duplicados**
- Implementa:
  - Números de secuencia
  - Confirmaciones (ACKs)
  - Control de flujo
  - Recuperación de errores

### 🔹 Ejemplo de la vida real

> 📬 Como enviar una carta con acuse de recibo.  
> El receptor firma al recibirla.

### 🔁 Establecimiento de conexión: Three-Way Handshake

1. **SYN** → Cliente inicia conexión con número de secuencia
2. **SYN-ACK** → Servidor responde con número propio y ACK del cliente
3. **ACK** → Cliente responde, se establece la conexión

✅ A partir de aquí se pueden intercambiar datos.

### 🔹 Usos típicos de TCP

- 🌐 Navegación Web (HTTP, HTTPS)
- ✉️ Correo electrónico (IMAP, POP3, SMTP)
- 📁 Transferencia de archivos (FTP)
- 🔐 Acceso remoto seguro (SSH, Telnet)

---

## 🎯 Comparación resumida

| Característica       | **TCP**                                | **UDP**                                     |
|----------------------|----------------------------------------|---------------------------------------------|
| Tipo de conexión     | Orientado a conexión                   | Sin conexión                                |
| Fiabilidad           | Alta (verifica y reenvía)              | Baja (no verifica ni reenvía)               |
| Orden de entrega     | Garantizado                            | No garantizado                              |
| Velocidad            | Más lento (por mecanismos de control)  | Más rápido (menor carga de control)         |
| Casos de uso típicos | Web, Email, SSH, FTP                   | Streaming, Juegos, DNS, DHCP                |
| Usa puertos          | Sí (`1–65535`, `0` reservado)          | Sí (`1–65535`, `0` reservado)               |

---

📌 **Ambos usan puertos** para identificar servicios dentro del host.  
🔒 **TCP** es preferido cuando se requiere precisión, y **UDP** cuando se necesita velocidad.

