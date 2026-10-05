# DAW Project Hub
Pequeña página web para practicar un flujo profesional de trabajo con Git y GitHub.

## Historial del proyecto

Es preferible realizar varios commits pequeños y coherentes en lugar de uno solo grande porque:
1. **Trazabilidad:** Facilita identificar exactamente en qué momento se introdujo un cambio o un error específico.
2. **Reversibilidad:** Permite deshacer o corregir un cambio concreto sin perder el trabajo realizado en el resto del proyecto.
3. **Legibilidad:** Ofrece un historial claro y comprensible que ayuda a cualquier miembro del equipo a seguir la evolución del código.

## Reflexión de Seguridad (.env y secretos)

1. **¿Por qué `.env.example` puede publicarse?**
   Porque solo contiene la estructura o plantilla de las variables de entorno sin valores reales ni secretos, sirviendo de guía para otros desarrolladores.

2. **¿Por qué `.env` debe ignorarse?**
   Porque contiene credenciales, claves API o tokens de acceso reales que, si se hacen públicos, comprometerían la seguridad de la aplicación.

3. **¿Qué habría que hacer si una contraseña o token reales se publican en GitHub?**
   Revocar y cambiar inmediatamente la credencial o token expuesto para invalidarlo, e invalidar cualquier acceso que pudiera haberse producido.

4. **¿Bastaría con eliminar el archivo en un commit posterior? Justificar respuesta.**
   No, porque Git mantiene todo el historial de cambios. Aunque el archivo se elimine en el último commit, cualquier persona podría ver las credenciales en commits anteriores examinando el historial. Es necesario revocar la clave y purgar el historial del repositorio.

   ## Conflicto resuelto

- **Origen del conflicto:** Se produjo al intentar fusionar la rama `feature/nuevo-eslogan` en `main` habiendo modificado en ambas ramas la misma línea de código (la etiqueta `<h1>` de la cabecera en `index.html`) de forma independiente.
- **Archivo afectado:** `index.html`.
- **Decisión tomada:** Se interpretaron los marcadores de conflicto (`<<<<<<<`, `=======`, `>>>>>>>`) y se redactó una versión combinada que integra ambas ideas: *"Un espacio para conocer las fases del desarrollo, publicación y despliegue de aplicaciones web."*
- **Comprobación:** Se eliminaron las marcas de conflicto, se preparó el archivo con `git add`, se completó el commit de merge y se verificó que el repositorio quedó en un estado limpio con `git status` y `git log --oneline --graph`.