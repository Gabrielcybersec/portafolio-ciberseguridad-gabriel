# 📦 Encapsulación y la Vida de un Paquete

---

## 🧠 ¿Qué es la encapsulación?

La **encapsulación** es el proceso en el que **cada capa del modelo OSI o TCP/IP** añade su propia información de control (encabezados y, en algunos casos, remolques) a los datos que recibe de la capa superior.

> ✉️ **Analogía:**  
> Es como enviar una carta:  
> Ponés la hoja en un sobre → dentro de una caja → dentro de un camión.  
> Cada envoltura agrega información para que llegue correctamente a su destino.

---

## 🔁 Encapsulación por capas (de arriba hacia abajo)

| Capa OSI          | Unidad de datos         | Información añadida                              |
|-------------------|--------------------------|--------------------------------------------------|
| Aplicación        | **Datos**                | Solicitud del usuario (ej. HTTP, DNS, etc.)      |
| Transporte        | **Segmento / Datagrama** | Encabezado TCP/UDP (puertos, secuencias, flags) |
| Red               | **Paquete IP**           | Encabezado IP (dirección origen/destino, TTL)   |
| Enlace de Datos   | **Trama**                | Encabezado y tráiler MAC (dirección MAC, FCS)   |
| Física            | **Bits**                 | Transmisión como pulsos eléctricos, luz o radio |

---

## 🌍 Ejemplo práctico: Acceder a `example.com`

Supongamos que ingresás `example.com` en tu navegador. Aquí está el recorrido de los datos (la vida del paquete):

### 1. 🧑‍💻 Capa de Aplicación

- El navegador genera una solicitud HTTP o HTTPS
- La pasa a la capa de transporte

### 2. 🔐 Capa de Transporte (TCP)

- Se establece una conexión mediante el **Three-Way Handshake**
- Se encapsula la solicitud en un **segmento TCP**
- Se agregan:
  - Puerto de origen (ej. 49152)
  - Puerto de destino (ej. 80 o 443)

### 3. 🛰️ Capa de Red (IP)

- Se agrega un **encabezado IP** con:
  - IP origen: `192.168.1.5`
  - IP destino: `93.184.216.34` (servidor de example.com)
- Se forma un **paquete IP**

### 4. 🔗 Capa de Enlace (Ethernet / WiFi)

- Se encapsula en una **trama**:
  - Dirección MAC de origen y destino
  - Tráiler con FCS (código de verificación)
- Lista para transmitirse por el medio físico

---

## 📡 Transmisión y enrutamiento

- La **trama** viaja hasta el router
- El router elimina los datos de enlace, inspecciona el **paquete IP**
- Reenvía el paquete al siguiente salto (otro router o ISP)
- Este proceso se repite hasta llegar al servidor de destino

---

## 🧾 En el servidor (example.com)

- El servidor **desencapsula** los datos en orden inverso:
  ```plaintext
  Trama → Paquete IP → Segmento TCP → Datos HTTP
  ```
- El servidor responde con una página web u otra respuesta
- El proceso se repite ahora **desde el servidor hacia vos**

---

## ✅ Conclusiones clave

- Cada capa cumple funciones específicas y encapsula sus datos
- La encapsulación permite modularidad, diagnóstico, control de errores y entrega eficiente
- La "vida de un paquete" es todo el ciclo que vive la información: desde que sale de tu dispositivo hasta que llega al servidor (y viceversa)

📘 Este flujo es la base de todo lo que ocurre en redes modernas y es esencial para comprender seguridad, rendimiento y funcionamiento de protocolos.

