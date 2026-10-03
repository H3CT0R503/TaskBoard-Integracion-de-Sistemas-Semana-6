# 💳 TaskBoard — Semana 6 (Eloquent ORM y Migraciones)

> Proyecto integrador de **Integración de Sistemas (CE-ISC019)** — TaskBoard deja de simular datos y guarda información real en MySQL con Eloquent.

![Laravel](https://img.shields.io/badge/Laravel-11.x-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?style=for-the-badge&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Eloquent-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

---

## 📖 Descripción

En la **Semana 6**, la pasarela de pagos **TaskBoard** pasa de usar arreglos de PHP a trabajar con una base de datos **MySQL real** mediante el ORM **Eloquent** de Laravel. Abarca dos guías:

- **Jueves** — Migraciones y modelos Eloquent (Comercio y Transacción).
- **Viernes** — Relaciones Eloquent (`hasMany`/`belongsTo`) y datos reales en los controladores.

---

## ✨ Características

- ✅ Migraciones versionadas para crear las tablas `comercios`, `transacciones` y `eventos_transaccion`.
- ✅ Modelos Eloquent con `$fillable` para asignación masiva.
- ✅ Llave foránea con `foreignId()->constrained()` e integridad referencial.
- ✅ Relaciones `hasMany()` y `belongsTo()` entre las tres entidades.
- ✅ Prevención del problema N+1 con `with()` (eager loading).
- ✅ Route Model Binding para inyectar modelos directamente en las rutas.

---

## 🛠️ Tecnologías

| Herramienta | Uso |
|---|---|
| **Laravel 11.x** | Framework principal |
| **Eloquent ORM** | Acceso a datos con objetos |
| **MySQL** | Base de datos real |
| **Artisan / Tinker** | Migraciones y pruebas en vivo |

---

## 📋 Requisitos

- PHP **8.2+**, Composer y Laravel instalados
- **MySQL** corriendo (XAMPP) con la base `taskboard` creada
- Extensión `pdo_mysql` habilitada

---

## ⚙️ Instalación

```bash
git clone https://github.com/H3CT0R503/NOMBRE-DEL-REPO.git
cd NOMBRE-DEL-REPO
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate      # crea las tablas en MySQL
php artisan serve
```

> Configura la conexión en `.env`: `DB_DATABASE=taskboard`, `DB_USERNAME=root`, `DB_PASSWORD=` (vacío en XAMPP).

---

## 🕹️ Comandos útiles

| Comando | Qué hace |
|---|---|
| `php artisan make:model Comercio -m` | Crea modelo + migración juntos |
| `php artisan migrate` | Ejecuta las migraciones pendientes |
| `php artisan migrate:rollback` | Deshace la última migración |
| `php artisan migrate:status` | Muestra el estado de las migraciones |
| `php artisan tinker` | Consola para probar Eloquent en vivo |

---

## 📂 Estructura (relevante)

```text
taskboard/
├── app/Models/            # Comercio, Transaccion, EventoTransaccion
├── database/migrations/   # create_comercios_table, create_transacciones_table, ...
├── .env                   # conexión a MySQL (no se sube a Git)
└── routes/web.php
```

---

## 🧠 Conceptos aplicados

- **ORM vs SQL manual:** `Comercio::find(1)` en lugar de PDO + SQL.
- **Migración:** cambios de estructura como código versionado (`up()` / `down()`).
- **Llave foránea e integridad referencial:** una transacción siempre apunta a un comercio real.
- **Relaciones Eloquent:** `hasMany` (uno a muchos) y `belongsTo` (pertenece a).
- **Convenciones:** tabla en plural snake_case, modelo en singular PascalCase.

---

## 👤 Autor

**Hector Interiano**
📚 Integración de Sistemas · Ciclo 02-2026
🎓 UPED "Dr. Luis Alonso Aparicio" · Docente: Ing. Oscar Contreras

---

<p align="center">Hecho con 💙 y Laravel</p>
