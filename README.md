# Tarea 2 - Taller de Redes y Servicios
## Protocolo MySQL

**Integrantes:**
- Juan Pablo Manriquez
- Benjamín Paredes

**Curso:** Taller de Redes y Servicios 2026-1  
**Universidad:** Diego Portales

---

## Descripción

Este repositorio contiene la implementación del protocolo MySQL mediante
contenedores Docker, desarrollada sobre Ubuntu 24.04. Se utilizó
`mysql/mysql-server:8.0` como servidor y DBeaver Community Edition como
cliente gráfico.

---

## Estructura del repositorio

taller-redes-tarea2/

├── servidor/

│   └── Dockerfile        # Imagen del servidor MySQL

├── cliente/

│   └── Dockerfile        # Imagen del cliente MySQL (ubuntu + mysql-client)

├── docker-compose.yml    # Orquestación de los contenedores

├── captura_mysql.pcapng  # Captura de tráfico con Wireshark

└── README.md

---

## Requisitos

- Ubuntu 24.04 (nativo o máquina virtual)
- Docker
- Docker Compose v2
- Wireshark
- DBeaver Community Edition

---

## Instrucciones de uso

### 1. Clonar el repositorio

```bash
git clone https://github.com/benjaparedess/taller-redes-tarea2.git
cd taller-redes-tarea2
```

### 2. Levantar los contenedores

```bash
docker compose up --build
```

Esperar hasta ver `Welcome to the MySQL monitor` en la terminal.

### 3. Conectar DBeaver

Abrir DBeaver y crear una nueva conexión con los siguientes parámetros:

| Campo | Valor |
|---|---|
| Host | localhost |
| Puerto | 3306 |
| Base de datos | taller_db |
| Usuario | alumno |
| Contraseña | alumno123 |

### 4. Ejecutar consultas de prueba

```sql
CREATE TABLE IF NOT EXISTS CURSOS (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL
);

INSERT INTO CURSOS (nombre) VALUES ('Taller de Redes');
INSERT INTO CURSOS (nombre) VALUES ('Bases de Datos');
INSERT INTO CURSOS (nombre) VALUES ('Optimización');

SELECT * FROM CURSOS;
```

### 5. Capturar tráfico con Wireshark

```bash
sudo wireshark &
```

Seleccionar interfaz `any` y aplicar filtro `tcp.port == 3306`.

---

## Credenciales

| Campo | Valor |
|---|---|
| Usuario root | root / taller123 |
| Usuario app | alumno / alumno123 |
| Base de datos | taller_db |
| Puerto | 3306 |



## Video de demostración
[Ver demostración en Google Drive](https://drive.google.com/drive/u/0/folders/1vKUmhqk0MAdahzh-Spx91ezWPk9NP5yB)