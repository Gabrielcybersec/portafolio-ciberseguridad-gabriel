# 📚 Modelo OSI (Open Systems Interconnection)

> **Desarrollado por**: ISO (Organización Internacional de Normalización)  
> **Propósito**: Establecer un modelo de referencia teórico que permita comprender, diseñar y estandarizar la comunicación entre sistemas de red.

---

## 🧠 ¿Qué es el Modelo OSI?

El modelo OSI es un marco de referencia dividido en **siete capas**, cada una con funciones específicas en el proceso de comunicación de datos. Permite entender **cómo viaja la información desde una aplicación en un equipo hasta otra aplicación remota**, pasando por distintos niveles de procesamiento.

---

## 🧩 Capas del Modelo OSI

### Capa 7 – Aplicación
- Proporciona servicios e interfaces a las aplicaciones de usuario final.
- Ejemplos: HTTP, FTP, DNS, POP3, SMTP, IMAP.

---

### Capa 6 – Presentación
- Codifica, cifra y comprime los datos para que sean entendibles por la capa de aplicación.
- Ejemplos: JPEG, PNG, MPEG, Unicode.

---

### Capa 5 – Sesión
- Establece, gestiona y finaliza sesiones de comunicación entre aplicaciones.
- Garantiza el orden correcto de los datos.
- Ejemplos: NFS, RPC.

---

### Capa 4 – Transporte
- Realiza la segmentación de datos y gestiona su transporte extremo a extremo.
- Asegura confiabilidad (TCP) o velocidad (UDP).
- Funciones clave:
  - Segmentación
  - Recuperación de errores
  - Control de flujo
- Protocolos: TCP, UDP

---

### Capa 3 – Red
- Encargada del direccionamiento lógico (IP) y enrutamiento entre redes.
- Decide la mejor ruta para que los datos lleguen a su destino.
- Protocolos: IP, ICMP, IPSec.

---

### Capa 2 – Enlace de Datos
- Establece comunicación entre nodos adyacentes.
- Control de acceso al medio (evita colisiones).
- Asigna dirección MAC a cada interfaz de red.
- Detecta errores de transmisión.
- Protocolos: Ethernet (802.3), Wi-Fi (802.11)

---

### Capa 1 – Física
- Transmite bits a través del medio físico (cableado, inalámbrico, óptico).
- Define el tipo de señal según el medio (eléctrico, óptico, electromagnético).
- Aplica multiplexación (TDM, FDM, WDM).
- Es base del proceso de convergencia (voz, datos, video por el mismo canal).
- Ejemplos: voltaje en cables, pulsos de luz en fibra óptica, ondas de radio (Wi-Fi, AM/FM).

---

## 🧾 Tabla Resumen

| Capa | Nombre | Función Principal | Protocolos/Normas |
|------|--------|-------------------|-------------------|
| 7 | Aplicación | Servicios a usuario | HTTP, FTP, SMTP |
| 6 | Presentación | Codificación y cifrado | JPEG, PNG, MPEG |
| 5 | Sesión | Gestión de sesiones | RPC, NFS |
| 4 | Transporte | Comunicación extremo a extremo | TCP, UDP |
| 3 | Red | Enrutamiento lógico | IP, ICMP, IPSec |
| 2 | Enlace de Datos | Transferencia entre nodos | Ethernet, Wi-Fi |
| 1 | Física | Transmisión física | Señales eléctricas, ópticas |

---

## ✅ Aplicaciones del Modelo OSI

- Diagnóstico de red (¿en qué capa está el problema?).
- Diseño de infraestructuras de red.
- Seguridad por capas.
- Compatibilidad entre fabricantes.
- Estudio de protocolos específicos.

---

## 📌 Notas

- **La modularidad** del modelo permite estudiar cada función de red de forma aislada y precisa.
- Aunque en la práctica se utiliza más el **modelo TCP/IP**, OSI sigue siendo una herramienta educativa fundamental.

---
