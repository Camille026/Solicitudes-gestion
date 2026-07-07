# Prueba Técnica — Analista de Sistemas / Desarrollador

## Objetivo

Evaluar **análisis de un escenario de negocio** (sin código) y luego **depuración e implementación** sobre un módulo legacy, con coherencia entre ambas etapas.

## Modalidad

- **Formato:** take-home.
- **Plazo:** hasta el jueves **16/07/2026** a las **23:00** hs (hora Argentina).
- **Entrega:** repositorio Git **público**; enviar la URL por email (ver [Entrega y contacto](#entrega-y-contacto)).

## Instancias

| Instancia | Contenido | Peso |
|-----------|-----------|------|
| **1 — Análisis** | Entrevista con usuarios → documentar proceso, reglas, modelo y supuestos | 55% |
| **2 — Desarrollo** | Diagnosticar y corregir `codigo-base/` según tu análisis | 45% |

**Orden obligatorio:** completar Instancia 1 **antes** de abrir o modificar `Instancia-2-Desarrollo/codigo-base/`.

## Material provisto

```
Instancia-1-Analisis/
  Escenario.md              ← transcripción de entrevista (solo descripción)
  Plantilla-Analisis.md     ← completar y entregar

Instancia-2-Desarrollo/
  Consigna-Desarrollo.md
  codigo-base/              ← PHP / MySQL / JS (acceso solo en Instancia 2)

Plantilla-Entrega.md        ← diagnóstico, código, log IA
Reglas-Uso-IA.md
```

## Restricciones (Instancia 2)

1. No modificar estructura de carpetas de `codigo-base/`.
2. No cambiar contrato JSON `{ success, data | error }`.
3. No renombrar `src/controllers/api.php`.
4. Declarar uso de IA según [Reglas-Uso-IA.md](Reglas-Uso-IA.md).

## Criterios globales

| Nivel | Rango | Significado |
|-------|-------|-------------|
| Rechazado | 0–39 | Incompleto o incoherente |
| Trainee viable | 40–59 | Mínimo con acompañamiento |
| Estándar | 60–79 | Análisis y código coherentes |
| Refinado | 80–100 | Análisis sólido, debugging documentado |

## Entrega y contacto

| | |
|---|---|
| **Fecha límite** | Jueves **16/07/2026**, hasta las **23:00** hs (hora Argentina) |

### Contacto principal

| | |
|---|---|
| **Email** | direcciondegestioninformatica@diputadosmisiones.gov.ar |
| **Horario** | Lun–Vie, 8:00–12:00 hs |

### Contacto secundario

| | |
|---|---|
| **Email** | robertosueldo@diputadosmisiones.gov.ar |
| **Email alternativo** | roberto.sueldo@gmail.com |
| **Teléfono / WhatsApp** | +54 9 376 43-0550 |
| **Horario** | Mar, mié, vie, sáb y dom, 14:00–20:00 hs |

### Cómo entregar

1. Subir trabajo completo a repositorio Git **público**.
2. Incluir `Plantilla-Analisis.md`, `Plantilla-Entrega.md` y código corregido.
3. Enviar la URL del repositorio por **email** al contacto principal (o secundario si no obtenés respuesta).
4. Historial de commits legible.
