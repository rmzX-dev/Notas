### **Gestión de Redes WiFi**
| Comando                                                  | Descripción                            |
| -------------------------------------------------------- | -------------------------------------- |
| `nmcli device wifi list`                                 | Listar redes WiFi disponibles          |
| `nmcli device wifi connect <SSID> password <contraseña>` | Conectarse a una red WiFi              |
| `nmcli connection show`                                  | Mostrar conexiones de red activas      |
| `nmcli connection up <nombre-conexión>`                  | Activar una conexión guardada          |
| `nmcli connection down <nombre-conexión>`                | Desactivar una conexión                |
| `iwctl station <dispositivo> scan`                       | Escanear redes WiFi (usando `iwd`)     |
| `iwctl station <dispositivo> get-networks`               | Listar redes escaneadas (usando `iwd`) |

---

### **Gestión de Paquetes (Pacman)**
| Comando | Descripción |
|---------|-------------|
| `sudo pacman -Syu` | Actualizar el sistema y los paquetes |
| `sudo pacman -S <paquete>` | Instalar un paquete |
| `sudo pacman -R <paquete>` | Eliminar un paquete |
| `sudo pacman -Rs <paquete>` | Eliminar un paquete y sus dependencias no usadas |
| `sudo pacman -Syy` | Forzar la actualización de la base de datos |
| `sudo pacman -Qs <nombre>` | Buscar paquetes instalados |
| `sudo pacman -Fy` | Actualizar la base de datos de archivos |
| `sudo pacman -F <archivo>` | Buscar qué paquete contiene un archivo |

---
audio

sudo systemctl enable --now bluetooth

---

### **Gestión de Servicios (Systemd)**
| Comando | Descripción |
|---------|-------------|
| `sudo systemctl start <servicio>` | Iniciar un servicio |
| `sudo systemctl stop <servicio>` | Detener un servicio |
| `sudo systemctl restart <servicio>` | Reiniciar un servicio |
| `sudo systemctl enable <servicio>` | Habilitar inicio automático |
| `sudo systemctl disable <servicio>` | Deshabilitar inicio automático |
| `sudo systemctl status <servicio>` | Ver estado de un servicio |
| `journalctl -u <servicio> -f` | Ver logs de un servicio en tiempo real |


### **Comandos útiles para PostgreSQL**

#### **Conexión y Autenticación**
| Comando                 | Descripción                               |
| ----------------------- | ----------------------------------------- |
| `sudo -u postgres psql` | Conectarse a PostgreSQL                   |
| `\conninfo`             | Mostrar información de la conexión actual |
| `\password <usuario>`   | Cambiar contraseña de un usuario          |

#### **Gestión de Bases de Datos**
| Comando | Descripción |
|---------|-------------|
| `\l` o `\list` | Listar todas las bases de datos |
| `CREATE DATABASE <nombre>;` | Crear una nueva base de datos |
| `DROP DATABASE <nombre>;` | Eliminar una base de datos |
| `\c <basedatos>` | Cambiar a otra base de datos |

#### **Gestión de Tablas**
| Comando | Descripción |
|---------|-------------|
| `\dt` | Listar tablas en la base de datos actual |
| `\d <tabla>` | Mostrar estructura de una tabla |
| `CREATE TABLE <nombre> (...);` | Crear una nueva tabla |
| `DROP TABLE <nombre>;` | Eliminar una tabla |
| `ALTER TABLE <tabla> ADD COLUMN <columna> <tipo>;` | Añadir columna a una tabla |

#### **Consultas y Operaciones**
| Comando                                                   | Descripción                                |
| --------------------------------------------------------- | ------------------------------------------ |
| `SELECT * FROM <tabla>;`                                  | Consultar todos los registros de una tabla |
| `INSERT INTO <tabla> VALUES (...);`                       | Insertar datos en una tabla                |
| `UPDATE <tabla> SET <columna>=<valor> WHERE <condición>;` | Actualizar registros                       |
| `DELETE FROM <tabla> WHERE <condición>;`                  | Eliminar registros                         |
| `\x` (activar/desactivar)                                 | Modo de visualización expandida            |

#### **Usuarios y Permisos**
| Comando | Descripción |
|---------|-------------|
| `\du` | Listar usuarios y roles |
| `CREATE USER <nombre> WITH PASSWORD '<contraseña>';` | Crear un nuevo usuario |
| `GRANT ALL PRIVILEGES ON DATABASE <basedatos> TO <usuario>;` | Dar permisos a un usuario |
| `ALTER USER <usuario> WITH SUPERUSER;` | Convertir usuario en superusuario |

