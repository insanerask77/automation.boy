# 🐳 Guía Completa: Cómo Instalar Docker en Windows, macOS y Linux

Docker es una plataforma que permite crear, desplegar y ejecutar aplicaciones dentro de contenedores. A continuación, te muestro cómo instalar Docker en los tres sistemas operativos principales.

---

## 🪟 Windows

### Requisitos

- Windows 10/11 Pro, Enterprise o Education (con WSL2)
- Habilitar la virtualización en la BIOS

### Pasos

1. **Descargar Docker Desktop**  
   👉 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

2. **Instalar el ejecutable**

   - Ejecuta el `.exe` descargado.
   - Sigue las instrucciones del instalador.

3. **Habilitar WSL2 si es necesario**
   Docker Desktop solicitará habilitarlo si no lo tienes.

4. **Verifica instalación**
   Abre PowerShell y ejecuta:

   ```sh
   docker --version
   ```

---

## 🍎 macOS

### Requisitos

- macOS 11+ (Big Sur o superior)
- Procesador Intel o Apple Silicon (M1/M2)

### Pasos

1. **Descargar Docker Desktop para Mac**  
   👉 [https://www.docker.com/products/docker-desktop/](https://www.docker.com/products/docker-desktop/)

2. **Instalar el archivo `.dmg`**

   - Monta el archivo y arrastra Docker a la carpeta de aplicaciones.

3. **Abrir Docker**

   - Inicia Docker Desktop desde Aplicaciones.

4. **Verifica instalación**
   Abre la terminal y ejecuta:

   ```sh
   docker --version
   ```

---

## 🐧 Linux

### Requisitos

- Distribución basada en Debian, Ubuntu, Fedora, etc.

### Ubuntu / Debian

```sh
sudo apt update
sudo apt install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | \
    sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) \
  signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io
```

Verifica:

```sh
docker --version
```

Agrega tu usuario al grupo docker (opcional):

```sh
sudo usermod -aG docker $USER
```

Cierra sesión y vuelve a entrar.

---

## ✅ Verificar que Docker funciona

Ejecuta:

```sh
docker run hello-world
```

Si todo está bien, verás un mensaje de éxito indicando que Docker se instaló correctamente.

---

## 🧠 Recursos Útiles

- Documentación oficial: [https://docs.docker.com/](https://docs.docker.com/)
- Guía de instalación por sistema:  
  [Windows](https://docs.docker.com/desktop/install/windows/) |  
  [macOS](https://docs.docker.com/desktop/install/mac/) |  
  [Linux](https://docs.docker.com/engine/install/)

---
