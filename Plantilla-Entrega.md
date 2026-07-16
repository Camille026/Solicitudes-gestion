# Plantilla de Entrega — Instancia 2

> Completar junto con el código corregido.  
> Nombre del candidato: _____Garayo, Camila Daiana__________________  
> Fecha de entrega: _______16/07/2026________________  
> URL del repositorio público: https://github.com/Camille026/Solicitudes-gestion.git  

> **Enviar la URL por email antes del jueves 16/07/2026, 23:00 hs** al contacto principal: **direcciondegestioninformatica@diputadosmisiones.gov.ar** (Lun–Vie, 8:00–12:00 hs). Contacto secundario: ver [Consigna-General.md](../Consigna-General.md#entrega-y-contacto).

**Orden sugerido:** Instancia 1 terminada → levantar entorno → §1 (diagnóstico, **antes** de corregir) → corregir `codigo-base/` → §2–4 → §5 (log IA, al final).

**Análisis de negocio:** entregado en `Instancia-1-Analisis/Plantilla-Analisis.md`.

---

## 1. Diagnóstico de bugs (antes de corregir)

| # | Bug / síntoma                                            | Archivo                         | Evidencia                                                             | Hipótesis de causa                                                                   
|---|-------------------------------------------------------    |---------------------------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| 1 | Error SQLSTATE[42S22] Unknown column 'fecha_creacion'     | Solicitud.php                   | API devolvía error al listar                                         | Código usaba columna distinta a la definida en DB
 (fecha_creacion vs created_at)                                 |
| 2 | Validación de título fallaba                              | Solicitud.php (método validate) | API devolvía "El título es obligatorio" aunque estaba escrito        | Input en index.html no tenía name="titulo", por lo que no llegaba 
al backend                                                      |
| 3 | Acciones no restringidas según estado                     | api.php                         | Se podía editar/borrar vía API aunque frontend ocultaba botones      | Faltaban reglas de negocio en controlador para bloquear edición/borrado
 según estado                                                   |
| 4 | Función con await no declarada como asíncrona             | app.js                          | Error en consola: Unexpected reserved word 'await'                   | Falta de async en la declaración de la función                                       
| 5 | Faltaba archivo config.php con credenciales               | config.php                      | Error de conexión PDO al iniciar                                     | Proyecto incluía solo config_example.php, requería crear config.php real 
| 6 | Faltaban llaves de cierre en funciones                     | Solicitud.php y Controllers.php | El servidor devolvía error 500 y en consola aparecía el parse error.| Funciones o clases sin llaves de cierre(}) al final del archivo                      

*(Agregar filas si encontrás más fallos.)*


## 2. Resumen de cambios realizados

| Archivo modificado | Qué se cambió                                               | Por qué (vincular con Instancia 1 si aplica) |
|--------------------|---------------|---------------------------------------------|
| `Solicitud.php`    | Ajuste de funcion `getAll()` para usar `created_at` en ordenamiento | Columna correcta según modelo de datos |
| `Solicitud.php`    | Refuerzo de `validate()` con `trim()` y validación de prioridad | Cumplir reglas de negocio de Instancia 1 |
| `index.html`       | Agregado `name="titulo"` en input | Permitir envío correcto de datos al backend |
| `api.php` (controlador) | Restricción en `update()` y `delete()` para permitir solo si estado = pendiente | Alinear reglas de negocio con análisis de Instancia 1 |
| `Solicitud.php` + `api.php` | Nueva función `cambiarEstado()` y endpoints `tomar`, `resolver`, `rechazar` | Implementar ciclo de vida de solicitudes |

---

## 3. Funcionalidades implementadas

- [x] ABM básico funcional
- [x] Reglas de edición/eliminación según estado
- [x] Cambio de estado con reglas de negocio
- [x] Filtros / orden según Instancia 1
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
```
No hay autenticación de usuario. Login pendiente

```
---

## 5. Declaración de IA

**¿Usaste herramientas de IA?**: Sí

**Herramientas utilizadas:Claude.ai/Microsoft Copilot**

**Log de prompts y validaciones manuales:**
--
###Promps relevantes

1. A partir del archivo compartido y de la entrevista, ¿Qué sugerencias consideras esenciales para mi análisis -> Para Inst.1, luego de haber desarrollado todos los puntos en un 
  documento Word, adjunté en la herramiente IA, a lo que me ofrece cambios en el modelo de datos (Ej.: tipo de datos para estado que sea ENUM, no VARCHAR, añadir fecha_actualizacion). 
2. En el diagrama de flujo ¿Consideras que representa correctamente el ciclo de vida de una solicitud?->En 3, escribí descripción según sugerencia dada.
-Instancia 2:

1. "Error SQLSTATE[42S22] Unknown column 'fecha_creacion'" → En el script se ejecuta fecha_creacion en el método getAll()-Lo cambié según el script: created_at en linea 25 de Solicitud.php ->
  {
  "success": false,
  "error": "Error del servidor: SQLSTATE[42S22]: Column not found: 1054 Unknown column 'fecha_creacion' in 'order clause'"
  }

2. "Faltaba archivo config.php" → Ajuste base de datos: luego de crear config.php y crear la base de datos con credenciales de conexión.

3. "Acciones no restringidas según estado" → propuesta de reglas en `update()` y `delete()` para solo permitir si estado = pendiente.

4. "ERROR al intentar crear nueva solicitud: La validación de campo obligatorio de titulo no responde aun cuando el campo es completado"
5. "En validate se intenta eliminar espacios en el campo `titulo`-> el error cambia:

6. Unchecked runtime.lastError: Could not establish connection. Receiving end does not exist.
  src/controllers/api.php:1  Failed to load resource: the server responded with a status of 400 (Bad Request) 
  index.html:1 Unchecked runtime.lastError: Could not establish connection. Receiving end does not exist. ->Sugerencia de comprobar en index.html que el input tuviese `name=titulo`. Al verificar que no estaba, lo agregué.

###Validaciones manuales

**Nueva solicitud:** Creación de nueva solicitud → aparece en la base de datos con estado `pendiente` y fechas correctas (`created_at`, `updated_at`).  
 **Cambio de estado:** Al presionar el botón de tomar, pasa a estar `en_proceso`; al presionar Resolver o Rechazar, pasa a `resuelta` o `rechazada`.  
3. **Restricciones:** Intento de editar/borrar en estado no permitido → backend devuelve error coherente con reglas de negocio.  
4. **Frontend:** Corrección de `async` en `app.js` → tabla carga solicitudes sin error en consola.  
5. **Conexión:** Creación de `config.php` → conexión PDO exitosa, sin error de driver.


*(Ver [Reglas-Uso-IA.md](../Reglas-Uso-IA.md))*

---

## 6. Autoevaluación (opcional)

| Criterio |                    0 | 1 |  2 | 3 | Comentario |
|----------|---|---|---|---|------------   |
| Diagnóstico de bugs          |  |   |  2 |   | Se documentaron los fallos principales.          |
| Coherencia Inst. 1 ↔ código  |  |   |    | 3 | No se implementó nada que no estuviera en Instancia 1         |
| Calidad del código           |  |   | 2  |   |Se pudo resolver y poner en marcha las funcionalidades necesarias          |