#### **Exportar e Importar Datos**
| Comando | Descripción |
|---------|-------------|
| `pg_dump -U <usuario> -d <basedatos> > backup.sql` | Exportar base de datos a SQL |
| `psql -U <usuario> -d <basedatos> < backup.sql` | Importar SQL a una base de datos |

---

### **Comandos útiles para Git**

#### **Repositorios**
| Comando | Descripción |
|---------|-------------|
| `git init` | Inicializar un repositorio local |
| `git clone <url>` | Clonar un repositorio remoto |
| `git remote -v` | Listar repositorios remotos |

#### **Commits y Cambios**
| Comando | Descripción |
|---------|-------------|
| `git status` | Ver estado de los archivos |
| `git add <archivo>` | Añadir archivo al staging |
| `git add .` | Añadir todos los cambios al staging |
| `git commit -m "mensaje"` | Hacer commit con un mensaje |
| `git commit --amend` | Modificar el último commit |

#### **Ramas (Branches)**
| Comando | Descripción |
|---------|-------------|
| `git branch` | Listar ramas locales |
| `git branch <nombre>` | Crear nueva rama |
| `git checkout <rama>` | Cambiar a otra rama |
| `git checkout -b <rama>` | Crear y cambiar a nueva rama |
| `git merge <rama>` | Fusionar rama actual con otra |

#### **Actualizar y Sincronizar**
| Comando                     | Descripción                         |
| --------------------------- | ----------------------------------- |
| `git pull`                  | Descargar cambios y fusionar        |
| `git fetch`                 | Descargar cambios sin fusionar      |
| `git push`                  | Subir cambios al repositorio remoto |
| `git push -u origin <rama>` | Subir rama nueva al remoto          |

#### **Historial y Diferencias**
| Comando | Descripción |
|---------|-------------|
| `git log` | Ver historial de commits |
| `git log --oneline` | Historial resumido |
| `git diff` | Ver cambios no añadidos |
| `git diff --staged` | Ver cambios en staging |

#### **Deshacer Cambios**
| Comando | Descripción |
|---------|-------------|
| `git restore <archivo>` | Descartar cambios en un archivo |
| `git reset HEAD <archivo>` | Sacar archivo del staging |
| `git reset --hard <commit>` | Borrar todos los cambios hasta un commit |

### **Tipos de Commits (Conventional Commits)**
| Tipo         | Descripción                                                                  | Ejemplo                             |
| ------------ | ---------------------------------------------------------------------------- | ----------------------------------- |
| **feat**     | Nueva funcionalidad o característica.                                        | `feat: añadir login con Google`     |
| **fix**      | Corrección de un error o bug.                                                | `fix: resolver error en formulario` |
| **docs**     | Cambios en la documentación (sin afectar código).                            | `docs: actualizar README.md`        |
| **style**    | Cambios de formato (espacios, comas, etc.) que no afectan la lógica.         | `style: ajustar indentación`        |
| **refactor** | Reestructuración de código sin corregir bugs ni añadir features.             | `refactor: optimizar función X`     |
| **perf**     | Mejoras de rendimiento.                                                      | `perf: reducir tiempo de carga`     |
| **test**     | Añadir o modificar pruebas.                                                  | `test: agregar test para API`       |
| **chore**    | Tareas de mantenimiento (dependencias, configuraciones, etc.).               | `chore: actualizar dependencias`    |
| **build**    | Cambios en herramientas de compilación o despliegue (Webpack, Docker, etc.). | `build: configurar Dockerfile`      |
| **ci**       | Cambios en integración continua (GitHub Actions, Travis, etc.).              | `ci: añadir workflow de tests`      |
| **revert**   | Revertir un commit anterior.                                                 | `revert: volver al commit abc123`   |

---

### **Estructura Recomendada**
```plaintext
<tipo>(<ámbito opcional>): <descripción breve>

<cuerpo opcional>

<pie opcional> (ej: "Fixes #123")
```
- **Ámbito**: Parte del proyecto afectada (ej: `auth`, `database`).  
- **Cuerpo**: Detalles técnicos (opcional).  
- **Pie**: Referencias a issues o breaking changes (opcional).  

### **Ejemplo
```plaintext
feat(auth): añadir autenticación con JWT

Se implementó JWT para manejo de sesiones.
Incluye validación de tokens.

Fixes #45
```

