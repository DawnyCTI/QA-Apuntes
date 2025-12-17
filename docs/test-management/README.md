# Diseño y Gestión de Pruebas

## Planificación de Pruebas

### ¿Qué es la Planificación de Pruebas?
La planificación de pruebas es el proceso de definir el alcance, enfoque, recursos y cronograma de las actividades de prueba.

### Componentes de un Plan de Pruebas

#### 1. Objetivos de Prueba
- Definir qué necesita ser probado
- Identificar criterios de éxito
- Establecer metas de calidad

#### 2. Alcance de Pruebas
- **En el Alcance**: Funciones/funcionalidades a probar
- **Fuera del Alcance**: Funciones/funcionalidades que no se probarán
- **Suposiciones**: Condiciones asumidas como verdaderas
- **Restricciones**: Limitaciones y restricciones

#### 3. Estrategia de Prueba
- Enfoque de prueba (manual vs. automatizado)
- Tipos de pruebas a realizar
- Criterios de entrada y salida
- Criterios de suspensión y reanudación

#### 4. Planificación de Recursos
- **Equipo**: Roles y responsabilidades
- **Entorno**: Hardware, software, herramientas
- **Herramientas**: Herramientas de prueba requeridas
- **Presupuesto**: Estimación de costos

#### 5. Cronograma
- Hitos y fechas límite
- Dependencias de tareas
- Tiempo de contingencia

#### 6. Gestión de Riesgos
- Identificar riesgos potenciales
- Evaluar probabilidad e impacto de riesgos
- Definir estrategias de mitigación

### Estructura de Plantilla de Plan de Pruebas

```markdown
# Plan de Pruebas para [Nombre del Proyecto]

## 1. Introducción
- Propósito
- Alcance
- Referencias

## 2. Elementos de Prueba
- Funciones a probar
- Funciones no a probar

## 3. Enfoque de Prueba
- Niveles de prueba
- Tipos de prueba
- Técnicas de prueba

## 4. Criterios de Aprobación/Fallo
- Criterios de entrada
- Criterios de salida
- Criterios de suspensión

## 5. Entregables de Prueba
- Documento de plan de pruebas
- Casos de prueba
- Informes de prueba

## 6. Entorno de Prueba
- Requisitos de hardware
- Requisitos de software
- Configuración de red

## 7. Cronograma
- Fases y hitos de prueba

## 8. Personal y Capacitación
- Roles y responsabilidades
- Requisitos de capacitación

## 9. Riesgos y Contingencias
- Riesgos identificados
- Planes de mitigación

## 10. Aprobaciones
- Requisitos de firma
```

## Diseño de Casos de Prueba

### ¿Qué es un Caso de Prueba?
Un caso de prueba es un conjunto de condiciones o variables bajo las cuales un probador determinará si un sistema bajo prueba satisface los requisitos.

### Componentes de un Caso de Prueba

1. **ID de Caso de Prueba**: Identificador único
2. **Título de Caso de Prueba**: Descripción breve
3. **Descripción**: Descripción detallada del caso de prueba
4. **Precondiciones**: Requisitos previos antes de la ejecución
5. **Pasos de Prueba**: Instrucciones paso a paso
6. **Datos de Prueba**: Datos de entrada requeridos
7. **Resultado Esperado**: Resultado esperado
8. **Resultado Real**: Resultado observado (completado durante la ejecución)
9. **Estado**: Aprobado/Fallido/Bloqueado/Omitido
10. **Prioridad**: Alta/Media/Baja
11. **Severidad**: Crítica/Mayor/Menor/Trivial

### Ejemplo de Caso de Prueba

```
ID de Caso de Prueba: TC_001
Título: Verificar inicio de sesión de usuario con credenciales válidas
Descripción: Probar la funcionalidad de inicio de sesión con nombre de usuario y contraseña válidos
Precondiciones: 
  - La cuenta de usuario existe en el sistema
  - El usuario está en la página de inicio de sesión

Pasos de Prueba:
1. Ingresar nombre de usuario válido
2. Ingresar contraseña válida
3. Hacer clic en el botón "Iniciar sesión"

Datos de Prueba:
  Nombre de usuario: testuser@example.com
  Contraseña: ValidPass123!

Resultado Esperado:
  - El usuario inicia sesión exitosamente
  - El usuario es redirigido al tablero
  - Se muestra mensaje de bienvenida

Prioridad: Alta
Severidad: Crítica
```

### Técnicas de Diseño de Casos de Prueba

#### 1. Partición de Equivalencia
- Dividir datos de entrada en particiones equivalentes
- Probar un valor de cada partición
- Ejemplo: Campo de edad (0-17, 18-65, 66+)

#### 2. Análisis de Valores Límite
- Probar en los límites de dominios de entrada
- Ejemplo: Para rango 1-100, probar 0, 1, 100, 101

