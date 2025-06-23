# Proyecto Final - Sistema CRUD con MVC en C# .NET

## Descripción General

Este proyecto final tiene como objetivo que los estudiantes desarrollen un sistema CRUD (Create, Read, Update, Delete) completo utilizando el patrón MVC en C# .NET, basándose en el proyecto anterior de login-mvc. El trabajo es **grupal** y cada miembro del equipo debe contribuir activamente al desarrollo, documentación y presentación del proyecto.

## Objetivos del Proyecto

### Objetivos Técnicos
- Implementar un sistema CRUD funcional sobre la base del proyecto login-mvc
- Desarrollar la arquitectura completa: Models, Views, Controllers
- Diseñar y implementar la base de datos con todas las tablas necesarias
- Crear interfaces de usuario intuitivas y funcionales
- Integrar el sistema de autenticación con el CRUD

### Objetivos Transversales
- Desarrollar habilidades de trabajo en equipo
- Aplicar metodologías de desarrollo colaborativo
- Mejorar capacidades de documentación técnica
- Fortalecer habilidades de presentación y comunicación

## Especificaciones Técnicas

### Funcionalidades Requeridas

1. **Sistema de Autenticación**
   - Utilizar como base el proyecto login-mvc desarrollado anteriormente
   - Implementar control de acceso al sistema CRUD

2. **Sistema CRUD Completo**
   - **Create**: Formularios para crear nuevos registros
   - **Read**: Listados y vistas de detalle de registros
   - **Update**: Formularios de edición de registros existentes
   - **Delete**: Funcionalidad de eliminación con confirmación

3. **Base de Datos**
   - Diseño normalizado de tablas
   - Relaciones apropiadas entre entidades
   - Implementación de constraints y validaciones
   - Scripts de creación y datos de prueba

4. **Interfaz de Usuario**
   - Diseño responsive y user-friendly
   - Validaciones del lado cliente y servidor
   - Mensajes de confirmación y error apropiados
   - Navegación intuitiva

## Estructura del Proyecto a Entregar

### 1. Documentación Técnica
- **README.md**: Descripción general del proyecto e instrucciones de instalación
- **Documentación de la Base de Datos**: Diagrama ER, diccionario de datos
- **Manual de Usuario**: Guía de uso del sistema
- **Documentación Técnica**: Arquitectura del sistema, patrones utilizados
- **Casos de Uso**: Descripción detallada de todas las funcionalidades

### 2. Documentación del Proceso
- **Bitácora de Desarrollo**: Registro de avances y decisiones técnicas
- **División de Tareas**: Asignación de responsabilidades por miembro
- **Control de Versiones**: Historial de commits y contribuciones

## Recomendaciones para la Fragmentación de Tareas

### División Macro de Responsabilidades

1. **Líder de Proyecto/Arquitecto**
   - Definición de la arquitectura general
   - Coordinación entre equipos
   - Revisión de código y merge de branches

2. **Especialista en Base de Datos**
   - Diseño del modelo de datos
   - Creación de scripts SQL
   - Optimización de consultas

3. **Desarrollador Backend**
   - Implementación de Controllers
   - Desarrollo de Models y lógica de negocio
   - Configuración de Entity Framework

4. **Desarrollador Frontend**
   - Diseño e implementación de Views
   - Estilos CSS y responsividad
   - Validaciones del lado cliente

5. **Especialista en Testing/QA**
   - Pruebas funcionales
   - Documentación de bugs
   - Validación de casos de uso

6. **Documentador/Analista**
   - Creación de documentación técnica
   - Elaboración de manuales
   - Preparación de la presentación

## Gestión del Trabajo en GitHub

### Estrategia de Branching

1. **Branch Principal (main/master)**
   - Solo código estable y testeado
   - Requiere pull request y revisión

2. **Branch de Desarrollo (develop)**
   - Integración de features
   - Base para nuevas funcionalidades

3. **Feature Branches**
   - Una branch por funcionalidad
   - Nomenclatura: `feature/nombre-funcionalidad`
   - Ejemplo: `feature/crud-productos`

4. **Hotfix Branches**
   - Para correcciones urgentes
   - Nomenclatura: `hotfix/descripcion-error`

### Buenas Prácticas de Commits

1. **Mensajes Descriptivos**
   ```
   feat: agregar funcionalidad CRUD para productos
   fix: corregir validación en formulario de usuario
   docs: actualizar documentación de instalación
   style: mejorar diseño responsive del listado
   ```

2. **Commits Atómicos**
   - Un commit por cambio lógico
   - Evitar commits masivos

3. **Revisión de Código**
   - Todo pull request debe ser revisado
   - Al menos un approve antes del merge

### Distribución del Trabajo

