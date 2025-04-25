# 📍 Dirección IP – Conceptos Fundamentales de Red

---

## 🧠 ¿Qué es una dirección IP?

Una **dirección IP (Internet Protocol Address)** es un identificador lógico único asignado a cada dispositivo conectado a una red. Su función principal es **facilitar la localización y comunicación** entre dispositivos en redes locales o públicas.

📌 Equivale a una **dirección postal**, permitiendo que los paquetes (datos) lleguen al destino correcto.

**Ejemplos válidos de direcciones IPv4:**
- `192.168.0.1`
- `172.16.159.243`

---

## 🧩 Funciones clave

- Identifica de forma única a cada dispositivo (host).
- Permite la **localización lógica** y el **enrutamiento de datos**.
- Facilita la comunicación entre redes mediante routers.

---

## 📚 Estructura de una dirección IPv4

- Compuesta por **4 octetos** de 8 bits (32 bits en total).
- Cada octeto va de `0` a `255`.

```plaintext
Ejemplo: 192.168.1.1
```

---

## 📌 Ejemplo de red IPv4

```plaintext
192.168.1.0     → Dirección de red  
192.168.1.255   → Dirección de broadcast  
192.168.1.1–254 → Direcciones válidas para hosts  
```

---

## 🔐 Tipos de Direcciones IP

### 📦 Direcciones IP Privadas (RFC 1918)

Son utilizadas en redes internas (LAN). No son enrutable directamente a través de Internet.

| Rango IP Privada              | Notación CIDR   | Tamaño       |
|-------------------------------|------------------|--------------|
| `10.0.0.0 – 10.255.255.255`   | `10.0.0.0/8`     | Muy grande   |
| `172.16.0.0 – 172.31.255.255` | `172.16.0.0/12`  | Grande       |
| `192.168.0.0 – 192.168.255.255`| `192.168.0.0/16` | Pequeña      |

✅ *Estas IPs no son accesibles desde Internet directamente.*

---

### 🌐 Direcciones IP Públicas

- Son visibles desde Internet.
- Asignadas por un ISP (Proveedor de Servicios de Internet).
- Usadas por routers, servidores, firewalls y servicios expuestos al exterior.

---

## 🔁 NAT – Network Address Translation

**NAT** permite que múltiples dispositivos con direcciones IP privadas accedan a Internet usando una **única dirección IP pública**.

### ¿Qué hace?

- Traduce direcciones y puertos (IP interna:puerto ↔ IP externa:puerto).
- El router mantiene una tabla para redirigir las respuestas al host correcto.

### 🏢 Analogía para entenderlo

> 🌐 Red = Edificio  
> 🚪 Router = Portero  
> 📦 IP Pública = Entrada principal  
> 🧑‍💻 Dispositivos = Apartamentos  
>  
> Todo entra/sale por la misma puerta, pero el portero sabe quién pidió qué y lo reenvía correctamente.

---

## 🧠 ¿Qué es una máscara de subred?

Una **máscara de subred** determina qué parte de una IP representa la red y cuál representa a los dispositivos (hosts).

**Ejemplo típico:** `255.255.255.0` = `/24`  
Esto significa que **los primeros 24 bits son la parte de red**.

```plaintext
192.168.66.0     → Dirección de red  
192.168.66.255   → Broadcast  
192.168.66.1–254 → Direcciones válidas para dispositivos
```

---

## 📡 Dirección Broadcast

Es una **IP especial** usada para enviar mensajes a **todos los dispositivos en una red**.

- En una red `/24`, sería: `192.168.1.255`

---

## ✈️ ¿Qué es un Router?

Es un dispositivo que opera en la **Capa 3 (Red)** del modelo OSI.  
Su función principal es reenviar paquetes hacia otras redes.

### Funciones:

- Lee la dirección IP de destino.
- Consulta su tabla de enrutamiento.
- Redirige el paquete hacia la mejor ruta.
- Interconecta redes LAN, WAN o Internet.

---

## 💻 Ver tu IP y configuración de red en terminal

### 📍 En Windows:
```bash
ipconfig
```

### 📍 En Linux / UNIX:
```bash
ifconfig
```

### 📍 Alternativa moderna (Linux):
```bash
ip a s
```

📋 Estos comandos muestran:

- Dirección IP asignada
- Máscara de subred
- Dirección MAC
- Dirección de broadcast

---

## ✅ Resumen visual

| Concepto          | Explicación breve                                                        |
|-------------------|---------------------------------------------------------------------------|
| Dirección IP      | Identificador único de cada dispositivo en la red                        |
| IP Privada        | No visible desde Internet, solo para redes internas                      |
| IP Pública        | Asignada por el ISP, visible desde Internet                              |
| Máscara de subred | Divide una IP entre parte de red y parte de host                         |
| Broadcast         | Dirección usada para enviar mensajes a todos los dispositivos            |
| Router            | Encaminador de paquetes entre diferentes redes                           |
| NAT               | Traduce IPs privadas a públicas para acceder a Internet                  |
| ifconfig / ip a s | Comandos CLI para obtener configuración de red en Linux y Windows        |

---
