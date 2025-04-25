# 📘 Modelo OSI (Open Systems Interconnection)

**Creado por:** ISO (Organización Internacional de Normalización)  
**Propósito:** Ayudar a entender cómo se comunican los dispositivos en una red, dividiendo el proceso en **7 capas**.

---

## 🧠 ¿Qué es el Modelo OSI?

El Modelo OSI es una guía teórica que **explica cómo viajan los datos desde un programa en un dispositivo hasta otro programa en otro dispositivo** a través de una red.

📦 Cada **capa** del modelo tiene **una función específica** y trabaja en conjunto con las otras para lograr la comunicación completa.

---

# 🌐 Las 7 Capas del Modelo OSI

---

## 🟣 Capa 7 – Aplicación

📌 **Qué hace:**  
Es la capa más cercana al usuario. Permite que los programas (como navegadores o correos electrónicos) se comuniquen con la red.

🛠️ **Ejemplos:**  
HTTP, FTP, DNS, SMTP, IMAP, Telnet

---

## 🟣 Capa 6 – Presentación

📌 **Qué hace:**  
Traduce los datos para que el programa los entienda. Aquí se codifica, comprime y cifra la información si es necesario.

🛠️ **Ejemplos:**  
JPEG, MP3, PNG, MPEG, TLS/SSL, ASCII, Unicode

---

## 🟣 Capa 5 – Sesión

📌 **Qué hace:**  
Establece, mantiene y termina conexiones entre aplicaciones. También se encarga de que los datos lleguen en orden y sin errores.

🛠️ **Ejemplos:**  
NFS, RPC, NetBIOS

---

## 🟣 Capa 4 – Transporte

📌 **Qué hace:**  
Garantiza que los datos lleguen completos, ordenados y sin duplicarse. Divide los datos en partes pequeñas llamadas **segmentos**.

✈️ Usa dos protocolos principales:
- **TCP:** Confiable, lento, garantiza entrega
- **UDP:** Rápido, sin confirmación

🛠️ **Ejemplos:**  
TCP, UDP

---

## 🟣 Capa 3 – Red

📌 **Qué hace:**  
Determina la ruta que deben tomar los datos para llegar al destino. Se encarga de asignar direcciones IP.

🛠️ **Ejemplos:**  
IP (IPv4, IPv6), ICMP (ping), IPSec

---

## 🟣 Capa 2 – Enlace de Datos

📌 **Qué hace:**  
Gestiona la comunicación entre dispositivos que están en la misma red (LAN). Agrega la dirección MAC para que el dispositivo sepa a quién enviar los datos localmente.

🛠️ **Ejemplos:**  
Ethernet (802.3), Wi-Fi (802.11), ARP

📌 Subcapas:
- **LLC (Logical Link Control)**
- **MAC (Media Access Control)**

---

## ⚫ Capa 1 – Física

📌 **Qué hace:**  
Transmite los datos en forma de señales (eléctricas, ópticas o de radio). Define los cables, conectores y voltajes.

🛠️ **Ejemplos:**  
UTP (cable de red), fibra óptica, ondas de Wi-Fi, Bluetooth

---

## 🧪 Analogía rápida

Imaginá enviar una carta:

1. Aplicación – Escribís la carta (mensaje)
2. Presentación – La traducís a otro idioma
3. Sesión – Abrís un canal de comunicación
4. Transporte – Cortás la carta en sobres ordenados
5. Red – Decidís la ruta por donde se enviará
6. Enlace – Pones etiquetas y direcciones locales
7. Física – El cartero la lleva por la calle (cable, aire…)

---

## 📋 Tabla Resumen

| Capa | Nombre             | Función principal                                       | Ejemplos de protocolos             |
|------|--------------------|---------------------------------------------------------|------------------------------------|
| 7    | Aplicación         | Interfaz directa con el usuario                        | HTTP, FTP, DNS                     |
| 6    | Presentación       | Formato, codificación, cifrado                         | JPEG, SSL, MPEG                    |
| 5    | Sesión             | Gestión de sesiones                                    | NetBIOS, RPC                       |
| 4    | Transporte         | Entrega confiable o rápida de datos                    | TCP, UDP                           |
| 3    | Red                | Enrutamiento y direccionamiento IP                     | IP, ICMP, IPSec                    |
| 2    | Enlace de Datos    | Entrega entre nodos en la misma red                    | Ethernet, Wi-Fi, ARP               |
| 1    | Física             | Transmisión de bits como señales                       | Cables, radiofrecuencia, luz       |

---

## 🎓 ¿Por qué es importante aprender el modelo OSI?

- Te permite **entender los problemas de red** (¿falló el cable, el IP, el navegador?).
- Ayuda a **diseñar, mantener y solucionar redes**.
- Es base para **certificaciones como CCNA, CEH, CompTIA**, etc.

---

> ✅ Conocer el Modelo OSI te convierte en un mejor técnico, administrador o especialista en redes.

