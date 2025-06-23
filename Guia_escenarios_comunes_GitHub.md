# Guía de Escenarios Comunes en GitHub

## Introducción

Durante el desarrollo del proyecto, te encontrarás con diversas situaciones en GitHub y Git. Esta guía te ayudará a resolver los problemas más comunes que enfrentan los equipos de desarrollo. **No entres en pánico** - todos estos problemas tienen solución.

## 🚨 Escenarios de Emergencia

### Escenario 1: "¡Borré código importante por accidente!"

**Síntomas**:
- Eliminaste archivos o código por error
- Hiciste cambios que rompieron algo que funcionaba
- No recuerdas qué cambios hiciste

**Solución**:
```bash
# Ver historial de commits recientes
git log --oneline -10

# Volver a un commit anterior específico (sin perder historial)
git revert [hash-del-commit]

# O descartar cambios locales no guardados
git checkout -- nombre-archivo.cs

# O volver todo el directorio a un estado anterior
git reset --hard [hash-del-commit]
```

**Prevención**:
- Haz commits frecuentes
- Usa mensajes descriptivos
- Prueba antes de hacer push

### Escenario 2: "Mi compañero y yo modificamos el mismo archivo"

**Síntomas**:
```
Auto-merging Controllers/ProductoController.cs
CONFLICT (content): Merge conflict in Controllers/ProductoController.cs
Automatic merge failed; fix conflicts and then commit the result.
```

**Solución paso a paso**:

1. **No entres en pánico** - Los conflictos son normales

2. **Ve qué archivos tienen conflictos**:
   ```bash
   git status
   ```

3. **Abre el archivo en conflicto** y busca las marcas:
   ```csharp
   public ActionResult Create()
   {
   <<<<<<< HEAD
       // Tu código
       var productos = db.Productos.ToList();
       return View(productos);
   =======
       // Código de tu compañero
       var productos = GetAllProductos();
       return View(productos);
   >>>>>>> branch-de-tu-compañero
   }
   ```

4. **Edita manualmente** para resolver:
   ```csharp
   public ActionResult Create()
   {
       // Versión final combinada
       var productos = db.Productos.ToList();
       return View(productos);
   }
   ```

5. **Elimina las marcas** `<<<<<<<`, `=======`, `>>>>>>>`

6. **Guarda y confirma**:
   ```bash
   git add Controllers/ProductoController.cs
   git commit -m "fix: resolver conflicto en ProductoController"
   git push origin main
   ```

**Prevención**:
- Comunica cuando vayas a trabajar en un archivo
- Haz `git pull` frecuentemente
- Trabaja en archivos diferentes cuando sea posible

### Escenario 3: "No puedo hacer push - me dice 'rejected'"

**Síntomas**:
```
! [rejected] main -> main (fetch first)
error: failed to push some refs to 'https://github.com/...'
```

**Causa**: Tu repositorio local está desactualizado

**Solución**:
```bash
# Actualizar tu repositorio local
git pull origin main

# Si hay conflictos, resuélvelos (ver escenario 2)
# Luego intenta push nuevamente
git push origin main
```

**Solución alternativa** (si tienes cambios locales importantes):
```bash
# Guardar tus cambios temporalmente
git stash

# Actualizar
git pull origin main

# Recuperar tus cambios
git stash pop

# Resolver conflictos si aparecen, luego
git add .
git commit -m "fix: resolver conflictos después de stash"
git push origin main
```

## 📁 Escenarios de Gestión de Archivos

### Escenario 4: "Agregué archivos que no debería subir"

**Archivos que NO debes subir**:
- `bin/` y `obj/` (archivos compilados)
- `.vs/` (configuración de Visual Studio)
- `*.user` (configuraciones personales)
- `.env` (variables de entorno)
- Bases de datos locales

**Si ya los subiste**:
```bash
# Remover del tracking pero mantener localmente
git rm --cached -r bin/
git rm --cached -r obj/
git rm --cached -r .vs/

# Agregar al .gitignore
echo "bin/" >> .gitignore
echo "obj/" >> .gitignore
echo ".vs/" >> .gitignore

# Confirmar cambios
git add .gitignore
git commit -m "fix: remover archivos innecesarios y actualizar .gitignore"
git push origin main
```

### Escenario 5: "Necesito cambiar el nombre de un archivo que ya está en GitHub"

**Solución**:
```bash
# Mover/renombrar archivo
git mv archivo-viejo.cs archivo-nuevo.cs

# Confirmar cambio
git commit -m "refactor: renombrar archivo-viejo.cs a archivo-nuevo.cs"
git push origin main
```

