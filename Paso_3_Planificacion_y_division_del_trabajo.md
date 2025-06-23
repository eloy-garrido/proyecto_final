# Paso 3: Planificación y División del Trabajo

## Introducción

Una vez que todos los miembros del equipo tienen su entorno configurado y pueden trabajar con Git/GitHub, es momento de planificar el proyecto. Este paso es **crucial** para el éxito del trabajo grupal, ya que una buena planificación evita conflictos, duplicación de trabajo y asegura que todos contribuyan de manera efectiva.

## Objetivos de Este Paso

- 🎯 **Definir roles y responsabilidades** claras para cada miembro
- 📋 **Crear un plan de trabajo** detallado con fechas
- 🔄 **Establecer metodología** de trabajo colaborativo
- 📊 **Configurar herramientas** de seguimiento del proyecto
- 🤝 **Definir protocolos** de comunicación

## Paso 1: Reunión de Planificación Inicial

### Preparación para la Reunión

**Antes de la reunión, cada miembro debe**:
- ✅ Revisar completamente las instrucciones del proyecto final
- ✅ Tener acceso al repositorio y poder hacer commits
- ✅ Preparar ideas sobre qué tipo de CRUD quieren desarrollar
- ✅ Pensar en sus fortalezas y preferencias técnicas

### Agenda de la Reunión

**Duración recomendada**: 2-3 horas

1. **Definición del Proyecto** (30 min)
2. **Asignación de Roles** (45 min)
3. **División de Tareas** (60 min)
4. **Cronograma** (30 min)
5. **Protocolos de Trabajo** (15 min)

## Paso 2: Definir el Proyecto Específico

### Elegir el Dominio del CRUD

**Ejemplos de proyectos sugeridos**:
- 📚 **Sistema de Biblioteca** (libros, autores, préstamos)
- 🛒 **E-commerce Simple** (productos, categorías, pedidos)
- 🏥 **Gestión de Clínica** (pacientes, citas, doctores)
- 🎓 **Sistema Académico** (estudiantes, cursos, calificaciones)
- 🏨 **Gestión Hotelera** (habitaciones, reservas, huéspedes)
- 🚗 **Concesionaria** (vehículos, clientes, ventas)

### Definir Entidades Principales

**Para cada proyecto, identificar 3-4 entidades principales**:

**Ejemplo: Sistema de Biblioteca**
```
Entidades:
1. Libros (ID, Título, Autor, ISBN, Categoría, Stock)
2. Usuarios (ID, Nombre, Email, Teléfono, Tipo)
3. Préstamos (ID, LibroID, UsuarioID, FechaPrestamo, FechaDevolucion)
4. Categorías (ID, Nombre, Descripción)
```

### Documentar la Decisión

Crear un archivo `Documentation/definicion-proyecto.md`:

```markdown
# Definición del Proyecto

## Nombre del Proyecto
[Nombre del sistema]

## Descripción
[Descripción breve del sistema]

## Entidades Principales
1. **Entidad1**: [descripción y campos principales]
2. **Entidad2**: [descripción y campos principales]
3. **Entidad3**: [descripción y campos principales]

## Funcionalidades CRUD
- Crear, leer, actualizar, eliminar para cada entidad
- Relaciones entre entidades
- Validaciones específicas

## Decisiones Técnicas
- Framework: ASP.NET Core MVC
- Base de datos: SQL Server
- ORM: Entity Framework Core
- Frontend: Razor Views con Bootstrap
```

## Paso 3: Asignación de Roles

### Roles Sugeridos para el Equipo

#### 1. **Líder de Proyecto / Scrum Master**
**Responsabilidades**:
- Coordinar reuniones y comunicación
- Supervisar el cronograma
- Resolver conflictos y bloqueos
- Mantener actualizado el estado del proyecto
- Hacer merge de pull requests principales

**Perfil ideal**: Persona organizada, con buenas habilidades de comunicación

#### 2. **Arquitecto de Software / Backend Lead**
**Responsabilidades**:
- Diseñar la arquitectura general del sistema
- Implementar Models y DbContext
- Desarrollar Controllers principales
- Configurar Entity Framework
- Establecer patrones de código

**Perfil ideal**: Fuerte en lógica de programación y C#

#### 3. **Especialista en Base de Datos**
**Responsabilidades**:
- Diseñar el modelo de datos
- Crear scripts de base de datos
- Implementar migraciones
- Optimizar consultas
- Crear datos de prueba

