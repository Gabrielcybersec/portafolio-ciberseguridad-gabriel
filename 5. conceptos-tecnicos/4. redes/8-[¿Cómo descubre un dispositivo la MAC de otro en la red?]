# 📡 [¿Cómo descubre un dispositivo la MAC de otro en la red?]

---

## 🧠 ¿Por qué necesitamos ARP?

Cuando un dispositivo quiere **enviar datos a otro dentro de la misma red local (LAN)**, necesita conocer su dirección MAC. Tener solo la dirección IP **no es suficiente en redes Ethernet o Wi-Fi**.

> 📌 Aunque dos equipos tengan IPs válidas, **sin conocer sus direcciones MAC no pueden comunicarse directamente** en la red local.

---

## 🔍 ¿Qué es ARP?

**ARP (Address Resolution Protocol)** traduce una dirección IP a su correspondiente dirección MAC.

> 🗣️ “Tengo la IP del otro equipo... ¿cuál es su MAC?”

---

## 🔁 ¿Cuándo se usa ARP?

Cada vez que:

- Querés comunicarte con otro dispositivo **en tu misma red local**
- Conocés la **IP** del destino, pero no su **MAC**
- Justo después de recibir una IP por **DHCP**, y necesitás hablar con el router

---

## 🔄 ¿Cómo funciona ARP paso a paso?

### 🧪 Escenario:

- Tu IP: `192.168.66.89`
- Querés comunicarte con el router: `192.168.66.1`

Sabés la IP, pero no su MAC. Entonces...

### Paso 1: **ARP Request**

- Se envía una solicitud tipo **broadcast**:

```plaintext
¿Quién tiene 192.168.66.1? Dime tu MAC
```

```plaintext
De: cc:5e:f8:02:21:a7 → A: ff:ff:ff:ff:ff:ff
```

### Paso 2: **ARP Reply**

- El router responde en **unicast**:

```plaintext
Yo soy 192.168.66.1 y mi MAC es 44:df:65:d8:fe:6c
```

```plaintext
De: 44:df:65:d8:fe:6c → A: cc:5e:f8:02:21:a7
```

---

## 📡 Broadcast vs Unicast en ARP

| Fase        | Tipo de tráfico | ¿A quién se le envía?                  |
|-------------|------------------|----------------------------------------|
| ARP Request | 📣 Broadcast     | A **todos** los dispositivos de la red |
| ARP Reply   | 🎯 Unicast       | Solo al dispositivo que hizo la solicitud |

---

## 🧪 Captura real con herramientas

### 📋 tshark

```bash
user@pc$ tshark -r arp.pcapng -Nn

1 0.000000000 cc:5e:f8:02:21:a7 → ff:ff:ff:ff:ff:ff ARP Who has 192.168.66.1? Tell 192.168.66.89
2 0.003566632 44:df:65:d8:fe:6c → cc:5e:f8:02:21:a7 ARP 192.168.66.1 is at 44:df:65:d8:fe:6c
```

### 📋 tcpdump

```bash
user@pc$ tcpdump -r arp.pcapng -n -v

17:24:11.112348 ARP, Request who-has 192.168.66.101 tell 192.168.66.55
17:24:11.115872 ARP, Reply 192.168.66.101 is-at 7c:df:a1:d3:8c:5c
```

---

## ⚙️ ¿En qué capa del modelo OSI trabaja ARP?

- ARP opera **entre la Capa 2 (enlace)** y la **Capa 3 (red)**.
- Traduciendo IPs (lógicas) a MACs (físicas), **no utiliza TCP, UDP ni IP**.
- Por eso se considera **parte de la Capa 2** (enlace), aunque interactúa con la 3.

> ✅ Los mensajes ARP NO están encapsulados en IP, sino **directamente en tramas Ethernet**.

---

## 🧩 Estructura de una trama Ethernet con ARP

```plaintext
[Trama Ethernet]
- MAC destino: ff:ff:ff:ff:ff:ff (si es Request)
- MAC origen: MAC del solicitante
- EtherType: ARP (0x0806)

[ARP Payload]
- ¿Quién tiene la IP X? Dímelo.
```

---

## ✅ Resumen rápido – Tabla técnica de ARP

| Concepto clave     | Explicación sencilla                                                        |
|--------------------|------------------------------------------------------------------------------|
| ¿Para qué sirve?   | Para saber la MAC de un dispositivo conociendo solo su IP                   |
| ¿Cuándo se usa?    | Cada vez que se quiere comunicar con otra IP en la red local                |
| ¿ARP Request?      | Se envía por **broadcast**                                                  |
| ¿ARP Reply?        | Se responde en **unicast**                                                  |
| ¿Dónde ocurre?     | Solo dentro de la **misma red local (LAN)**                                 |
| ¿En qué capa está? | Entre la 2 y 3, pero **más cerca de la capa 2** (usa MAC, no IP/TCP/UDP)     |

---

## 🎯 Conclusión final

- ARP es **clave para que los dispositivos se comuniquen localmente**.
- Permite traducir IP a MAC, esencial para enviar tramas Ethernet.
- Toda red local funcional usa ARP (excepto si se usa IPv6, que utiliza **NDP**).

