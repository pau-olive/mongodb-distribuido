# MongoDB Distribuido: Replica Set con Árbitro y Clúster Sharded

![Portada del proyecto](cover.png)

## Descripción del Proyecto
Proyecto personal de **Administración de Sistemas y Bases de Datos** centrado en la configuración avanzada de un **entorno MongoDB distribuido**, orientado a **alta disponibilidad** y **escalabilidad horizontal**, simulando un entorno de producción real en local.

El objetivo del proyecto es comprender y aplicar conceptos reales de arquitectura distribuida utilizados en entornos empresariales, sin necesidad de disponer de múltiples máquinas físicas.

---

## Características Principales
- **Replica Set** con 3 nodos (1 primario + 2 secundarios).
- **Árbitro** para mejorar las elecciones sin almacenar datos.
- **Clúster Sharded completo**, con:
  - Config Servers en Replica Set.
  - Shards independientes.
  - Router `mongos`.
- Activación del sharding en base de datos y colección con **clave hashed**.
- Inserción masiva de datos de prueba.
- Verificación del balanceo y distribución de datos.
- Entorno **100% reproducible en local** mediante puertos diferenciados (Windows + PowerShell).

---

## Tecnologías y Herramientas Utilizadas
- **MongoDB**
  - `mongod`
  - `mongos`
  - `mongosh`
- **PowerShell**
- Comandos principales:
  - `rs.initiate()`
  - `rs.add()`
  - `rs.addArb()`
  - `rs.status()`
  - `sh.addShard()`
  - `sh.enableSharding()`
  - `sh.shardCollection()`
  - `sh.status()`
  - `getShardDistribution()`

---

## Objetivos Alcanzados
- Alta disponibilidad mediante **replicación automática**.
- Gestión de **failover** y elecciones de primario.
- Escalabilidad horizontal real mediante sharding.
- Arquitectura MongoDB completa simulada en local.
- Validación del correcto funcionamiento del clúster distribuido.

---

## Arquitectura del Proyecto

### Replica Set
- 3 nodos de datos:
  - 1 Primario
  - 2 Secundarios
- 1 Árbitro:
  - No almacena datos.
  - Participa únicamente en las elecciones.

### Clúster Sharded
- **Config Servers** (Replica Set):
  - Almacenan la configuración del clúster.
- **Shards**:
  - Nodos independientes que contienen los datos.
- **mongos**:
  - Router que recibe las peticiones del cliente y las distribuye a los shards correspondientes.

---

## Proceso de Configuración (Resumen)

### 1. Configuración del Replica Set
- Creación de carpetas de persistencia.
- Inicio de múltiples instancias `mongod` con puertos distintos.
- Inicialización del Replica Set.
- Añadido de los nodos secundarios.
- Verificación mediante `rs.status()`.

### 2. Añadido del Árbitro
- Creación de un nodo dedicado.
- Incorporación al Replica Set con `rs.addArb()`.
- Comprobación del funcionamiento de elecciones y failover.

### 3. Configuración del Clúster Sharded
- Creación de los Config Servers en Replica Set.
- Inicialización del Replica Set de configuración.
- Creación e inicio de los shards.
- Inicio del router `mongos`.
- Añadido de los shards al clúster.

### 4. Sharding y Datos
- Activación del sharding en la base de datos.
- Fragmentación de la colección con clave `_id` hashed.
- Inserción de **10.000 documentos** de prueba.
- Verificación de la distribución de chunks entre shards.

---

## Verificación y Validación
- Estado del Replica Set con `rs.status()`.
- Estado del clúster con `sh.status()`.
- Distribución real de los datos con `getShardDistribution()`.

Estas comprobaciones confirman que:
- El balanceador funciona correctamente.
- Los datos están repartidos entre los shards.
- El clúster es estable y funcional.

---

## Aprendizajes Clave
- Funcionamiento interno de los **Replica Sets**.
- Gestión de elecciones y uso de árbitros.
- **Sharding** y distribución de datos mediante clave hashed.
- Arquitectura distribuida aplicada en entorno local.
- Verificación y troubleshooting en MongoDB.

---

## Relevancia Profesional
Proyecto alineado con competencias clave en:
- **Big Data y NoSQL**.
- **Cloud** (MongoDB Atlas, Amazon DocumentDB).
- **DevOps** y arquitecturas escalables.
- Administración de sistemas y bases de datos distribuidas.

---

## Conclusión
Proyecto completo y funcional de **MongoDB distribuido**, pensado para comprender arquitecturas reales utilizadas en entornos profesionales y preparado para escalar.

⭐ Si te interesan las bases de datos distribuidas, ¡dale una estrella al repositorio!

---

## Capturas del Proceso Completo

<div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 15px; margin: 30px 0;">

<img src="screenshots/screenshots (1).png">
<img src="screenshots/screenshots (2).png">
<img src="screenshots/screenshots (3).png">
<img src="screenshots/screenshots (4).png">
<img src="screenshots/screenshots (5).png">
<img src="screenshots/screenshots (6).png">
<img src="screenshots/screenshots (7).png">
<img src="screenshots/screenshots (8).png">
<img src="screenshots/screenshots (9).png">
<img src="screenshots/screenshots (10).png">
<img src="screenshots/screenshots (11).png">
<img src="screenshots/screenshots (12).png">
<img src="screenshots/screenshots (13).png">
<img src="screenshots/screenshots (14).png">
<img src="screenshots/screenshots (15).png">
<img src="screenshots/screenshots (16).png">
<img src="screenshots/screenshots (17).png">
<img src="screenshots/screenshots (18).png">
<img src="screenshots/screenshots (19).png">
<img src="screenshots/screenshots (20).png">
<img src="screenshots/screenshots (21).png">
<img src="screenshots/screenshots (22).png">
<img src="screenshots/screenshots (23).png">
<img src="screenshots/screenshots (24).png">
<img src="screenshots/screenshots (25).png">
<img src="screenshots/screenshots (26).png">
<img src="screenshots/screenshots (27).png">
<img src="screenshots/screenshots (28).png">
<img src="screenshots/screenshots (29).png">
<img src="screenshots/screenshots (30).png">
<img src="screenshots/screenshots (31).png">
<img src="screenshots/screenshots (32).png">
<img src="screenshots/screenshots (33).png">
<img src="screenshots/screenshots (34).png">
<img src="screenshots/screenshots (35).png">
<img src="screenshots/screenshots (36).png">
<img src="screenshots/screenshots (37).png">

</div>

---

**Autor**: Pau Olivé Moreno  
**Fecha**: Principios de 2025
