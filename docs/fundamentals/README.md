# Fundamentos de QA

## ¿Qué es el Aseguramiento de Calidad?

El Aseguramiento de Calidad (QA) es un proceso sistemático para determinar si un producto o servicio cumple con los requisitos especificados. Se enfoca en mejorar y estabilizar la producción y los procesos asociados para evitar o al menos minimizar los problemas que conducen a defectos.

### Objetivos Clave de QA
- Asegurar que la calidad del producto cumpla con las expectativas del cliente
- Identificar defectos antes del lanzamiento a producción
- Reducir costos al detectar problemas tempranamente
- Mejorar los procesos de desarrollo
- Construir confianza del cliente

## Tipos de Pruebas

### 1. Pruebas Funcionales
Valida que el software funcione según los requisitos.
- **Pruebas Unitarias**: Prueba de componentes individuales
- **Pruebas de Integración**: Prueba de interacciones entre componentes
- **Pruebas de Sistema**: Prueba del sistema completo
- **Pruebas de Aceptación**: Validación contra requisitos del negocio

### 2. Pruebas No Funcionales
Se enfoca en aspectos como rendimiento, usabilidad y confiabilidad.
- **Pruebas de Rendimiento**: Velocidad, escalabilidad, estabilidad
- **Pruebas de Seguridad**: Vulnerabilidades y amenazas
- **Pruebas de Usabilidad**: Experiencia del usuario
- **Pruebas de Compatibilidad**: Diferentes entornos

### 3. Pruebas de Mantenimiento
- **Pruebas de Regresión**: Asegurar que los cambios no rompan funcionalidad existente
- **Pruebas de Humo**: Verificaciones básicas de funcionalidad
- **Pruebas de Sanidad**: Verificación enfocada de funcionalidad específica

## Principios de Testing

### 1. Las pruebas muestran presencia de defectos
Las pruebas pueden demostrar que existen defectos pero no pueden demostrar que no hay defectos.

### 2. Las pruebas exhaustivas son imposibles
Probar todo no es factible; es necesario realizar pruebas basadas en riesgos.

### 3. Pruebas tempranas
Las actividades de prueba deben comenzar lo más temprano posible en el SDLC.

### 4. Agrupación de defectos
Un pequeño número de módulos suele contener la mayoría de los defectos.

### 5. Paradoja del pesticida
Ejecutar las mismas pruebas repetidamente eventualmente dejará de encontrar nuevos errores.

### 6. Las pruebas dependen del contexto
El enfoque de pruebas varía según el contexto de la aplicación.

### 7. Falacia de ausencia de errores
Encontrar y corregir defectos no ayuda si el sistema es inutilizable.

## Ciclo de Vida del Desarrollo de Software (SDLC)

### Modelos Comunes de SDLC

#### Modelo en Cascada
- Enfoque secuencial
- Cada fase debe completarse antes de comenzar la siguiente
- Mejor para: Requisitos bien definidos

#### Modelo Ágil
- Enfoque iterativo e incremental
- Retroalimentación y adaptación continua
- Mejor para: Requisitos que cambian rápidamente

#### Modelo en V
- Modelo de Verificación y Validación
- Actividades de prueba paralelas al desarrollo
- Mejor para: Proyectos que requieren alta confiabilidad

#### DevOps
- Colaboración entre desarrollo y operaciones
- Integración y entrega continua
- Mejor para: Aplicaciones en la nube de ritmo rápido

## Ciclo de Vida de Pruebas (STLC)

### 1. Análisis de Requisitos
- Comprender requisitos
- Identificar requisitos probables
- Determinar enfoque de prueba

### 2. Planificación de Pruebas
- Definir estrategia de prueba
- Estimar recursos y cronograma
- Identificar riesgos

### 3. Desarrollo de Casos de Prueba
- Crear casos de prueba
- Preparar datos de prueba
- Configurar entorno de prueba

### 4. Configuración del Entorno de Prueba
- Configurar hardware y software
- Preparar datos de prueba
- Verificar disponibilidad del entorno

### 5. Ejecución de Pruebas
- Ejecutar casos de prueba
- Registrar defectos
- Re-probar defectos corregidos

### 6. Cierre de Pruebas
- Evaluar criterios de completitud de pruebas
- Documentar lecciones aprendidas
- Archivar artefactos de prueba

## Métricas de Calidad

### Métricas Clave a Rastrear
- **Densidad de Defectos**: Defectos por unidad de código
- **Cobertura de Pruebas**: Porcentaje de código/requisitos probados
- **Porcentaje de Detección de Defectos**: Defectos encontrados en pruebas vs. producción
- **Tasa de Ejecución de Pruebas**: Pruebas ejecutadas vs. planificadas
- **Tiempo de Resolución de Defectos**: Tiempo promedio para corregir defectos

## Roles en QA

### Ingeniero de QA
- Diseñar y ejecutar casos de prueba
- Reportar y rastrear defectos
- Verificar correcciones

### Líder de QA
- Planificar actividades de prueba
- Gestionar equipo de pruebas
- Reportar a las partes interesadas

### Ingeniero de Automatización de Pruebas
- Desarrollar scripts de prueba automatizados
- Mantener framework de automatización
- Integrar pruebas con CI/CD

### Ingeniero de Pruebas de Rendimiento
- Diseñar y ejecutar pruebas de rendimiento
- Analizar cuellos de botella de rendimiento
- Recomendar optimizaciones
