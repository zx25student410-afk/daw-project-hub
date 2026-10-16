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
Edición remota de prueba.
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

## Instrucciones de uso

Para visualizar la página web en tu navegador:
1. Clona el repositorio en tu máquina local mediante SSH:
   `git clone git@github.com:zx25student410-afk/daw-project-hub.git`
2. Navega al directorio del proyecto:
   `cd daw-project-hub`
3. Abre el archivo `index.html` directamente en tu navegador web preferido o utiliza la extensión **Live Server** en Visual Studio Code.

## Forks y colaboración

1. **¿Qué es un fork en GitHub?**
   Es una copia completa e independiente de un repositorio ajeno alojada en tu propia cuenta de GitHub, que te permite hacer cambios libremente sin afectar al proyecto original.

2. **¿En qué se diferencia un fork de una rama?**
   Una rama vive dentro del mismo repositorio y comparte permisos y contexto directo con el proyecto. Un fork es un repositorio completamente distinto que pertenece a otra cuenta de GitHub.

3. **¿En qué cuenta se almacena un fork?**
   Se almacena en la cuenta personal (o de organización) del usuario que realiza la copia, no en la del propietario original.

4. **¿Cuándo resulta útil trabajar mediante un fork?**
   Es útil al colaborar en proyectos de código abierto (*open source*) o cuando no se tienen permisos directos de escritura en el repositorio original.

5. **¿Qué relación existe entre el repositorio original y el fork?**
   Mantienden un vínculo de origen que permite comparar cambios, enviar propuestas de mejora (*Pull Requests*) y sincronizar novedades del proyecto original hacia el fork.

6. **¿Qué es el repositorio upstream?**
   Es el término que se utiliza para referirse al repositorio fuente u original a partir del cual creaste tu fork.

7. **¿Qué diferencia existe entre `origin` y `upstream`?**
   `origin` apunta a tu copia remota personal (tu fork), mientras que `upstream` apunta al repositorio remoto original del autor o proyecto fuente.

8. **¿Cómo se propone que un cambio del fork llegue al repositorio original?**
   Mediante la solicitud de una propuesta de cambio llamada **Pull Request (PR)** enviada desde una rama del fork hacia la rama principal del repositorio original.

9. **¿Quién decide si se acepta la propuesta?**
   Los propietarios, mantenedores o administradores con permisos de escritura en el repositorio original (`upstream`).

10. **¿Puede seguir evolucionando el repositorio original mientras existe el fork?**
    Sí, ambos repositorios avanzan de forma independiente. El creador del fork debe sincronizar periódicamente su copia con el repositorio `upstream` para mantenerse al día.