1. **Asignación por Issues**
   - Crear issues para cada tarea
   - Asignar responsables
   - Usar labels para categorizar

2. **Sincronización Regular**
   - Pulls diarios desde develop
   - Comunicación constante del equipo
   - Reuniones de sincronización

### Consideraciones de Calidad

1. **Estándares de Código**
   - Seguir convenciones de nomenclatura C#
   - Comentarios en código
   - Manejo apropiado de excepciones

2. **Testing**
   - Pruebas de todas las funcionalidades CRUD
   - Validación de casos edge
   - Testing de la integración

3. **Seguridad**
   - Validación de inputs
   - Protección contra SQL injection
   - Manejo seguro de sesiones

## Entregables

### 1. Repositorio GitHub (40%)
- Código fuente completo y funcional
- Historial de commits de todos los miembros
- README con instrucciones de instalación
- Documentación técnica

### 2. Proyecto Escrito (35%)
- Documento de análisis y diseño
- Manual de usuario
- Documentación técnica completa
- Casos de uso detallados
- Diagramas de base de datos

### 3. Presentación (25%)
- Presentación de 15-20 minutos
- Demo funcional del sistema
- Explicación de la arquitectura
- Reflexiones sobre el proceso de desarrollo
- Solo 2 personas presentan, pero afecta a todo el equipo

## Rúbrica de Evaluación

### Contribuciones en GitHub (40 puntos)

| Criterio | Excelente (4) | Bueno (3) | Satisfactorio (2) | Insuficiente (1) |
|----------|---------------|-----------|-------------------|------------------|
| **Cantidad de Commits** | +20 commits significativos | 15-19 commits | 10-14 commits | <10 commits |
| **Calidad de Commits** | Mensajes descriptivos, cambios atómicos | Buenos mensajes, cambios coherentes | Mensajes aceptables | Mensajes poco descriptivos |
| **Distribución Temporal** | Commits consistentes durante todo el proyecto | Buena distribución | Distribución irregular | Commits concentrados al final |
| **Tipo de Contribuciones** | Código, documentación, revisiones | Principalmente código y algo de docs | Solo código | Contribuciones mínimas |

### Funcionalidad del Sistema (30 puntos)

| Criterio | Excelente (4) | Bueno (3) | Satisfactorio (2) | Insuficiente (1) |
|----------|---------------|-----------|-------------------|------------------|
| **CRUD Completo** | Todas las operaciones funcionan perfectamente | Funciona con errores menores | Funciona parcialmente | No funciona o errores graves |
| **Integración con Login** | Integración perfecta y segura | Buena integración | Integración básica | No integrado o inseguro |
| **Base de Datos** | Diseño normalizado y eficiente | Buen diseño con mejoras menores | Diseño básico funcional | Diseño deficiente |
| **Interfaz de Usuario** | UI intuitiva y responsive | Buena UI con mejoras menores | UI básica funcional | UI deficiente |

### Documentación Escrita (20 puntos)

| Criterio | Excelente (4) | Bueno (3) | Satisfactorio (2) | Insuficiente (1) |
|----------|---------------|-----------|-------------------|------------------|
| **Completitud** | Documentación completa y detallada | Buena documentación | Documentación básica | Documentación incompleta |
| **Calidad Técnica** | Diagramas claros, casos de uso detallados | Buena calidad técnica | Calidad aceptable | Calidad deficiente |
| **Manual de Usuario** | Manual claro y completo | Buen manual | Manual básico | Manual incompleto |
| **Presentación** | Formato profesional, sin errores | Buena presentación | Presentación aceptable | Presentación deficiente |

### Presentación (10 puntos)

| Criterio | Excelente (4) | Bueno (3) | Satisfactorio (2) | Insuficiente (1) |
|----------|---------------|-----------|-------------------|------------------|
| **Demo Técnico** | Demo fluido y completo | Buena demo con errores menores | Demo básico | Demo con errores graves |
| **Explicación Técnica** | Explicación clara y profunda | Buena explicación | Explicación básica | Explicación deficiente |
| **Organización** | Presentación bien estructurada | Buena organización | Organización básica | Mal organizada |
| **Tiempo** | Manejo perfecto del tiempo | Buen manejo del tiempo | Se ajusta al tiempo | No respeta el tiempo |

## Consideraciones Finales

Este proyecto no solo evaluará sus conocimientos técnicos en C# .NET y MVC, sino también sus habilidades para trabajar en equipo, gestionar un proyecto de software y comunicar resultados técnicos. Como futuros profesionales de la informática, estas competencias son fundamentales para su éxito profesional.

**Recuerden**: La colaboración efectiva, la comunicación clara y la organización del trabajo son tan importantes como la calidad técnica del código. ¡Éxito en su proyecto!