#### 3. Pruebas de Tabla de Decisión
- Enfoque sistemático para lógica de negocio compleja
- Combinaciones de entradas y salidas correspondientes

```
| Condición 1 | Condición 2 | Acción 1 | Acción 2 |
|------------|-------------|----------|----------|
| Verdadero  | Verdadero   | Ejecutar | Omitir   |
| Verdadero  | Falso       | Omitir   | Ejecutar |
| Falso      | Verdadero   | Omitir   | Ejecutar |
| Falso      | Falso       | Omitir   | Omitir   |
```

#### 4. Pruebas de Transición de Estado
- Probar comportamiento del sistema con diferentes estados
- Ejemplo: Estados de pedido (Pendiente → Procesando → Enviado → Entregado)

#### 5. Pruebas de Caso de Uso
- Derivar casos de prueba de casos de uso
- Enfoque en escenarios de usuario

#### 6. Adivinación de Errores
- Técnica basada en experiencia
- Predecir dónde podrían ocurrir errores

## Gestión de Datos de Prueba

### ¿Qué son los Datos de Prueba?
Los datos de prueba son los datos que se utilizan para ejecutar pruebas, que pueden incluir valores de entrada, resultados esperados y datos de configuración.

### Tipos de Datos de Prueba

#### 1. Datos de Prueba Válidos
- Datos que deben ser aceptados por el sistema
- Prueba escenarios positivos

#### 2. Datos de Prueba Inválidos
- Datos que deben ser rechazados por el sistema
- Prueba escenarios negativos

#### 3. Datos de Prueba de Límite
- Datos en los bordes de rangos válidos/inválidos

#### 4. Datos de Prueba Predeterminados
- Datos preconfigurados o generados por el sistema

### Mejores Prácticas de Gestión de Datos de Prueba

1. **Seguridad de Datos**
   - Enmascarar datos sensibles
   - Cumplir con regulaciones de protección de datos
   - Usar datos sintéticos cuando sea posible

2. **Calidad de Datos**
   - Asegurar precisión de datos
   - Mantener datos actualizados
   - Validar integridad de datos

3. **Reutilización de Datos**
   - Crear conjuntos de datos reutilizables
   - Documentar requisitos de datos
   - Control de versiones de datos de prueba

4. **Mantenimiento de Datos**
   - Limpieza regular
   - Archivar datos antiguos
   - Actualizar bases de datos de prueba

### Técnicas de Generación de Datos de Prueba

- **Creación Manual**: Crear datos manualmente
- **Enmascaramiento de Datos**: Anonimizar datos de producción
- **Subconjunto de Datos**: Extraer subconjunto de datos de producción
- **Datos Sintéticos**: Generar datos artificiales
- **Siembra de Datos**: Poblar base de datos con datos predefinidos

## Seguimiento y Reporte de Errores

### ¿Qué es un Error/Defecto?
Un error es una falla en el software que hace que produzca un resultado incorrecto o inesperado, o que se comporte de formas no deseadas.

### Ciclo de Vida de un Error

```
Nuevo → Asignado → Abierto → Corregido → Re-probar → Verificado → Cerrado
                    ↓
                Rechazado / Diferido / Duplicado
```

### Componentes de un Reporte de Error

1. **ID de Error**: Identificador único
2. **Resumen**: Descripción breve
3. **Descripción**: Explicación detallada
4. **Pasos para Reproducir**: Cómo recrear el error
5. **Resultado Esperado**: Qué debería suceder
6. **Resultado Real**: Qué sucede realmente
7. **Severidad**: Impacto en el sistema
8. **Prioridad**: Urgencia de corrección
9. **Entorno**: SO, navegador, versión
10. **Adjuntos**: Capturas de pantalla, registros, videos

### Ejemplo de Reporte de Error

```
ID de Error: BUG-001
Resumen: Botón de inicio de sesión no responde en dispositivos móviles

Descripción:
El botón de inicio de sesión en la página de autenticación no responde 
a eventos táctiles en dispositivos móviles usando el navegador Safari de iOS.

Pasos para Reproducir:
1. Abrir la aplicación en iPhone usando Safari
2. Navegar a página de inicio de sesión
3. Ingresar credenciales válidas
4. Tocar el botón "Iniciar sesión"

Resultado Esperado:
El usuario debería iniciar sesión y ser redirigido al tablero

Resultado Real:
No sucede nada al tocar el botón de inicio de sesión

Entorno:
- Dispositivo: iPhone 12 Pro
- SO: iOS 15.5
- Navegador: Safari
- Versión de App: 2.3.1

Severidad: Crítica
Prioridad: Alta

Adjuntos:
- captura_pantalla_inicio_sesion.png
- video_reproduccion.mp4
```

### Severidad vs Prioridad