**Perfil ideal**: Conocimientos de SQL y modelado de datos

#### 4. **Frontend Developer / UI/UX**
**Responsabilidades**:
- Diseñar e implementar Views
- Trabajar con Razor y Bootstrap
- Implementar validaciones del lado cliente
- Asegurar responsive design
- Crear una experiencia de usuario intuitiva

**Perfil ideal**: Habilidades en HTML, CSS, JavaScript

#### 5. **QA Tester / Documentador**
**Responsabilidades**:
- Probar todas las funcionalidades
- Documentar bugs y casos de prueba
- Crear la documentación técnica
- Escribir casos de uso
- Preparar material para la presentación

**Perfil ideal**: Detallista, buenas habilidades de escritura

#### 6. **DevOps / Integrador**
**Responsabilidades**:
- Gestionar configuraciones del proyecto
- Manejar deployment y configuraciones
- Integrar diferentes módulos
- Resolver conflictos de merge complejos
- Asegurar que todo funcione en conjunto

**Perfil ideal**: Conocimientos técnicos generales, resolución de problemas

### Matriz de Responsabilidades

Crear archivo `Documentation/roles-responsabilidades.md`:

```markdown
# Roles y Responsabilidades

| Miembro | Rol Principal | Rol Secundario | Responsabilidades Específicas |
|---------|---------------|----------------|-------------------------------|
| [Nombre1] | Líder de Proyecto | Frontend | Coordinación, Views de usuario |
| [Nombre2] | Backend Lead | QA | Models, Controllers, Testing |
| [Nombre3] | DB Specialist | DevOps | Base de datos, Deployment |
| [Nombre4] | Frontend Lead | Documentador | UI/UX, Documentación |
| [Nombre5] | QA/Tester | Backend | Testing, Controllers |
| [Nombre6] | Documentador | Frontend | Docs, Views secundarias |
```

## Paso 4: División Técnica del Trabajo

### Metodología: Desarrollo por Capas

**Fase 1: Fundación**
- Base de datos y Models
- Configuración inicial del proyecto
- Autenticación básica

**Fase 2: Backend**
- Controllers y lógica de negocio
- APIs internas
- Validaciones del servidor

**Fase 3: Frontend**
- Views y formularios
- Estilos y responsive design
- Validaciones del cliente

**Fase 4: Integración**
- Testing completo
- Corrección de bugs
- Documentación final

### Asignación Detallada por Entidad

**Ejemplo para Sistema de Biblioteca**:

```markdown
## Entidad: Libros
- **Model** → [Nombre - Backend Lead]
- **Controller** → [Nombre - Backend Lead]
- **Views** → [Nombre - Frontend Lead]
- **Testing** → [Nombre - QA Tester]

## Entidad: Usuarios
- **Model** → [Nombre - DB Specialist]
- **Controller** → [Nombre - Backend Support]
- **Views** → [Nombre - Frontend Support]
- **Testing** → [Nombre - QA Tester]

## Componentes Transversales
- **Autenticación** → [Nombre - Backend Lead]
- **Layout Principal** → [Nombre - Frontend Lead]
- **Base de Datos** → [Nombre - DB Specialist]
- **Documentación** → [Nombre - Documentador]
```

### Crear Issues en GitHub

Para cada tarea, crear un Issue:

1. **Ir a la pestaña "Issues"** en GitHub
2. **Crear Issues detallados**:

```markdown
Título: [Backend] Implementar Model de Libro

## Descripción
Crear el modelo de Libro con todas las propiedades necesarias

## Tareas
- [ ] Crear clase Book en Models/
- [ ] Definir propiedades (Id, Title, Author, ISBN, etc.)
- [ ] Agregar validaciones con Data Annotations
- [ ] Configurar relaciones con otras entidades
- [ ] Actualizar DbContext

## Criterios de Aceptación
- [ ] Modelo compila sin errores
- [ ] Validaciones funcionan correctamente
- [ ] Relaciones están bien definidas
- [ ] Código está documentado

## Asignado a
@username-del-responsable

## Etiquetas
backend, model, high-priority
```

## Paso 5: Cronograma Detallado

### Template de Cronograma

Crear archivo `Documentation/cronograma.md`:

