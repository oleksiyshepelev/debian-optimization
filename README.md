# 🚀 Debian 12 Server Optimization Script

¡Bienvenido! Este repositorio incluye un **script Bash** para optimizar tu servidor Debian 12, dejándolo ligero, rápido y fácil de mantener.

---

## 📋 Tabla de Contenidos

- [✨ Características](#-características)
- [⚙️ Requisitos](#️-requisitos)
- [🚀 Instalación y Uso](#-instalación-y-uso)
- [🔄 Funcionalidades](#-funcionalidades)
- [📂 Estructura del Proyecto](#-estructura-del-proyecto)
- [🛡️ Seguridad y Respaldo](#️-seguridad-y-respaldo)
- [📝 Licencia](#-licencia)

---

## ✨ Características

- 🎁 **Backup automático** de configuraciones críticas
- 🔧 **Deshabilitación interactiva** de servicios innecesarios
- 🔄 **Actualizaciones automáticas** con `unattended-upgrades`
- 🏎️ **Gobernador CPU** en modo `performance`
- ⚙️ **Ajustes **`` para red y memoria
- ⏰ **Sincronización horaria** rápida con `chrony`
- 🔄 **Rollback fácil** al estado previo

---

## ⚙️ Requisitos

- Debian 12 o derivado (Ubuntu 22.04+ compatible)
- Acceso root o usuario con `sudo`
- Conexión a Internet para paquetes APT

---

## 🚀 Instalación y Uso

1. **Clona este repositorio**

   ```bash
   git clone https://github.com/tu-usuario/debian-optimize.git
   cd debian-optimize
   ```

2. **Haz ejecutable el script**

   ```bash
   chmod +x optimize-debian.sh
   ```

3. **Opciones**

   - 🔒 `backup`  → Solo crea un respaldo de configuraciones
   - ⚙️  `apply`   → Ejecuta backup + optimizaciones (interactivo)
   - ⏮️ `rollback`→ Restaura desde el último backup

   ```bash
   # Crea backup
   sudo ./optimize-debian.sh backup

   # Aplica optimizaciones
   sudo ./optimize-debian.sh apply

   # Restaura backup
   sudo ./optimize-debian.sh rollback
   ```

---

## 🔄 Funcionalidades Detalladas

| Paso                          | Descripción                                                                |
| ----------------------------- | -------------------------------------------------------------------------- |
| 📦 **Backup**                 | Copia de `/etc/sysctl.d`, `/etc/default/cpufrequtils`, `/etc/chrony`, etc. |
| 🛑 **Servicios interactivos** | Te muestra lista de servicios habilitados y te permite deshabilitarlos.    |
| ⚙️ **Auto-upgrades**          | Instala y configura `unattended-upgrades` y `apt-listchanges`.             |
| 🏎️ **CPU Governor**          | Instala `cpufrequtils` y fija governor en `performance`.                   |
| 🔧 **Ajustes sysctl**         | Aplica `vm.swappiness`, `net.core.somaxconn`, `vfs_cache_pressure`, etc.   |
| ⏰ **Chrony**                  | Sustituye `systemd-timesyncd` por `chrony` para tiempo preciso y rápido.   |
| 🔄 **Rollback**               | Restaura configuraciones y habilita servicios previos.                     |

---

## 📂 Estructura del Proyecto

```plain
debian-optimize/
├── optimize-debian.sh   # Script principal
└── README.md            # Este documento
```

---

## 🛡️ Seguridad y Respaldo

- 🔐 **Permisos root**: el script debe ejecutarse como root para modificar servicios y configs.
- 📂 **Backups**: se guardan en `/root/optimize-backup-YYYYMMDD-HHMMSS/`.
- 🔄 **Rollback**: un solo comando restaura todo.

---

## 📝 Licencia

Este proyecto está bajo la [MIT License](https://opensource.org/licenses/MIT). ¡Siéntete libre de usar y modificar a tu gusto!