### Escenario 6: "Quiero deshacer mi último commit"

**Si NO has hecho push todavía**:
```bash
# Deshacer commit pero mantener cambios
git reset --soft HEAD~1

# Deshacer commit y cambios completamente
git reset --hard HEAD~1
```

**Si YA hiciste push**:
```bash
# Crear commit que revierte el anterior
git revert HEAD
git push origin main
```

## 🔄 Escenarios de Colaboración

### Escenario 7: "Mi compañero hizo cambios pero no los veo"

**Causa**: Tu repositorio local no está actualizado

**Solución**:
```bash
# Actualizar repositorio local
git pull origin main

# Verificar que tienes los últimos cambios
git log --oneline -5
```

### Escenario 8: "Dos personas trabajaron en la misma funcionalidad"

**Situación**: Sin querer, dos personas implementaron la misma función

**Solución**:
1. **Comunicarse inmediatamente** con el equipo
2. **Revisar ambas implementaciones**:
   ```bash
   # Ver diferencias entre commits
   git diff [commit1] [commit2]
   ```
3. **Decidir qué implementación usar** o combinar ambas
4. **Hacer refactor** si es necesario
5. **Documentar la decisión** en el commit

**Prevención**:
- Usar GitHub Issues para reclamar tareas
- Comunicación constante en el chat del equipo
- Daily standups

### Escenario 9: "El proyecto no funciona después de hacer pull"

**Síntomas**:
- Errores de compilación después de actualizar
- Faltan referencias o paquetes NuGet
- Base de datos no funciona

**Solución**:
```bash
# 1. Verificar que tienes todos los archivos
git status

# 2. Restaurar paquetes NuGet (en Visual Studio)
# Tools → NuGet Package Manager → Package Manager Console
Update-Package -reinstall

# 3. Limpiar y reconstruir
# Build → Clean Solution
# Build → Rebuild Solution

# 4. Verificar base de datos
# Revisar si hay nuevas migraciones
dotnet ef database update
```

## 🔧 Escenarios de Configuración

### Escenario 10: "Git me pide usuario y contraseña constantemente"

**Solución para Windows**:
```bash
# Configurar credential manager
git config --global credential.helper manager-core

# Primera vez te pedirá login, después se recordará
git push origin main
```

**Solución alternativa con token**:
1. Ve a GitHub → Settings → Developer Settings → Personal Access Tokens
2. Crea un token con permisos de repo
3. Usa el token como contraseña

### Escenario 11: "Mis commits aparecen con nombre/email incorrecto"

**Solución**:
```bash
# Verificar configuración actual
git config user.name
git config user.email

# Configurar correctamente (usar email de GitHub)
git config --global user.name "Tu Nombre"
git config --global user.email "tu-email@github.com"

# Para cambiar autor del último commit
git commit --amend --author="Tu Nombre <tu-email@github.com>"
```

### Escenario 12: "No puedo ver el repositorio o me dice 'access denied'"

**Causas y soluciones**:

1. **No aceptaste la invitación**:
   - Revisa tu email para la invitación de GitHub
   - Haz clic en "Accept Invitation"

2. **URL incorrecta**:
   ```bash
   # Verificar URL del repositorio
   git remote -v
   
   # Cambiar si es necesario
   git remote set-url origin https://github.com/usuario/proyecto-correcto.git
   ```

3. **Problemas de autenticación**:
   - Verifica que estás logueado en GitHub
   - Revisa tus credenciales

## 📊 Escenarios de Organización

### Escenario 13: "El historial de commits está muy desordenado"

**Problema**: Commits con mensajes poco descriptivos o muy frecuentes

**Prevención futura**:
- Usar formato estándar: `tipo: descripción`
- Commits atómicos (un cambio lógico por commit)
- Revisar cambios antes de hacer commit

**Para limpiar historial** (solo si todos están de acuerdo):
```bash
# Ver historial actual
git log --oneline

# Combinar últimos 3 commits en uno
git rebase -i HEAD~3
# En el editor, cambiar 'pick' por 'squash' para los commits que quieres combinar
```

### Escenario 14: "No sabemos quién hizo qué cambio"

**Para investigar cambios**:
```bash
# Ver quién modificó cada línea de un archivo
git blame nombre-archivo.cs

# Ver historial de un archivo específico
git log -p nombre-archivo.cs

# Ver cambios en un commit específico
git show [hash-del-commit]
```

