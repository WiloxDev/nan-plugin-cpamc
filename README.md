<p align="center">
  <img src="assets/logo.png" alt="NaN Builders Plugin for CPAMC" width="220" />
</p>

# 🔬 NaN Builders Plugin for CLI PROXY API CONSOLE (CPAMC)

[![Gentle Hub](https://img.shields.io/badge/Gentle%20Hub-Plugin-F095C8?style=for-the-badge)](https://gentlemanprogramming.com/gentle-hub/)
[![Ecosistema](https://img.shields.io/badge/Ecosistema-CPAMC%20%7C%20Gentle--Shell-orange?style=for-the-badge)](#)
[![Discord](https://img.shields.io/badge/Discord-Apoyo-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://bit.ly/48zTJUo)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

Plugin oficial en Go (C-ABI) que integra el catálogo de modelos experimentales y endpoints de la comunidad de **NaN Builders** dentro de **CLI PROXY API CONSOLE (CPAMC)** y el ecosistema **Gentle-Shell**.

Permite acceder a modelos afinados para desarrollo especializado, con soporte nativo para pools de cuentas en **CPAMC Auto Switcher Pro**.

> 💬 **Comunidad y Soporte Oficial:** `wilox2` · [Servidor de Discord](https://bit.ly/48zTJUo)

---

## 🌟 Modelos y Capacidades

- Conexión a endpoints de NaN Builders optimizados para síntesis de código.
- Formateo SSE de alta velocidad con consumo mínimo de recursos.
- Total compatibilidad con los contratos de streaming de Gentle Shell.

---

## 🛠️ Métodos de Instalación

### Método 1: Compilación local con Go
Requiere Go (>= 1.22) y compilador C:
```bash
git clone https://github.com/WiloxDev/nan-plugin-cpamc.git
cd nan-plugin-cpamc
make install
```
El archivo `nan-plugin-linux-amd64.so` se copiará automáticamente en la carpeta de plugins de CPAMC.

---

### Método 2: Despliegue en Docker
Monta el archivo `.so` en el contenedor de CPAMC:
```yaml
services:
  cpamc:
    image: ghcr.io/router-for-me/cliproxyapi:latest
    volumes:
      - ./plugins/nan-plugin-linux-amd64.so:/app/plugins/nan.so:ro
      - ./config.yaml:/app/config.yaml:ro
    ports:
      - "8317:8317"
```

---

## ⚙️ Configuración en CPAMC

### En la Consola Web Oficial
1. Abre: 👉 **[http://127.0.0.1:8317/management.html](http://127.0.0.1:8317/management.html)**
2. Ve a **Plugins / NaN Builders**.
3. Pega tu API Key de acceso.

### En `config.yaml`
```yaml
plugins:
  nan:
    enabled: true
    api_key: "tu-api-key-de-nan-builders"
    base_url: "https://api.nanbuilders.org/v1"
```

---

## 🚀 Uso en Gentle Shell

1. Sincroniza los modelos con `/cpamc refresh`.
2. Escribe `/model` y selecciona tu modelo bajo el prefijo `cpamc/nan-*`.
3. Para operación continua, vincula múltiples cuentas con **[CPAMC Auto Switcher Pro](https://github.com/WiloxDev/cpamc-auto-switcher-pro)**.

---

## 🌐 Ecosistema de la Suite WiloxDev para Gentle Hub

- 🌉 **[bridge-cpamc-oficial](https://github.com/WiloxDev/bridge-cpamc-oficial)** — Puente e instalador oficial multiplataforma de CPAMC.
- ⚡ **[cpamc-auto-switcher-pro](https://github.com/WiloxDev/cpamc-auto-switcher-pro)** — Balanceador de carga y conmutación automática anti-429.
- 🐋 **[deepseek-plugin-cpamc](https://github.com/WiloxDev/deepseek-plugin-cpamc)** — Plugin oficial de DeepSeek V3 y R1.
- 👁️ **[gentle-context-lens](https://github.com/WiloxDev/gentle-context-lens)** — Cabina de contexto, semáforo de tokens y poda quirúrgica.

---

## 📄 Licencia

MIT © Wilox. Desarrollado para la comunidad de Gentle Shell y CLIProxyAPI.
