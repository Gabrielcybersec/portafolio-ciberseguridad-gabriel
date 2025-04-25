# 🌐 Modelo OSI (Open Systems Interconnection)

**Desarrollado por:** ISO (International Organization for Standardization)

El modelo OSI es un marco teórico que estandariza las funciones de un sistema de telecomunicaciones o de computación en siete capas. Este modelo facilita la interoperabilidad entre productos y software de diferentes fabricantes.

---

## 🧠 Descripción Técnica por Capa

### 🟣 Capa 7 – Aplicación
- **Función:** Proporciona interfaces directas al usuario para acceder a servicios de red.
- **Protocolos comunes:** `HTTP`, `FTP`, `DNS`, `SMTP`, `IMAP`, `POP3`
- **Unidad de datos (PDU):** Datos

---

### 🟣 Capa 6 – Presentación
- **Función:** Traduce, codifica, cifra y comprime datos para la capa de aplicación.
- **Ejemplos:** `SSL/TLS`, `JPEG`, `MPEG`, `ASCII`
- **Transformación de datos:** bits ↔ formato de aplicación

---

### 🟣 Capa 5 – Sesión
- **Función:** Establece, mantiene y finaliza sesiones entre aplicaciones.
- **Protocolos:** `NetBIOS`, `RPC`, `PPTP`
- **Servicios:** Control de diálogo, sincronización, recuperación por checkpoint

---

### 🟣 Capa 4 – Transporte
- **Función:** Entrega fiable (o no) de datos entre hosts.
- **Protocolos:** `TCP` (confiable), `UDP` (rápido, no confiable)
- **Mecanismos:** Segmentación, secuenciación, ACKs, control de flujo y errores
- **PDU:** Segmentos (TCP) / Datagramas (UDP)

---

### 🟣 Capa 3 – Red
- **Función:** Direccionamiento lógico y enrutamiento entre redes.
- **Protocolos:** `IP`, `ICMP`, `IGMP`, `IPSec`
- **Encabezado IP:** Origen, destino, TTL, fragmentación
- **PDU:** Paquete

---

### 🟣 Capa 2 – Enlace de Datos
- **Función:** Comunicación entre nodos, control de acceso al medio y detección de errores.
- **Subcapas:** `LLC`, `MAC`
- **Protocolos:** `Ethernet 802.3`, `Wi-Fi 802.11`, `ARP`
- **Estructura de trama:**
  - MAC origen y destino
  - EtherType (`0x0800` = IPv4)
  - CRC/FCS
- **PDU:** Trama

---

### ⚫ Capa 1 – Física
- **Función:** Transmisión de bits en el medio físico (eléctrico, óptico o electromagnético).
- **Medios comunes:** Par trenzado (UTP), fibra óptica, aire (Wi-Fi)
- **Representación de bits:**
  - `UTP`: 0V = 0, 5V = 1
  - `Fibra`: luz apagada = 0, luz encendida = 1
  - `Wi-Fi`: modulación de amplitud/frecuencia
- **Unidad:** Bit

---

## 📋 Tabla Resumen

| Nº de Capa | Nombre             | Funciones Principales                                | Protocolos / Tecnologías          |
|------------|--------------------|------------------------------------------------------|-----------------------------------|
| 7          | Aplicación         | Servicios de red para aplicaciones                   | HTTP, FTP, SMTP, DNS              |
| 6          | Presentación       | Codificación, cifrado, compresión                    | JPEG, SSL, TLS                    |
| 5          | Sesión             | Gestión de sesiones y sincronización                 | RPC, NetBIOS                      |
| 4          | Transporte         | Entrega fiable, segmentación, control de errores     | TCP, UDP                          |
| 3          | Red                | Enrutamiento y direccionamiento                      | IP, ICMP, IPSec                   |
| 2          | Enlace de Datos    | MAC, acceso al medio, tramas, detección de errores   | Ethernet, Wi-Fi, ARP              |
| 1          | Física             | Bits, señalización, codificación de medios físicos   | UTP, fibra óptica, radiofrecuencia|

---

## 📚 Referencias
- ISO/IEC 7498-1
- IEEE 802 family standards
- [RFC 1122](https://datatracker.ietf.org/doc/html/rfc1122)
- [RFC 791](https://datatracker.ietf.org/doc/html/rfc791)
- [RFC 793](https://datatracker.ietf.org/doc/html/rfc793)
