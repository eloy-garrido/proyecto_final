# Paso 2: Configuración Local y Primeros Commits

## Introducción

Ahora que el repositorio está creado en GitHub, cada miembro del equipo debe configurar su entorno local para trabajar con Git y GitHub. Este documento te guiará paso a paso para clonar el repositorio, configurar Git y hacer tus primeros commits.

## Requisitos Previos

Antes de continuar, asegúrate de que:
- ✅ Tienes una cuenta de GitHub activa
- ✅ Has aceptado la invitación al repositorio del proyecto
- ✅ Tienes Git instalado en tu computadora
- ✅ Tienes Visual Studio o VS Code instalado

## Paso 1: Verificar Instalación de Git

### En Windows

1. **Abre la terminal** (Command Prompt o PowerShell)
2. **Ejecuta el comando**:
   ```bash
   git --version
   ```
3. **Deberías ver algo como**: `git version 2.x.x`

### Si Git no está instalado

1. **Descarga Git** desde: [https://git-scm.com/download/windows](https://git-scm.com/download/windows)
2. **Instala con configuración por defecto**
3. **Reinicia tu terminal** y verifica nuevamente

## Paso 2: Configurar Git por Primera Vez

### Configuración Básica Obligatoria

**Importante**: Usa el **mismo email** que tienes registrado en GitHub.

```bash
# Configurar tu nombre (reemplaza con tu nombre real)
git config --global user.name "Tu Nombre Completo"

# Configurar tu email (DEBE ser el mismo de GitHub)
git config --global user.email "tu.email@ejemplo.com"

# Configurar editor por defecto (opcional)
git config --global core.editor "code --wait"
```

### Verificar Configuración

```bash
# Ver toda la configuración
git config --list

# Ver solo nombre y email
git config user.name
git config user.email
```

### Configuración Adicional Recomendada

```bash
# Evitar problemas con saltos de línea
git config --global core.autocrlf true

# Configurar colores en la terminal
git config --global color.ui auto

# Configurar comportamiento de push
git config --global push.default simple
```

## Paso 3: Clonar el Repositorio

### Obtener la URL del Repositorio

1. **Ve al repositorio** en GitHub
2. **Haz clic en el botón verde "Code"**
3. **Copia la URL HTTPS** (algo como: `https://github.com/usuario/proyecto-final-curso.git`)

### Clonar en tu Computadora

```bash
# Navegar a donde quieres guardar el proyecto
cd C:\Users\TuUsuario\Documents

# Clonar el repositorio (reemplaza con tu URL real)
git clone https://github.com/usuario/proyecto-final-curso.git

# Entrar al directorio del proyecto
cd proyecto-final-curso
```

### Verificar que Funciona

```bash
# Ver el estado del repositorio
git status

# Ver el historial de commits
git log --oneline

# Ver archivos en el directorio
dir
```

## Paso 4: Primer Commit de Prueba

### Crear un Archivo de Identificación

Cada miembro del equipo debe crear un archivo para identificarse:

```bash
# Crear un archivo con tu nombre
echo "# Mi nombre es [Tu Nombre]" > mi-identificacion.md
echo "## Rol en el proyecto: [Tu Rol]" >> mi-identificacion.md
echo "## Fecha de configuración: $(Get-Date)" >> mi-identificacion.md
```

**En Linux/Mac**:
```bash
echo "# Mi nombre es [Tu Nombre]" > mi-identificacion.md
echo "## Rol en el proyecto: [Tu Rol]" >> mi-identificacion.md
echo "## Fecha de configuración: $(date)" >> mi-identificacion.md
```

### Agregar y Hacer Commit

```bash
# Ver qué archivos han cambiado
git status

# Agregar el archivo al staging area
git add mi-identificacion.md

# Verificar que está agregado
git status

# Hacer el commit con mensaje descriptivo
git commit -m "feat: agregar archivo de identificación de [Tu Nombre]"

# Subir los cambios a GitHub
git push origin main
```

## Paso 5: Flujo de Trabajo Básico

### Rutina Diaria de Trabajo

**ANTES de empezar a trabajar SIEMPRE**:
```bash
# 1. Actualizar tu repositorio local
git pull origin main

# 2. Verificar estado
git status
```

**DESPUÉS de hacer cambios**:
```bash
# 1. Ver qué archivos cambiaron
git status

# 2. Agregar archivos específicos o todos
git add archivo-especifico.cs
# O agregar todos los cambios
git add .

# 3. Hacer commit con mensaje descriptivo
git commit -m "tipo: descripción clara del cambio"

# 4. Subir cambios
git push origin main
```

### Tipos de Commit Recomendados

Use estos prefijos en tus mensajes de commit:

- `feat:` - Nueva funcionalidad
- `fix:` - Corrección de errores
- `docs:` - Cambios en documentación
- `style:` - Cambios de formato (espacios, puntos y comas, etc.)
- `refactor:` - Reestructuración de código sin cambiar funcionalidad
- `test:` - Agregar o modificar pruebas

**Ejemplos**:
```bash
git commit -m "feat: agregar modelo de Usuario"
git commit -m "fix: corregir validación en formulario de login"
git commit -m "docs: actualizar README con instrucciones de instalación"
```

## Paso 6: Trabajar con Visual Studio

### Abrir el Proyecto

```bash
# Desde la terminal, abrir VS Code en el directorio actual
code .

# O abrir Visual Studio
start devenv .
```

### Configurar .gitignore para C#

El archivo `.gitignore` ya debería estar configurado, pero verifica que incluya:

```gitignore
# Visual Studio
.vs/
bin/
obj/
*.user
*.suo

# .NET Core
project.lock.json
project.fragment.lock.json
artifacts/

# Archivos temporales
*.tmp
*.log
```

### Integración con VS Code

Si usas VS Code, instala estas extensiones útiles:
- **GitLens** - Para mejor visualización de Git
- **Git History** - Para ver historial gráfico
- **C# for Visual Studio Code** - Para desarrollo en C#

## Paso 7: Resolución de Problemas Comunes

### Problema: "Permission denied" o "Authentication failed"

**Solución**:
1. Verifica que aceptaste la invitación al repositorio
2. Configura credenciales de GitHub:

```bash
# En Windows, usar Git Credential Manager
git config --global credential.helper manager-core

# Primera vez te pedirá login de GitHub
git push origin main
```

### Problema: "Your branch is behind"

**Solución**:
```bash
# Actualizar tu repositorio local
git pull origin main

# Si hay conflictos, resuélvelos y luego:
git add .
git commit -m "fix: resolver conflictos de merge"
git push origin main
```

### Problema: "No changes added to commit"

**Solución**:
```bash
# Primero agregar archivos al staging area
git add .

# Luego hacer commit
git commit -m "tu mensaje aquí"
```

### Problema: Conflictos de Merge

**Cuando aparezcan conflictos**:

1. **No entres en pánico** - Los conflictos son normales
2. **Comunícate con tu equipo** inmediatamente
3. **Abre los archivos en conflicto** en tu editor
4. **Busca las marcas de conflicto**:
   ```
   <<<<<<< HEAD
   Tu código
   =======
   Código de otro compañero
   >>>>>>> rama-o-commit
   ```
5. **Edita manualmente** para resolver el conflicto
6. **Elimina las marcas** `<<<<<<<`, `=======`, `>>>>>>>`
7. **Guarda el archivo**
8. **Agrega y confirma**:
   ```bash
   git add archivo-resuelto.cs
   git commit -m "fix: resolver conflicto en archivo-resuelto.cs"
   git push origin main
   ```

## Paso 8: Buenas Prácticas

### Commits Frecuentes y Pequeños

✅ **Haz commits pequeños y frecuentes**  
❌ **Evita commits gigantes con muchos cambios**  

### Mensajes Descriptivos

✅ **Buenos mensajes**:
- `feat: agregar validación de email en registro`
- `fix: corregir error de null reference en login`
- `docs: actualizar documentación de instalación`

❌ **Malos mensajes**:
- `cambios`
- `fix`
- `actualizaciones varias`

### Sincronización Regular

```bash
# Al menos 2-3 veces al día
git pull origin main
```

### Comunicación

- **Avisa cuando vayas a trabajar** en algo específico
- **Comunica si encuentras problemas**
- **Comparte tu progreso** regularmente

## Verificación del Paso 2

Antes de continuar, verifica que:

✅ Git está configurado con tu nombre y email  
✅ Has clonado exitosamente el repositorio  
✅ Puedes hacer `git status` sin errores  
✅ Has hecho tu primer commit de identificación  
✅ Puedes hacer `git push` sin problemas  
✅ Tu commit aparece en GitHub  
✅ Entiendes el flujo básico de trabajo  

## Comandos de Referencia Rápida

```bash
# Flujo básico diario
git pull origin main        # Actualizar
git status                  # Ver estado
git add .                   # Agregar cambios
git commit -m "mensaje"     # Confirmar cambios
git push origin main        # Subir cambios

# Comandos útiles
git log --oneline          # Ver historial
git diff                   # Ver diferencias
git reset HEAD archivo     # Quitar archivo del staging
git checkout -- archivo   # Descartar cambios locales
```

## Próximos Pasos

Una vez completado este paso:

1. **Todos los miembros** deberían tener su entorno configurado
2. **Practicar** el flujo básico de trabajo
3. **Comenzar con la planificación** detallada del proyecto
4. **Establecer horarios** de trabajo colaborativo

---

**Recuerda**: La práctica hace al maestro. No tengas miedo de hacer commits frecuentes mientras aprendes.

**Siguiente documento**: "Paso 3: Planificación y División del Trabajo"