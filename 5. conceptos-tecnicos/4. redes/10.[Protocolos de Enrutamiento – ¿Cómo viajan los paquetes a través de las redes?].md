# 📦 Protocolos de Enrutamiento – ¿Cómo viajan los paquetes a través de las redes?

---

## 🧠 ¿Por qué necesitamos enrutamiento?

Imaginá esto: tenés tres redes conectadas a Internet, pero **no hay ninguna indicación clara de cómo llegar desde la Red 1 a la Red 2 o la Red 3**.

Cada red tiene su propio router conectado a Internet, pero... ¿cómo saben **qué camino seguir** los paquetes?

> 🔁 Para eso existen los protocolos de enrutamiento: algoritmos que permiten a los routers descubrir rutas óptimas entre redes.

---

## 🧭 El reto de Internet

🌐 Internet es una **red de redes**, compuesta por:

- 🛣️ **Millones de routers**
- 💻 **Miles de millones de dispositivos**
- ⚡ **Múltiples caminos posibles** entre un origen y un destino

👉 Cada router necesita saber **a qué vecino enviar el paquete** para acercarlo a su destino. Para eso, necesita protocolos que compartan información, analicen rutas y reaccionen a cambios.

---

## 🚦 ¿Qué hacen los protocolos de enrutamiento?

- 📤 Intercambian información entre routers
- 🗺️ Construyen un "mapa" de la red
- 🧠 Calculan rutas óptimas
- 🔁 Se actualizan si hay cambios en la topología

---

## 📚 Protocolos de Enrutamiento más importantes

### 🟢 OSPF – Open Shortest Path First

- Tipo: Interior, basado en estado de enlace
- Uso: Corporativo, grandes empresas, ISPs
- Funciona con el algoritmo Dijkstra
- Cada router comparte su información de enlaces → todos construyen un mapa completo

✅ Rápido y confiable  
🔒 Soporta áreas jerárquicas

---

### 🔵 EIGRP – Enhanced Interior Gateway Routing Protocol

- Tipo: Interior, híbrido (propietario de Cisco)
- Uso: Redes Cisco medianas o grandes
- Utiliza métricas como ancho de banda, delay, confiabilidad
- Combina lo mejor de vector de distancia y estado de enlace

✅ Muy estable  
❗ Solo en routers Cisco

---

### 🔴 BGP – Border Gateway Protocol

- Tipo: Exterior, basado en políticas
- Uso: Internet global (entre ISPs, empresas, gobiernos)
- No busca la ruta más corta, sino la **más adecuada según política**

✅ Es el protocolo de enrutamiento principal de Internet  
⚠️ Requiere configuración avanzada y conocimiento de políticas

---

### 🟡 RIP – Routing Information Protocol

- Tipo: Interior, vector de distancia
- Uso: Redes pequeñas o educativas
- Funciona por conteo de saltos (máx 15)

✅ Fácil de configurar  
❌ Limitado, lento para reaccionar a cambios

---

## 🧬 Ejemplo visual de enrutamiento

📱 Un usuario móvil quiere visitar un sitio web:

1. Existen varias rutas posibles para llegar al servidor web.
2. Cada router en el camino evalúa su tabla de enrutamiento.
3. El protocolo (OSPF, BGP, etc.) decide cuál es la mejor ruta.
4. Si un router intermedio falla, el protocolo recalcula y redirecciona.

---

## 📊 Conclusión clara

| Protocolo | Tipo     | Función Principal                                 | Ideal para...                  |
|-----------|----------|---------------------------------------------------|--------------------------------|
| **OSPF**  | Interior | Ruta más corta basada en topología               | Grandes redes empresariales    |
| **EIGRP** | Interior | Métricas avanzadas *(ancho de banda, delay)*     | Redes Cisco optimizadas        |
| **BGP**   | Exterior | Rutas entre redes diferentes *(ISPs)*            | Internet global                |
| **RIP**   | Interior | Rutas simples por cantidad de saltos             | Redes pequeñas o educativas    |

---

✅ Esta guía te permite comprender el rol de cada protocolo de enrutamiento y su aplicación ideal según el entorno de red.
