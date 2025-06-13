# 🛠️ Troubleshooting Guide

Este documento describe los errores comunes al trabajar con la API de GitHub y cómo resolverlos.

---

## ❌ Error 401 - Unauthorized

### Causa:
- Token de autenticación incorrecto, vencido o no incluido.
- Headers mal formados.

### Solución:
- Verificá que estés enviando el token en el header:

Authorization: Bearer TU_TOKEN
- Comprobá que el token tenga permisos para acceder a los datos deseados.

---

## ❌ Error 403 - Forbidden / Rate Limit Exceeded

### Causa:
- Excediste el límite de llamadas a la API.

### Solución:
- Autenticá tus requests (usuarios autenticados tienen más límite).
- Consultá tu estado con:

GET https://api.github.com/rate_limit
- Esperá unos minutos antes de volver a intentar (GitHub reinicia el límite cada hora).

---

## ❌ Error 404 - Not Found

### Causa:
- El recurso solicitado no existe o es privado.
- URL mal escrita (usuario/repositorio equivocado).

### Solución:
- Verificá que el repositorio y/o archivo exista.
- Si es privado, asegurate de que tu token tenga acceso y permisos correctos.

---

## ✅ Buenas prácticas

- Usá autenticación para evitar límites bajos.
- Implementá manejo de errores en tus scripts.
- Siempre verificá la documentación oficial de GitHub: https://docs.github.com/en/rest

