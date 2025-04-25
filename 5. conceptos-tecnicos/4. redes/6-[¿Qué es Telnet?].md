# 📟 ¿Qué es Telnet?

---

**Telnet** (Teletype Network) es un **protocolo de red de la capa de aplicación (capa 7 del modelo OSI)** que permite establecer una conexión remota a otro sistema mediante una consola de texto.

> 🔧 Su propósito principal es administrar dispositivos, servicios o sistemas de forma remota como si estuvieras operándolos directamente desde su terminal.

---

## 🧱 Características clave

- 📡 **Protocolo de transporte:** TCP
- 🔌 **Puerto predeterminado:** 23 (aunque puede usarse con otros)
- ❌ **Comunicación sin cifrado:** los datos, incluidas las contraseñas, se envían en texto plano
- 🔐 **Obsoleto para administración real:** reemplazado por SSH (Secure Shell) en entornos modernos

---

## 🛠️ ¿Para qué sirve Telnet hoy?

Aunque ya no es recomendable para administración remota, **sigue siendo útil para pruebas de conectividad TCP**, como:

- Verificar si un servicio responde en un puerto específico
- Conectarse a servicios de diagnóstico:
  - **Puerto 7:** Echo (repite lo que se envía)
  - **Puerto 13:** Daytime (retorna fecha y hora)
  - **Puerto 80:** HTTP (pruebas manuales de web)

---

## 🧪 Ejemplos de uso práctico

### 1️⃣ Conexión a un **Servidor Echo** (puerto 7)

```bash
telnet 192.168.1.100 7
```

**Resultado esperado:**

```plaintext
Hi
Hi
Test
Test
```

**Salir:**  
Presionar `Ctrl + ]` → luego escribir `quit` → presionar Enter.

---

### 2️⃣ Conexión a un **Servidor Daytime** (puerto 13)

```bash
telnet 192.168.1.100 13
```

**Resultado esperado:**

```plaintext
Thu Apr 25 15:03:10 UTC 2025
```

La conexión se cierra automáticamente tras responder.

---

### 3️⃣ Solicitud manual a un **servidor web HTTP** (puerto 80)

```bash
telnet 192.168.1.100 80
```

Escribir el siguiente comando al conectarse:

```http
GET / HTTP/1.1
Host: example.com
```

✅ Presionar **Enter dos veces**  
📄 Resultado: se mostrará el encabezado HTTP y el contenido de la página en texto plano.

---

## 🚫 Consideraciones de seguridad

- ❗ **Telnet transmite todo sin cifrado**, incluidas contraseñas y datos sensibles.
- ❗ **No debe utilizarse en redes productivas o públicas.**

🔐 **SSH (Secure Shell)** es el protocolo recomendado para conexiones remotas seguras.

---

## ✅ Conclusión

| Aspecto               | Telnet                                     |
|------------------------|--------------------------------------------|
| Propósito original     | Administración remota por terminal         |
| Seguridad              | ❌ Inseguro – sin cifrado                   |
| Reemplazado por        | ✅ SSH (Secure Shell)                       |
| Uso actual             | Laboratorios, pruebas TCP, debugging       |
| Puerto predeterminado  | 23                                         |

> 💡 Aunque obsoleto para producción, **Telnet sigue siendo valioso como herramienta de diagnóstico en redes**.

