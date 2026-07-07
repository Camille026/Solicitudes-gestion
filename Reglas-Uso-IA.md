# Reglas de uso de IA — Prueba Técnica

El uso de IA está **permitido** con declaración y log. La entrega debe demostrar **comprensión**, no solo output generado.

## Permitido

- IA para analizar la entrevista, borradores de documentación o código.
- IA para explicar errores o sugerir correcciones.
- Autocompletado inline (Copilot, Cursor Tab, etc.).

## Obligatorio

1. **Declarar herramientas** en Plantilla-Entrega §5.
2. **Log de prompts relevantes** (decisiones de análisis, diagnóstico, implementación).
3. **Completar Instancia 1** (`Plantilla-Analisis.md`) antes de entregar código.
4. **Diagnóstico de bugs** en Plantilla-Entrega §1 **antes** de corregir.
5. **Validar manualmente al menos 3 comportamientos** y documentarlos en el log.

## Prohibido

1. Entregar solo código sin `Plantilla-Analisis.md` y `Plantilla-Entrega.md`.
2. Abrir o modificar `codigo-base/` antes de completar Instancia 1.
3. Cambiar estructura de carpetas, contrato JSON o URL del endpoint.
4. Omitir el log de IA si usaste herramientas asistidas.

## Cómo se detecta uso superficial

- Coherencia entre Instancia 1 e implementación.
- Diagnóstico de bugs vs archivos modificados y orden de commits.
- Supuestos de §6 Instancia 1 reflejados en validaciones del código.
- Log con validaciones manuales reales, no genéricas.

## Ejemplo de log (formato)

```markdown
### Herramientas
- ChatGPT

### Prompts relevantes
1. "¿Qué actores salen de esta entrevista?" → borrador para §2; reescribí con mis palabras.
2. "¿Cómo modelarías el flujo de estados?" → descarté un camino; usé otro en §3.

### Validaciones manuales
1. Alta con datos válidos → JSON ok y registro en listado.
2. Edición en estado no permitido → error coherente con Instancia 1.
3. Filtro en pantalla → resultados según mi supuesto documentado.
```