### Escenario 15: "El repositorio está muy desorganizado"

**Reorganización**:
1. **Crear estructura de carpetas clara**:
   ```
   proyecto/
   ├── Controllers/
   ├── Models/
   ├── Views/
   ├── Data/
   ├── Scripts/
   └── Documentation/
   ```

2. **Mover archivos correctamente**:
   ```bash
   git mv archivo.cs Controllers/archivo.cs
   git commit -m "refactor: mover archivo a carpeta correcta"
   ```

3. **Actualizar .gitignore** si es necesario

## 🆘 Escenarios de Crisis

### Escenario 16: "El repositorio está completamente roto"

**Última opción - Reset completo**:
```bash
# CUIDADO: Esto elimina todos los cambios locales
git fetch origin
git reset --hard origin/main
```

**Opción más segura**:
```bash
# Hacer backup de cambios locales
git stash

# Actualizar desde GitHub
git pull origin main

# Si aún hay problemas, clonar nuevamente
cd ..
git clone https://github.com/usuario/proyecto.git proyecto-backup
```

### Escenario 17: "Accidentalmente hice push de información sensible"

**Información sensible**: contraseñas, API keys, datos personales

**Solución URGENTE**:
1. **Cambiar inmediatamente** todas las contraseñas/keys expuestas
2. **Remover del historial**:
   ```bash
   # Para archivo específico
   git filter-branch --force --index-filter \
   'git rm --cached --ignore-unmatch archivo-con-secretos.txt' \
   --prune-empty --tag-name-filter cat -- --all
   
   # Forzar push (PELIGROSO)
   git push origin --force --all
   ```
3. **Contactar al profesor** inmediatamente

## 📋 Checklist de Buenas Prácticas

### Antes de Empezar a Trabajar
- [ ] `git status` - Ver estado actual
- [ ] `git pull origin main` - Actualizar repositorio
- [ ] Verificar que no hay conflictos
- [ ] Comunicar al equipo qué vas a hacer

### Antes de Hacer Commit
- [ ] `git status` - Ver qué archivos cambiaron
- [ ] `git diff` - Revisar cambios específicos
- [ ] Probar que el código funciona
- [ ] Escribir mensaje descriptivo

### Antes de Hacer Push
- [ ] `git log --oneline -3` - Ver últimos commits
- [ ] Verificar que el mensaje es claro
- [ ] `git pull origin main` - Actualizar por última vez
- [ ] `git push origin main` - Subir cambios

### Al Final del Día
- [ ] Subir todos los cambios importantes
- [ ] Actualizar Issues si completaste tareas
- [ ] Comunicar progreso al equipo

## 🆘 Contactos de Emergencia

### Cuando Pedir Ayuda
1. **Al equipo**: Para problemas técnicos menores
2. **Al líder del proyecto**: Para conflictos o decisiones
3. **Al profesor**: Para problemas serios o académicos
4. **A GitHub Support**: Para problemas de la plataforma

### Información a Incluir al Pedir Ayuda
- **Qué estabas haciendo** cuando ocurrió el problema
- **Mensajes de error** completos (screenshot)
- **Comandos que ejecutaste**
- **Lo que esperabas que pasara**
- **Lo que realmente pasó**

## 📚 Recursos Adicionales

### Comandos de Referencia Rápida
```bash
# Estado y información
git status                  # Ver estado actual
git log --oneline          # Ver historial
git diff                   # Ver cambios no guardados
git remote -v              # Ver repositorio remoto

# Actualización y sincronización
git pull origin main       # Actualizar desde GitHub
git fetch origin           # Descargar cambios sin aplicar
git push origin main       # Subir cambios

# Cambios y commits
git add .                  # Agregar todos los cambios
git add archivo.cs         # Agregar archivo específico
git commit -m "mensaje"    # Crear commit
git commit --amend         # Modificar último commit

# Resolución de problemas
git stash                  # Guardar cambios temporalmente
git stash pop              # Recuperar cambios guardados
git reset --hard HEAD      # Descartar todos los cambios
git clean -fd              # Limpiar archivos no rastreados
```

### Enlaces Útiles
- [GitHub Docs](https://docs.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Visualizing Git](https://git-school.github.io/visualizing-git/)

---

**Recuerda**: Todos estos problemas son normales en el desarrollo de software. No te frustres, pide ayuda cuando la necesites, y aprende de cada error. ¡La experiencia te hará mejor desarrollador!