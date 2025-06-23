# Paso 1: Creando el Repositorio en GitHub

## Introducción

GitHub es una plataforma que nos permite trabajar colaborativamente en proyectos de código, mantener un historial de cambios y coordinar el trabajo en equipo. En este documento aprenderás los primeros pasos para configurar el repositorio de tu proyecto final.

## ¿Qué es un Repositorio?

Un **repositorio** (o "repo") es como una carpeta especial que:
- Guarda todo el código de tu proyecto
- Mantiene un historial de todos los cambios realizados
- Permite que varias personas trabajen en el mismo proyecto
- Funciona como una "copia de seguridad" en la nube

## Paso 1: Designar al Administrador del Repositorio

### ¿Quién debe ser el administrador?

**Recomendación**: El líder del proyecto o la persona más organizada del equipo debería ser el administrador inicial. Esta persona será responsable de:

✅ Crear el repositorio inicial  
✅ Configurar los permisos del equipo  
✅ Establecer la estructura básica del proyecto  
✅ Invitar a todos los miembros del equipo  

> **Importante**: Ser administrador NO significa hacer todo el trabajo. Es solo un rol organizacional inicial.

### Responsabilidades del Administrador

1. **Configuración inicial** del repositorio
2. **Invitar a todos los miembros** del equipo
3. **Establecer las reglas** básicas del proyecto
4. **Resolver conflictos** cuando sea necesario
5. **Mantener organizado** el repositorio

## Paso 2: Crear el Repositorio en GitHub

### Instrucciones Detalladas

