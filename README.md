# MongoDB Distribuït: Replica Set amb Àrbitre i Clúster Sharded

![Portada del projecte](cover.png)

## Descripció del Projecte
Projecte personal d’**Administració de Sistemes i Bases de Dades** centrat en la configuració avançada d’un **entorn MongoDB distribuït**, orientat a **alta disponibilitat** i **escalabilitat horitzontal**, simulant un entorn de producció real en local.

L’objectiu del projecte és entendre i aplicar conceptes reals d’arquitectura distribuïda utilitzats en entorns empresarials, sense necessitat de múltiples màquines físiques.

---

## Característiques Principals
- **Replica Set** amb 3 nodes (1 primari + 2 secundaris).
- **Àrbitre** per millorar les eleccions sense emmagatzemar dades.
- **Clúster Sharded complet** amb:
  - Config Servers en Replica Set.
  - Shards independents.
  - Router `mongos`.
- Activació de sharding en base de dades i col·lecció amb **clau hashed**.
- Inserció massiva de dades de prova.
- Verificació del balançament i distribució de dades.
- Entorn **100% reproduïble en local** mitjançant ports diferenciats (Windows + PowerShell).

---

## Tecnologies i Eines Utilitzades
- **MongoDB**
  - `mongod`
  - `mongos`
  - `mongosh`
- **PowerShell**
- Comandes principals:
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

## Objectius Aconseguits
- Alta disponibilitat mitjançant **replicació automàtica**.
- Gestió de **failover** i eleccions de primari.
- Escalabilitat horitzontal real amb sharding.
- Arquitectura MongoDB completa simulada en local.
- Validació del funcionament del clúster distribuït.

---

## Arquitectura del Projecte

### Replica Set
- 3 nodes de dades:
  - 1 Primari
  - 2 Secundaris
- 1 Àrbitre:
  - No emmagatzema dades.
  - Participa únicament en eleccions.

### Clúster Sharded
- **Config Servers** (Replica Set):
  - Emmagatzemen la configuració del clúster.
- **Shards**:
  - Nodes independents que contenen les dades.
- **mongos**:
  - Router que rep les consultes del client i les distribueix als shards corresponents.

---

## Procés de Configuració (Resum)

### 1. Configuració del Replica Set
- Creació de carpetes de persistència.
- Inici de múltiples instàncies `mongod` amb ports diferents.
- Inicialització del Replica Set.
- Afegit dels nodes secundaris.
- Verificació amb `rs.status()`.

### 2. Afegit de l’Àrbitre
- Creació d’un node dedicat.
- Afegit al Replica Set amb `rs.addArb()`.
- Comprovació del funcionament d’eleccions i failover.

### 3. Configuració del Clúster Sharded
- Creació dels Config Servers en Replica Set.
- Inicialització del Replica Set de configuració.
- Creació i inici dels shards.
- Inici del router `mongos`.
- Afegit dels shards al clúster.

### 4. Sharding i Dades
- Activació del sharding a la base de dades.
- Fragmentació de la col·lecció amb clau `_id` hashed.
- Inserció de **10.000 documents** de prova.
- Verificació de la distribució de chunks entre shards.

---

## Verificació i Validació
- Estat del Replica Set amb `rs.status()`.
- Estat del clúster amb `sh.status()`.
- Distribució real de dades amb `getShardDistribution()`.

Aquestes comprovacions confirmen que:
- El balançador funciona correctament.
- Les dades estan repartides entre shards.
- El clúster és funcional i estable.

---

## Aprenentatges Clau
- Funcionament intern dels **Replica Sets**.
- Gestió d’eleccions i àrbitres.
- **Sharding** i distribució de dades amb clau hashed.
- Arquitectura distribuïda aplicada en entorn local.
- Verificació i troubleshooting en MongoDB.

---

## Rellevància Professional
Projecte alineat amb competències clau en:
- **Big Data i NoSQL**.
- **Cloud** (MongoDB Atlas, Amazon DocumentDB).
- **DevOps** i arquitectures escalables.
- Administració de sistemes i bases de dades distribuïdes.

---

## Conclusió
Projecte complet i funcional de **MongoDB distribuït**, pensat per entendre arquitectures reals utilitzades en entorns professionals i preparat per escalar.

⭐ Si t’interessen les bases de dades distribuïdes, dona-li una estrella al repositori!

---

## Captures del Procés Complet

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
**Data**: Principis de 2025