#### Severidad (Impacto en el Sistema)
- **Crítica**: Caída del sistema, pérdida de datos
- **Mayor**: Fallo de funcionalidad mayor
- **Menor**: Problema de funcionalidad menor
- **Trivial**: Problemas cosméticos

#### Prioridad (Urgencia de Corrección)
- **Alta**: Corregir inmediatamente
- **Media**: Corregir en próxima versión
- **Baja**: Corregir cuando haya tiempo

### Herramientas de Seguimiento de Errores
- **Jira**: Herramienta popular de gestión de proyectos
- **Bugzilla**: Rastreador de errores de código abierto
- **Azure DevOps**: Plataforma DevOps de Microsoft
- **GitHub Issues**: Integrado con GitHub
- **Trello**: Gestión visual de proyectos
- **Monday.com**: Plataforma de gestión de trabajo

## Métricas e Informes de Prueba

### Métricas Clave de Prueba

#### 1. Métricas de Cobertura de Pruebas
```
Cobertura de Pruebas = (Número de Requisitos Probados / Requisitos Totales) × 100%
Cobertura de Código = (Líneas de Código Ejecutadas / Líneas Totales de Código) × 100%
```

#### 2. Métricas de Defectos
```
Densidad de Defectos = Defectos Totales / Tamaño del Software (KLOC)
  (KLOC = Kilo Líneas de Código, es decir, miles de líneas de código)
Porcentaje de Detección de Defectos = (Defectos Encontrados en Pruebas / Defectos Totales) × 100%
Eficiencia de Eliminación de Defectos = (Defectos Encontrados Antes del Lanzamiento / Defectos Totales) × 100%
```

#### 3. Métricas de Ejecución de Pruebas
```
Tasa de Ejecución de Pruebas = (Pruebas Ejecutadas / Pruebas Totales) × 100%
Porcentaje de Aprobación = (Pruebas Aprobadas / Pruebas Totales) × 100%
Porcentaje de Fallo = (Pruebas Fallidas / Pruebas Totales) × 100%
```

#### 4. Métricas de Progreso de Pruebas
- Casos de prueba escritos vs. planificados
- Casos de prueba ejecutados vs. planificados
- Defectos encontrados vs. esperados
- Defectos corregidos vs. reportados

### Informes de Prueba

#### Informe de Estado Diario de Pruebas
- Pruebas ejecutadas
- Pruebas aprobadas/fallidas
- Nuevos defectos encontrados
- Bloqueadores y problemas

#### Informe Resumen Semanal de Pruebas
- Resumen de progreso de pruebas
- Logros clave
- Riesgos y problemas
- Planes para próxima semana

#### Informe de Cierre de Pruebas
- Resumen de pruebas y resultados
- Resumen de defectos
- Lecciones aprendidas
- Recomendaciones

### Panel de Métricas de Prueba de Ejemplo

```
Casos de Prueba Totales: 500
Ejecutados: 450 (90%)
Aprobados: 400 (89%)
Fallidos: 40 (9%)
Bloqueados: 10 (2%)

Defectos Encontrados: 85
Críticos: 5
Mayores: 20
Menores: 45
Triviales: 15

Cobertura de Pruebas: 92%
Cobertura de Código: 78%
Densidad de Defectos: 1.2 defectos/KLOC
```

## Herramientas de Gestión de Pruebas

### Herramientas Populares de Gestión de Pruebas

#### 1. TestRail
- Gestión completa de casos de prueba
- Seguimiento de ejecución de pruebas
- Informes y análisis

#### 2. Zephyr
- Se integra con Jira
- Métricas de prueba en tiempo real
- Trazabilidad

#### 3. qTest
- Gestión de pruebas empresarial
- Soporte para pruebas ágiles
- Integración CI/CD

#### 4. PractiTest
- Gestión de pruebas de extremo a extremo
- Informes flexibles
- Capacidades de integración

#### 5. TestLink
- Gestión de pruebas de código abierto
- Gestión de requisitos
- Seguimiento de ejecución de pruebas

## Mejores Prácticas en Gestión de Pruebas

1. **Planificación Temprana**
   - Comenzar planificación de pruebas temprano en el proyecto
   - Involucrar a las partes interesadas en la planificación

2. **Documentación Clara**
   - Mantener documentación de pruebas actualizada
   - Usar plantillas para consistencia

3. **Trazabilidad**
   - Vincular casos de prueba a requisitos
   - Rastrear defectos a casos de prueba

4. **Revisiones Regulares**
   - Revisar planes y casos de prueba regularmente
   - Actualizar según cambios

5. **Estrategia de Automatización**
   - Identificar candidatos para automatización
   - Equilibrar pruebas manuales y automatizadas

6. **Comunicación**
   - Actualizaciones de estado regulares
   - Informes transparentes
   - Compromiso de partes interesadas

7. **Mejora Continua**
   - Analizar métricas y tendencias
   - Aprender de defectos
   - Refinar procesos basándose en lecciones aprendidas
