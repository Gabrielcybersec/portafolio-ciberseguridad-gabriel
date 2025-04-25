# 📚 Modelo OSI (Open Systems Interconnection)

Desarrollado por la **ISO (International Organization for Standardization)**, el modelo OSI proporciona un marco teórico para entender cómo se comunican los sistemas a través de una red mediante **siete capas jerárquicas**, cada una con funciones específicas.

---

## 🧠 ¿Qué es el Modelo OSI?

Es una arquitectura de red en capas que permite la **interoperabilidad entre diferentes dispositivos y tecnologías**, definiendo cómo los datos deben viajar desde una aplicación en un dispositivo hasta una aplicación en otro.

---

## 🌐 Capas del Modelo OSI – Descripción Técnica

---

### 🔹 Capa 7: Aplicación (Application Layer)

- **Función técnica:** Proporcionar interfaces y servicios para que las aplicaciones de usuario accedan a funciones de red.
- **Servicios clave:** Transferencia de archivos, correo electrónico, acceso web, servicios de directorio.
- **Protocolos comunes:** HTTP, FTP, DNS, POP3, IMAP, SMTP

---

### 🔹 Capa 6: Presentación (Presentation Layer)

- **Función técnica:** Traducción de sintaxis, codificación, **compresión** y **cifrado/descifrado** de datos.
- **Ejemplos de codificación:** ASCII, Unicode
- **Ejemplos de formatos de datos:** JPEG, MPEG, PNG
- **Protocolos relacionados:** TLS, SSL

---

### 🔹 Capa 5: Sesión (Session Layer)

- **Función técnica:** Establecimiento, gestión y terminación de sesiones (conexiones lógicas) entre aplicaciones.
- **Mecanismos:** Sincronización, puntos de control, recuperación tras fallos.
- **Protocolos comunes:** NetBIOS, RPC, NFS

---

### 🔹 Capa 4: Transporte (Transport Layer)

- **Función técnica:** Segmentación de datos, control de errores, control de flujo y **garantía de entrega confiable**.
- **Protocolos:** 
  - **TCP (Transmission Control Protocol):** Orientado a conexión, confiable, con retransmisión y ACKs.
  - **UDP (User Datagram Protocol):** Sin conexión, más rápido, no garantiza entrega.
- **PDU (Unidad de datos):** Segmento

---

### 🔹 Capa 3: Red (Network Layer)

- **Función técnica:** Direccionamiento lógico, encaminamiento (routing), fragmentación de paquetes.
- **Protocolos clave:** IP, ICMP, IGMP, IPSec
- **Encabezado:** Contiene dirección IP origen y destino, TTL, protocolo.

---

### 🔹 Capa 2: Enlace de Datos (Data Link Layer)

- **Función técnica:** Transferencia fiable de tramas entre nodos conectados directamente, detección y corrección de errores físicos.
- **Subcapas:**
  - **LLC (Logical Link Control):** Identifica protocolos de red, multiplexa protocolos.
  - **MAC (Media Access Control):** Acceso al medio, direccionamiento MAC.
- **Protocolos comunes:** Ethernet (802.3), Wi-Fi (802.11), PPP, ARP
- **Componentes adicionales:** CRC, FCS, control de acceso al medio

---

### 🔹 Capa 1: Física (Physical Layer)

- **Función técnica:** Transmisión y recepción de bits crudos a través de medios físicos. Define voltajes, niveles de señal, tasas de bits, tipo de conectores.
- **Medios físicos comunes:**
  - UTP (eléctrico)
  - Fibra óptica (óptico)
  - Ondas de radio (Wi-Fi, Bluetooth)
- **Señales:**
  - 0V / 5V → bits binarios
  - Luz apagada/encendida
  - Amplitud, frecuencia o fase modulada (radiofrecuencia)
- **Técnicas utilizadas:** Multiplexación (TDM, FDM, WDM)

---

## 📋 Tabla de Resumen Técnico

| Nº de Capa | Nombre | Función Técnica | Protocolos / Normas |
|------------|--------|------------------|----------------------|
| Capa 7 | Aplicación | Interfaces de red para aplicaciones | HTTP, FTP, DNS, SMTP, IMAP |
| Capa 6 | Presentación | Codificación, cifrado, compresión | Unicode, JPEG, MPEG, TLS |
| Capa 5 | Sesión | Control de sesiones, sincronización | RPC, NetBIOS, NFS |
| Capa 4 | Transporte | Segmentación, entrega confiable | TCP, UDP |
| Capa 3 | Red | Direccionamiento IP, enrutamiento | IP, ICMP, IPSec |
| Capa 2 | Enlace de Datos | Control MAC, detección de errores | Ethernet, Wi-Fi, ARP |
| Capa 1 | Física | Transmisión de bits | UTP, fibra óptica, señales RF |

---

## 🧠 Consideraciones Finales

- El modelo OSI **no es un protocolo**, sino un marco conceptual.
- Aunque muchas redes modernas utilizan el modelo TCP/IP, el modelo OSI **permite analizar y diseñar redes de forma estructurada**.
- Es esencial para el análisis de protocolos, diagnósticos de red, formación y documentación técnica.

---