```markdown
# Cronograma del Proyecto

## Semana 1: Planificación y Fundación
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Martes: Planificación
- [ ] Reunión de planificación inicial
- [ ] Definición del proyecto
- [ ] Asignación de roles
- [ ] Configuración del repositorio

### Miércoles-Viernes: Fundación
- [ ] Diseño de base de datos
- [ ] Configuración inicial del proyecto ASP.NET
- [ ] Implementación de Models básicos
- [ ] Setup de Entity Framework

**Entregables**:
- Diseño de base de datos
- Proyecto ASP.NET configurado
- Models básicos implementados

## Semana 2: Backend Core
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Miércoles: Controllers Base
- [ ] Implementar Controllers para entidades principales
- [ ] Configurar routing
- [ ] Implementar operaciones CRUD básicas

### Jueves-Viernes: Validaciones y Lógica
- [ ] Agregar validaciones del servidor
- [ ] Implementar lógica de negocio
- [ ] Testing de APIs

**Entregables**:
- Controllers funcionales
- Validaciones implementadas
- Testing básico completado

## Semana 3: Backend Avanzado
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Miércoles: Integración
- [ ] Integrar autenticación con CRUD
- [ ] Implementar relaciones entre entidades
- [ ] Manejo de errores

### Jueves-Viernes: Optimización
- [ ] Optimizar consultas de base de datos
- [ ] Implementar logging
- [ ] Testing completo del backend

**Entregables**:
- Backend completamente funcional
- Integración con autenticación
- Suite de testing

## Semana 4: Frontend Core
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Miércoles: Views Básicas
- [ ] Implementar Views para operaciones CRUD
- [ ] Crear formularios
- [ ] Configurar Bootstrap

### Jueves-Viernes: Navegación
- [ ] Implementar menús y navegación
- [ ] Crear layout principal
- [ ] Responsive design básico

**Entregables**:
- Views funcionales para todas las entidades
- Navegación completa
- Design responsive

## Semana 5: Frontend Avanzado
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Miércoles: UX/UI
- [ ] Mejorar diseño visual
- [ ] Implementar validaciones del cliente
- [ ] Mensajes de confirmación y error

### Jueves-Viernes: Integración Frontend-Backend
- [ ] Testing de integración completa
- [ ] Corrección de bugs de UI
- [ ] Optimización de performance

**Entregables**:
- UI completa y pulida
- Validaciones del cliente
- Sistema completamente integrado

## Semana 6: Testing y Documentación
**Fechas**: [DD/MM] - [DD/MM]

### Lunes-Miércoles: Testing Final
- [ ] Testing completo del sistema
- [ ] Corrección de bugs finales
- [ ] Testing de casos edge
- [ ] Performance testing

### Jueves-Viernes: Documentación y Presentación
- [ ] Completar documentación técnica
- [ ] Crear manual de usuario
- [ ] Preparar presentación
- [ ] Ensayo de presentación

**Entregables**:
- Sistema completamente funcional
- Documentación completa
- Presentación preparada
- Proyecto listo para entrega
```

## Paso 6: Protocolos de Comunicación

### Canales de Comunicación

1. **GitHub Issues**: Para tareas específicas y seguimiento
2. **WhatsApp/Discord**: Para comunicación rápida diaria
3. **Reuniones virtuales**: Para sincronización semanal
4. **Email**: Para comunicación formal con el profesor

### Reuniones Regulares

#### Daily Standup (15 min diarios)
**Formato por WhatsApp o reunión rápida**:
- ¿Qué hice ayer?
- ¿Qué haré hoy?
- ¿Tengo algún bloqueo?

#### Weekly Review (1 hora semanal)
**Formato de reunión virtual**:
- Revisar progreso de la semana
- Resolver bloqueos
- Planificar la siguiente semana
- Actualizar cronograma si es necesario

### Protocolo de Commits y Pull Requests

```markdown
## Reglas de Commits
1. Siempre hacer `git pull` antes de trabajar
2. Commits pequeños y frecuentes
3. Mensajes descriptivos con formato: `tipo: descripción`
4. Probar código antes de hacer push

## Proceso de Pull Requests (Para cambios importantes)
1. Crear feature branch: `git checkout -b feature/nueva-funcionalidad`
2. Desarrollar y hacer commits
3. Push de la branch: `git push origin feature/nueva-funcionalidad`
4. Crear Pull Request en GitHub
5. Solicitar revisión de al menos un compañero
6. Hacer merge después de aprobación
```

## Paso 7: Configuración de Herramientas de Proyecto

### GitHub Projects

