# 📍 [DHCP: Cómo tu dispositivo obtiene su IP automáticamente]

---

## 🧠 ¿Qué es DHCP?

**DHCP (Dynamic Host Configuration Protocol)** es un protocolo de red que permite a los dispositivos obtener **automáticamente su configuración IP** al conectarse a una red. 

> Es el protocolo que permite que simplemente te conectés al Wi-Fi y navegues sin configurar nada manualmente.

---

## ⚙️ ¿Qué configura DHCP?

El servidor DHCP asigna automáticamente:

- 📍 **Dirección IP**
- 🎯 **Máscara de subred**
- 🚪 **Puerta de enlace (gateway)**
- 🌐 **Servidores DNS**

---

## 🔁 ¿Cómo funciona DHCP? – Ciclo DORA

El proceso se compone de 4 pasos llamados **DORA**:

| Etapa     | Mensaje DHCP   | Descripción                                                                 |
|-----------|----------------|-----------------------------------------------------------------------------|
| 📡 Discover | DHCPDISCOVER   | El cliente busca servidores DHCP (Broadcast IP y MAC)                     |
| 📨 Offer    | DHCPOFFER      | El servidor ofrece una IP al cliente (Unicast o Broadcast)                |
| 🙋 Request  | DHCPREQUEST    | El cliente solicita formalmente esa IP (Broadcast)                        |
| ✅ ACK      | DHCPACK        | El servidor confirma la asignación (Unicast o Broadcast)                  |

---

## 🧪 Ejemplo en la vida real

1. El cliente **envía un broadcast**: `¿Hay un servidor DHCP disponible?`
2. El servidor responde: `Podés usar la IP 192.168.1.50`
3. El cliente acepta: `Quiero esa IP`
4. El servidor confirma: `Listo, IP asignada`

---

## 🔍 ¿Broadcast o Unicast?

| Tipo de tráfico | ¿Qué significa?                         | ¿Cuándo se usa en DHCP?               |
|-----------------|------------------------------------------|---------------------------------------|
| 📣 Broadcast     | Mensaje a todos los dispositivos         | Discover, Request, a veces ACK        |
| 🎯 Unicast       | Directamente al cliente específico       | Offer (normalmente), a veces ACK      |

✅ **3 mensajes son Broadcast:** Discover, Request, ACK  
✅ **1 mensaje suele ser Unicast:** Offer

> ⚠️ El cliente no tiene IP al inicio, por eso se usa `0.0.0.0 → 255.255.255.255`.

---

## 🖥️ Captura real de red (tshark)

```bash
user@pc$ tshark -r captura-dhcp.pcap -n

1   0.000000 0.0.0.0 → 255.255.255.255 DHCP Discover
2   0.013904 192.168.1.1 → 192.168.1.50 DHCP Offer
3   1.001123 0.0.0.0 → 255.255.255.255 DHCP Request
4   1.105512 192.168.1.1 → 192.168.1.50 DHCP ACK
```

---

## 📚 Funcionamiento del Cliente DHCP – Desde cero hasta conocer la MAC

### ¿Qué sabe el cliente al iniciar?

❌ No conoce su IP  
❌ No conoce la IP o MAC del servidor DHCP  
❌ No conoce la IP o MAC del router  

✅ Solo conoce **su propia MAC**

---

### Fases DORA detalladas (MAC & IP)

| Fase       | IP Origen | IP Destino         | MAC Origen        | MAC Destino         | ¿Conoce MACs? |
|------------|-----------|---------------------|-------------------|---------------------|----------------|
| Discover   | 0.0.0.0   | 255.255.255.255     | MAC del cliente   | ff:ff:ff:ff:ff:ff   | ❌ No          |
| Offer      | IP del DHCP | 255.255.255.255   | MAC del servidor  | MAC del cliente     | ❌ Aún no      |
| Request    | 0.0.0.0   | 255.255.255.255     | MAC del cliente   | ff:ff:ff:ff:ff:ff   | ❌ No          |
| ACK        | IP del DHCP | IP del cliente     | MAC del servidor  | MAC del cliente     | ✅ Sí          |

---

## ⚡ ¿Cuándo aprende el cliente la MAC del router?

🟢 Después de recibir el **DHCP ACK**, el cliente ya conoce su IP, máscara y gateway.  
Entonces realiza una consulta **ARP**:

> 🗣️ “¿Quién tiene la IP 192.168.1.1 (gateway)?”

🛠️ El router responde:

> 🎯 “Yo soy 192.168.1.1 y esta es mi MAC: `aa:bb:cc:dd:ee:ff`”

Ahora puede comunicarse a nivel de **Capa 2** (enlace).

---

## 📌 Resumen final simplificado

| Concepto                 | Explicación                                  |
|--------------------------|-----------------------------------------------|
| IP inicial del cliente   | `0.0.0.0`                                     |
| MAC conocida al inicio   | Solo la del cliente                          |
| Uso de Broadcast         | En Discover y Request                        |
| Aprende la MAC del router| Después del ACK, mediante ARP                |
| Resultado                | Comunicación establecida en capa 2 y 3       |

---

## 🎯 ¿Qué obtiene tu dispositivo al finalizar?

✅ Dirección IP (ej: `192.168.1.50`)  
✅ Máscara de subred (ej: `255.255.255.0`)  
✅ Gateway (ej: `192.168.1.1`)  
✅ DNS (ej: `8.8.8.8`)  
✅ MAC del router (por ARP)  
✅ Conectividad total a nivel de red

---

### 🔥 Conclusión clara:

> 🧠 El cliente DHCP **NO obtiene oficialmente su IP** hasta completar el ciclo DORA y recibir el **DHCP ACK**.  
> Luego, usa **ARP para conocer la MAC del gateway** y poder comunicarse dentro de la red.

