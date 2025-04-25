# 🌐 [ICMP – Diagnóstico y Comunicación para Redes]

**Internet Control Message Protocol**

---

## 🧠 ¿Qué es ICMP?

**ICMP** es un protocolo de soporte de la **Capa 3 (Red)** que se encapsula directamente dentro de un paquete IP. No se utiliza para transmitir datos como TCP o UDP, sino que sirve para:

- 📈 Diagnóstico de red (latencia, pérdida)
- 🚫 Reporte de errores (host inalcanzable, TTL agotado)
- 🔍 Trazado de rutas (descubrimiento de saltos)

> ⚠️ ICMP **no utiliza puertos** → no es TCP ni UDP.

---

## 🛠️ Herramientas comunes que usan ICMP

| Comando       | ¿Para qué sirve?                                                             |
|---------------|------------------------------------------------------------------------------|
| `ping`        | Verifica si un host está activo (usa ICMP tipo 8 y tipo 0)                   |
| `traceroute`  | Muestra todos los routers (saltos) entre tu dispositivo y el destino final   |

---

## 🏓 `ping` – Verificar conectividad

### 🔄 ¿Cómo funciona?

1. Se envía un **ICMP Echo Request** (Tipo 8)
2. Se espera un **ICMP Echo Reply** (Tipo 0)

📊 Esto permite:

- Confirmar si un host está **activo**
- Medir tiempo de respuesta (RTT)
- Detectar pérdida de paquetes

### 📦 Ejemplo de uso:

```bash
ping 192.168.11.1 -c 4
```

📥 Cada respuesta incluye: tamaño, secuencia (`icmp_seq`), TTL y RTT (`time=ms`)

📊 Al final, se muestra: pérdida, RTT mínimo/promedio/máximo/desviación

---

## 🛰️ `traceroute` – ¿Qué ruta toma un paquete?

### 🧭 ¿Cómo funciona?

- Utiliza el campo **TTL** del encabezado IP
- Envía múltiples paquetes con TTL creciente
- Cada router que reduce el TTL a 0 responde con **ICMP Type 11 (Time Exceeded)**

📦 Se repite este proceso hasta llegar al destino (ICMP Tipo 0)

### 📋 Ejemplo de salida:

```plaintext
traceroute to example.com (93.184.216.34), 30 hops max
 1  192.168.1.1      2.14 ms
 2  10.0.0.1         5.23 ms
 3  * * *            (sin respuesta)
 4  172.16.0.1       9.20 ms
```

### ✨ ¿Qué significan los `* * *`?

- El salto **no respondió**
- Puede deberse a:
  - 🔥 Firewall que bloquea ICMP
  - 🚫 Router configurado para ignorar ICMP
  - 🕒 Timeout de red

> `* * *` = salto oculto o no accesible

---

## 🔑 Tipos de mensajes ICMP más usados

| Tipo | Descripción            | Usado por        | Función                                                |
|------|------------------------|------------------|--------------------------------------------------------|
| 8    | Echo Request           | `ping`           | Prueba inicial para verificar conectividad             |
| 0    | Echo Reply             | `ping`           | Confirmación de recepción                              |
| 11   | Time Exceeded          | `traceroute`     | TTL llegó a 0, el router se identifica                 |
| 3    | Destination Unreachable| General          | Indica que el destino no está disponible               |
| 5    | Redirect               | Routers          | Informa sobre una mejor ruta al destino (raro hoy día) |
| 4    | Source Quench          | Obsoleto         | Obsoleto: usado para indicar congestión                |

---

## ❓ ¿ICMP usa puertos?

**No.** ICMP no opera en la capa de transporte, por lo tanto:

- No usa puertos
- Se encapsula **directamente en IP**
- Usa solo **tipos** y **códigos**

---

## ✅ Resumen Final – Tabla Técnica

| Concepto                 | Explicación                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **ICMP**                 | Protocolo de diagnóstico/red, encapsulado en IP                            |
| **ping**                 | Verifica conectividad (usa ICMP tipos `8` y `0`)                            |
| **traceroute**           | Muestra ruta completa (usa TTL + ICMP tipo `11`)                            |
| `* * *` en traceroute    | Indica salto sin respuesta (firewall o router silenciado)                   |
| **No usa TCP/UDP**       | ICMP va directo dentro de IP, sin puertos                                   |
| **Tipos clave ICMP**     | `8` Request, `0` Reply, `11` TTL Exceeded, `3` Destination Unreachable       |

---

> 🧠 **Conclusión:**  
> ICMP es esencial para el diagnóstico de redes, permitiendo identificar conectividad, rutas, y problemas de entrega. Aunque simple, es poderoso para cualquier analista de red o pentester.