1. **Ir a la pestaña "Projects"** en el repositorio
2. **Crear nuevo proyecto**: "Proyecto Final CRUD"
3. **Configurar columnas**:
   - 📋 **Backlog** (tareas planificadas)
   - 🔄 **In Progress** (en desarrollo)
   - 👀 **In Review** (esperando revisión)
   - ✅ **Done** (completadas)

### Labels para Issues

Configurar etiquetas para organizar mejor:
- `priority-high` 🔴 - Tareas críticas
- `priority-medium` 🟡 - Tareas importantes
- `priority-low` 🟢 - Tareas opcionales
- `backend` 💾 - Relacionado con backend
- `frontend` 🎨 - Relacionado con frontend
- `database` 🗃️ - Relacionado con base de datos
- `documentation` 📝 - Documentación
- `bug` 🐛 - Errores a corregir
- `enhancement` ✨ - Mejoras

### Milestones

Crear milestones para clase:
- 🎯 **Clase 1**: Planificación y Fundación
- 🎯 **clase 2**: Backend Core
- 🎯 **clase 3**: Backend Avanzado
- 🎯 **clase 4**: Frontend Core
- 🎯 **clase 5**: Frontend Avanzado
- 🎯 **clase 6**: Testing y Documentación

## Paso 8: Documentar Todo

### Crear Archivos de Documentación

Todos estos archivos van en la carpeta `Documentation/`:

1. **`definicion-proyecto.md`** - Qué van a desarrollar
2. **`roles-responsabilidades.md`** - Quién hace qué
3. **`cronograma.md`** - Cuándo se hace cada cosa
4. **`protocolos-trabajo.md`** - Cómo trabajamos juntos
5. **`actas-reuniones.md`** - Registro de reuniones importantes

### Template para Actas de Reuniones

```markdown
# Acta de Reunión - [Fecha]

## Participantes
- [Nombre 1] - [Rol]
- [Nombre 2] - [Rol]
- ...

## Agenda
1. [Tema 1]
2. [Tema 2]
3. ...

## Decisiones Tomadas
- **Decisión 1**: [Descripción y justificación]
- **Decisión 2**: [Descripción y justificación]

## Tareas Asignadas
| Tarea | Responsable | Fecha Límite |
|-------|-------------|--------------|
| [Tarea 1] | [Nombre] | [DD/MM] |
| [Tarea 2] | [Nombre] | [DD/MM] |

## Próxima Reunión
- **Fecha**: [DD/MM/YYYY]
- **Hora**: [HH:MM]
- **Agenda preliminar**: [Temas a tratar]

## Observaciones
[Cualquier nota adicional importante]
```

## Verificación del Paso 3

Antes de continuar al desarrollo, verifica que:

✅ **Proyecto definido** - Saben exactamente qué van a desarrollar  
✅ **Roles asignados** - Cada persona sabe sus responsabilidades  
✅ **Tareas divididas** - El trabajo está fragmentado en tareas manejables  
✅ **Cronograma creado** - Tienen fechas claras para cada entregable  
✅ **Issues creados** - Tareas están documentadas en GitHub  
✅ **Protocolos establecidos** - Saben cómo van a trabajar juntos  
✅ **Herramientas configuradas** - Projects, labels, milestones están listos  
✅ **Documentación inicial** - Decisiones importantes están documentadas  

## Próximos Pasos

Con la planificación completa:

1. **Comenzar el desarrollo** siguiendo el cronograma
2. **Implementar daily standups** para mantener comunicación
3. **Usar GitHub Issues** para trackear el progreso
4. **Hacer reuniones semanales** de revisión
5. **Mantener documentación** actualizada

---

**Recuerda**: "Un proyecto bien planificado está medio terminado". La inversión de tiempo en esta etapa se recuperará con creces durante el desarrollo.

**Siguiente fase**: Comenzar con el desarrollo siguiendo el plan establecido

## Recursos Adicionales

### Plantillas de Documentos
- [Template de Casos de Uso](Documentation/template-casos-uso.md)
- [Template de Manual de Usuario](Documentation/template-manual-usuario.md)
- [Template de Documentación Técnica](Documentation/template-doc-tecnica.md)

### Herramientas Recomendadas
- **Draw.io**: Para diagramas de base de datos
- **Figma**: Para diseños de UI (opcional)
- **Trello**: Como alternativa a GitHub Projects
- **Discord**: Para reuniones de voz durante desarrollo