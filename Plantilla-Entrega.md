# Plantilla de Entrega — Instancia 2

> Completar junto con el código corregido.  
> Nombre del candidato: _______________________  
> Fecha de entrega: _______________________  
> URL del repositorio público: _______________________  
> **Enviar la URL por email antes del jueves 16/07/2026, 23:00 hs** al contacto principal: **direcciondegestioninformatica@diputadosmisiones.gov.ar** (Lun–Vie, 8:00–12:00 hs). Contacto secundario: ver [Consigna-General.md](../Consigna-General.md#entrega-y-contacto).

**Orden sugerido:** Instancia 1 terminada → levantar entorno → §1 (diagnóstico, **antes** de corregir) → corregir `codigo-base/` → §2–4 → §5 (log IA, al final).

**Análisis de negocio:** entregado en `Instancia-1-Analisis/Plantilla-Analisis.md`.

---

## 1. Diagnóstico de bugs (antes de corregir)

| # | Bug / síntoma | Archivo | Evidencia | Hipótesis de causa |
|---|---------------|---------|-----------|-------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |

*(Agregar filas si encontrás más fallos.)*

---

## 2. Resumen de cambios realizados

| Archivo modificado | Qué se cambió | Por qué (vincular con Instancia 1 si aplica) |
|--------------------|---------------|---------------------------------------------|
| | | |

---

## 3. Funcionalidades implementadas

- [ ] ABM básico funcional
- [ ] Reglas de edición/eliminación según estado
- [ ] Cambio de estado con reglas de negocio
- [ ] Filtros / orden según Instancia 1
- [ ] Otro: _______________________

---

## 4. Instrucciones de ejecución

**Requisitos:** PHP 7+, MySQL, servidor web local.

1. Base de datos:
   ```
   mysql -u root -p < Instancia-2-Desarrollo/codigo-base/sql/database.sql
   ```
2. Configuración:
   ```
   cp Instancia-2-Desarrollo/codigo-base/config/config_example.php \
      Instancia-2-Desarrollo/codigo-base/config/config.php
   ```
3. Servidor (ejemplo):
   ```
   cd Instancia-2-Desarrollo/codigo-base && php -S localhost:8080
   ```
4. URL: `http://localhost:8080/index.html`
5. Problemas conocidos / pendientes:

---

## 5. Declaración de IA

**¿Usaste herramientas de IA?** (Sí / No)

**Herramientas utilizadas:**

**Log de prompts y validaciones manuales:**

*(Ver [Reglas-Uso-IA.md](../Reglas-Uso-IA.md))*

---

## 6. Autoevaluación (opcional)

| Criterio | 0 | 1 | 2 | 3 | Comentario |
|----------|---|---|---|---|------------|
| Diagnóstico de bugs | | | | | |
| Coherencia Inst. 1 ↔ código | | | | | |
| Calidad del código | | | | | |