1. **Inicia sesión** en [GitHub.com](https://github.com)

2. **Haz clic en el botón "New"** (verde) o en el "+" en la esquina superior derecha

3. **Configura tu repositorio**:
   ```
   Repository name: proyecto-final-[nombre-curso]
   Description: Sistema CRUD con MVC en C# .NET - Proyecto Final
   Visibility: Private (para proteger su trabajo durante el desarrollo)
   Initialize this repository with:
   ☑️ Add a README file
   ☑️ Add .gitignore (seleccionar: VisualStudio)
   ☐ Choose a license (dejar vacío por ahora)
   ```

4. **Haz clic en "Create repository"**

## Paso 3: Configurar Permisos del Equipo

### Configuración Recomendada: Acceso Completo para Todos

Para facilitar el aprendizaje y evitar bloqueos, **todos los miembros tendrán permisos de "Write"**, lo que significa:

✅ Pueden hacer push directamente  
✅ Pueden crear y eliminar branches  
✅ Pueden hacer merge de pull requests  
✅ Pueden editar la configuración del repositorio  

### Pasos para Invitar al Equipo

1. **Ve a la pestaña "Settings"** de tu repositorio

2. **Haz clic en "Collaborators and teams"** en el menú lateral

3. **Haz clic en "Add people"**

4. **Para cada miembro del equipo**:
   - Ingresa su **username de GitHub** o **email**
   - Selecciona el rol: **"Write"**
   - Haz clic en **"Add [username] to this repository"**

5. **Cada miembro recibirá una invitación** por email que debe aceptar

### Verificación de Permisos

Todos los miembros deberían poder:
- Ver el repositorio
- Clonar el código
- Hacer commits y push
- Crear branches
- Hacer pull requests

## Paso 4: Configuración Inicial del Proyecto

### Estructura Básica de Carpetas

El administrador debe crear la estructura básica:

```
proyecto-final/
├── README.md
├── .gitignore
├── Documentation/
│   ├── README.md
│   └── casos-de-uso.md
├── Scripts/
│   └── README.md
└── src/
    └── README.md
```

### Comandos Básicos para el Administrador

```bash
# Clonar el repositorio recién creado
git clone https://github.com/username/proyecto-final-nombre-curso.git

# Entrar al directorio
cd proyecto-final-nombre-curso

# Crear las carpetas básicas
mkdir Documentation Scripts src

# Crear archivos README en cada carpeta
echo "# Documentación del Proyecto" > Documentation/README.md
echo "# Scripts de Base de Datos" > Scripts/README.md
echo "# Código Fuente" > src/README.md

# Agregar cambios
git add .

# Hacer commit
git commit -m "feat: estructura inicial del proyecto"

# Subir cambios
git push origin main
```

## Paso 5: Comunicación del Equipo

### Información que Debe Compartir el Administrador

Una vez creado el repositorio, compartir con el equipo:

1. **URL del repositorio**: `https://github.com/username/proyecto-final-nombre-curso`
2. **Instrucciones de clonado**: Comando `git clone`
3. **Reglas básicas** de trabajo (ver siguiente sección)

### Reglas Básicas de Trabajo en Equipo

📋 **SIEMPRE hacer `git pull` antes de empezar a trabajar**  
📋 **Hacer commits frecuentes con mensajes descriptivos**  
📋 **Comunicar al equipo cuando vayas a trabajar en algo específico**  
📋 **Probar tu código antes de hacer push**  
📋 **Avisar si encuentras problemas o errores**  

## Configuraciones Adicionales Recomendadas

### 1. Protección de la Rama Main (Opcional para Principiantes)

Si el equipo se siente cómodo, pueden configurar:
- Requerir pull requests para cambios en `main`
- Requerir revisión de código

### 2. Templates para Issues y Pull Requests

Crear templates básicos para organizar mejor el trabajo:

**`.github/ISSUE_TEMPLATE.md`**:
```markdown
## Descripción
Breve descripción de la tarea o problema

## Tareas
- [ ] Tarea 1
- [ ] Tarea 2

## Criterios de Aceptación
- [ ] Criterio 1
- [ ] Criterio 2
```

### 3. Etiquetas (Labels) Útiles

Crear labels para organizar el trabajo:
- `bug` - Para reportar errores
- `feature` - Para nuevas funcionalidades
- `documentation` - Para tareas de documentación
- `help wanted` - Cuando necesitas ayuda del equipo

## Troubleshooting Común

### Problema: "No puedo hacer push"
**Solución**: 
1. Verifica que aceptaste la invitación del repositorio
2. Asegúrate de haber configurado tu Git con tu email de GitHub
3. Intenta hacer `git pull` antes del `git push`

### Problema: "Conflictos de merge"
**Solución**:
1. No entres en pánico
2. Comunícate con tu equipo
3. Revisa la sección de resolución de conflictos en el siguiente documento

### Problema: "No encuentro el repositorio"
**Solución**:
1. Verifica que el administrador te haya invitado
2. Revisa tu email para la invitación
3. Asegúrate de estar usando el username correcto

## Verificación Final

Antes de continuar al siguiente paso, asegúrate de que:

✅ El repositorio está creado y configurado  
✅ Todos los miembros han sido invitados y aceptaron  
✅ Todos pueden clonar el repositorio  
✅ La estructura básica está creada  
✅ Las reglas de trabajo están claras para todo el equipo  

## Próximos Pasos

Una vez completado este paso:

1. **Todos los miembros** deben clonar el repositorio
2. **Configurar Git** en sus máquinas locales
3. **Hacer su primer commit** de prueba
4. **Comenzar con la planificación** del proyecto

---

## Comandos Git Básicos de Referencia Rápida

```bash
# Clonar el repositorio
git clone [URL-del-repositorio]

# Verificar estado
git status

# Actualizar desde GitHub
git pull

# Agregar cambios
git add .

# Hacer commit
git commit -m "descripción del cambio"

# Subir cambios
git push

# Ver historial
git log --oneline
```

---

**Recuerda**: Si tienes dudas o problemas, ¡comunícate con tu equipo! El aprendizaje colaborativo es parte del proceso.

**Siguiente documento**: "Paso 2: Configuración Local y Primeros Commits"