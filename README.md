# Prueba Técnica — Analista de Sistemas / Desarrollador

Material take-home para el puesto **Analista de Sistemas – Desarrollador**.  
**Fecha límite:** jueves **16/07/2026**, **23:00** hs (hora Argentina).

## Por dónde empezar

1. Leer [Consigna-General.md](Consigna-General.md).
2. **Instancia 1:** leer la entrevista en [Instancia-1-Analisis/Escenario.md](Instancia-1-Analisis/Escenario.md) y completar [Plantilla-Analisis.md](Instancia-1-Analisis/Plantilla-Analisis.md).
3. **Instancia 2:** leer [Consigna-Desarrollo.md](Instancia-2-Desarrollo/Consigna-Desarrollo.md), diagnosticar y corregir `codigo-base/`, completar [Plantilla-Entrega.md](Plantilla-Entrega.md).
4. [Reglas-Uso-IA.md](Reglas-Uso-IA.md) si usás herramientas de IA.

**Orden obligatorio:** Instancia 1 → Instancia 2. No abras `codigo-base/` hasta completar el análisis de negocio.

## Instancias

| Instancia | Peso | Carpeta | Qué hacer |
|-----------|------|---------|-----------|
| **1 — Análisis del escenario** | 55% | [Instancia-1-Analisis/](Instancia-1-Analisis/) | Analizar la entrevista y documentar proceso, reglas y supuestos |
| **2 — Código** | 45% | [Instancia-2-Desarrollo/](Instancia-2-Desarrollo/) | Diagnosticar bugs, corregir el módulo, coherente con Instancia 1 |

## Configuración del entorno (Instancia 2)

Requisitos: **PHP 7+**, **MySQL**, servidor web local.

```bash
mysql -u root -p < Instancia-2-Desarrollo/codigo-base/sql/database.sql

cp Instancia-2-Desarrollo/codigo-base/config/config_example.php \
   Instancia-2-Desarrollo/codigo-base/config/config.php

cd Instancia-2-Desarrollo/codigo-base
php -S localhost:8080
```

Abrí `http://localhost:8080/index.html`. No subas `config.php` con credenciales reales.

El módulo puede no funcionar al primer intento; documentá fallos en Plantilla-Entrega **antes** de corregir.

## Estructura del repositorio

```
.
├── README.md
├── Consigna-General.md
├── Reglas-Uso-IA.md
├── Plantilla-Entrega.md          ← Instancia 2
├── Instancia-1-Analisis/
│   ├── Escenario.md              ← entrevista (solo descripción)
│   └── Plantilla-Analisis.md     ← tu análisis de negocio
└── Instancia-2-Desarrollo/
    ├── Consigna-Desarrollo.md
    └── codigo-base/
```

## Entrega

1. Repositorio Git **público** con historial legible.
2. `Instancia-1-Analisis/Plantilla-Analisis.md` completada.
3. `Plantilla-Entrega.md` + `codigo-base/` corregido.
4. Enviar la URL por email al **contacto principal** ([Consigna-General.md](Consigna-General.md#entrega-y-contacto)).

## Entrega y contacto

Ver [Consigna-General.md](Consigna-General.md#entrega-y-contacto).
