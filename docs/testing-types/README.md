# Tipos de Pruebas

## Pruebas Manuales

### ¿Qué son las Pruebas Manuales?
Las pruebas manuales son el proceso de verificar manualmente el software en busca de defectos. Requiere que un probador asuma el rol de un usuario final y utilice la mayoría de las funciones de la aplicación para garantizar el comportamiento correcto.

### Tipos de Pruebas Manuales

#### 1. Pruebas Exploratorias
- **Definición**: Aprendizaje, diseño y ejecución de pruebas simultáneos
- **Cuándo usar**: Nuevas funciones, escenarios complejos
- **Beneficios**: Encuentra defectos inesperados, enfoque creativo
- **Técnicas**: Pruebas basadas en sesiones, exploración libre

#### 2. Pruebas Ad-hoc
- **Definición**: Pruebas informales sin planificación
- **Cuándo usar**: Verificaciones rápidas, restricciones de tiempo
- **Beneficios**: Rápido, requiere preparación mínima
- **Limitaciones**: No repetible, sin documentación

#### 3. Pruebas de Humo
- **Definición**: Verificación básica de funcionalidad
- **Cuándo usar**: Después de nuevas compilaciones, antes de pruebas detalladas
- **Beneficios**: Validación rápida de funciones críticas
- **Ejemplo**: ¿Pueden los usuarios iniciar sesión? ¿Pueden acceder a las funciones principales?

#### 4. Pruebas de Sanidad
- **Definición**: Pruebas enfocadas en funcionalidad específica
- **Cuándo usar**: Después de correcciones de errores, cambios menores
- **Beneficios**: Verificar rápidamente áreas específicas
- **Ejemplo**: Probar solo el módulo de pagos después de una corrección

## Pruebas Automatizadas

### ¿Qué son las Pruebas Automatizadas?
Las pruebas automatizadas utilizan herramientas de software para ejecutar pruebas pre-escritas en una aplicación antes de que se lance a producción.

### Beneficios de la Automatización
- **Velocidad**: Las pruebas se ejecutan más rápido que la ejecución manual
- **Repetibilidad**: Ejecución de pruebas consistente
- **Cobertura**: Se pueden ejecutar más pruebas
- **Detección Temprana**: Integración con CI/CD
- **Rentable**: Ahorro a largo plazo en pruebas repetitivas

### Tipos de Pruebas Automatizadas

#### 1. Pruebas Unitarias
```python
# Ejemplo: Probar una función simple
def test_add_numbers():
    assert add(2, 3) == 5
    assert add(-1, 1) == 0
    assert add(0, 0) == 0
```

#### 2. Pruebas de Integración
```python
# Ejemplo: Probar integración con base de datos
def test_user_creation():
    user = create_user("test@example.com")
    saved_user = database.get_user(user.id)
    assert saved_user.email == "test@example.com"
```

#### 3. Pruebas de Extremo a Extremo
```python
# Ejemplo: Probar flujo completo del usuario
def test_checkout_process():
    login("user@example.com", "password")
    add_item_to_cart("product-123")
    proceed_to_checkout()
    complete_payment()
    assert order_confirmation_displayed()
```

### Herramientas de Automatización de Pruebas
- **Selenium**: Pruebas de aplicaciones web
- **Cypress**: Pruebas web modernas
- **Playwright**: Automatización multi-navegador
- **JUnit/TestNG**: Frameworks de pruebas Java
- **PyTest**: Framework de pruebas Python
- **Jest**: Pruebas JavaScript

## Pruebas de Rendimiento

### ¿Qué son las Pruebas de Rendimiento?
Las pruebas de rendimiento determinan cómo se desempeña un sistema en términos de capacidad de respuesta y estabilidad bajo una carga de trabajo particular.

### Tipos de Pruebas de Rendimiento

#### 1. Pruebas de Carga
- **Propósito**: Validar rendimiento bajo carga esperada
- **Ejemplo**: Probar con 1000 usuarios concurrentes
- **Métricas**: Tiempo de respuesta, rendimiento, utilización de recursos

#### 2. Pruebas de Estrés
- **Propósito**: Determinar el punto de ruptura del sistema
- **Ejemplo**: Aumentar gradualmente usuarios hasta que el sistema falle
- **Métricas**: Carga máxima, tiempo de recuperación

#### 3. Pruebas de Picos
- **Propósito**: Probar aumento repentino en la carga
- **Ejemplo**: Tráfico de venta de Black Friday
- **Métricas**: Estabilidad del sistema, tasa de errores

#### 4. Pruebas de Resistencia
- **Propósito**: Probar sistema durante período extendido
- **Ejemplo**: Ejecutar a carga normal durante 24-48 horas
- **Métricas**: Fugas de memoria, degradación de recursos

#### 5. Pruebas de Escalabilidad
- **Propósito**: Determinar capacidad de escalamiento del sistema
- **Ejemplo**: Agregar más servidores y medir mejora
- **Métricas**: Escalabilidad lineal, eficiencia de recursos

### Herramientas de Pruebas de Rendimiento
- **JMeter**: Pruebas de carga de código abierto
- **Gatling**: Pruebas de carga de alto rendimiento
- **K6**: Pruebas de carga modernas
- **LoadRunner**: Pruebas de rendimiento empresarial
- **Locust**: Pruebas de carga basadas en Python

## Pruebas de Seguridad

### ¿Qué son las Pruebas de Seguridad?
Las pruebas de seguridad identifican vulnerabilidades y aseguran que los datos y recursos estén protegidos de posibles intrusos.

### Pruebas de Seguridad Comunes

#### 1. Escaneo de Vulnerabilidades
- Herramientas automatizadas escanean vulnerabilidades conocidas
- Herramientas: Nessus, OpenVAS, Qualys

#### 2. Pruebas de Penetración
- Ataques simulados en el sistema
- Enfoques manuales y automatizados
- Herramientas: Metasploit, Burp Suite, OWASP ZAP

#### 3. Auditoría de Seguridad
- Inspección de políticas y procedimientos de seguridad
- Revisión de código para problemas de seguridad

#### 4. Escaneo de Seguridad
- Análisis estático de código
- Herramientas: SonarQube, Checkmarx, Veracode

### Vulnerabilidades de Seguridad Comunes (OWASP Top 10)

1. **Inyección**: SQL, NoSQL, inyección de comandos del SO
2. **Autenticación Rota**: Problemas de gestión de sesiones
3. **Exposición de Datos Sensibles**: Datos sin cifrar
4. **Entidades Externas XML (XXE)**: Vulnerabilidades del procesador XML
5. **Control de Acceso Roto**: Acceso no autorizado
6. **Configuración Incorrecta de Seguridad**: Configuración predeterminada, errores
7. **Cross-Site Scripting (XSS)**: Scripts maliciosos
8. **Deserialización Insegura**: Manipulación de objetos
9. **Uso de Componentes con Vulnerabilidades Conocidas**: Bibliotecas desactualizadas
10. **Registro y Monitoreo Insuficientes**: Falta de detección

## Pruebas de Usabilidad

### ¿Qué son las Pruebas de Usabilidad?
Las pruebas de usabilidad evalúan qué tan fácil y amigable es el software.

### Aspectos Clave
- **Aprendizaje**: Qué tan fácil es para nuevos usuarios aprender
- **Eficiencia**: Qué tan rápido los usuarios pueden realizar tareas
- **Memorabilidad**: Qué tan fácilmente los usuarios recuerdan la interfaz
- **Errores**: Cuántos errores cometen los usuarios y recuperación
- **Satisfacción**: Qué tan placentera es la experiencia

### Métodos de Pruebas de Usabilidad
- **Pruebas Moderadas**: Facilitador guía a los usuarios
- **Pruebas No Moderadas**: Los usuarios prueban independientemente
- **Pruebas A/B**: Comparar dos versiones
- **Seguimiento Ocular**: Rastrear dónde miran los usuarios
- **Protocolo de Pensamiento en Voz Alta**: Los usuarios verbalizan pensamientos

## Pruebas de Regresión

### ¿Qué son las Pruebas de Regresión?
Las pruebas de regresión aseguran que los cambios recientes no hayan afectado adversamente la funcionalidad existente.

### Cuándo Realizar Pruebas de Regresión
- Después de correcciones de errores
- Después de agregar nuevas funciones
- Después de refactorización de código
- Después de cambios de configuración

### Tipos de Pruebas de Regresión

#### 1. Regresión Completa
- Ejecutar todos los casos de prueba
- Consume tiempo pero exhaustivo

#### 2. Regresión Parcial
- Probar solo áreas afectadas
- Enfoque más rápido basado en riesgos

#### 3. Regresión Unitaria
- Probar unidades/componentes específicos
- Usado después de cambios de código

### Estrategias de Pruebas de Regresión
- **Re-probar Todo**: Ejecutar todas las pruebas existentes
- **Selección de Pruebas de Regresión**: Ejecutar subconjunto de pruebas
- **Priorización**: Ejecutar las pruebas más importantes primero
- **Enfoque Híbrido**: Combinar múltiples estrategias

## Pruebas de Compatibilidad

### ¿Qué son las Pruebas de Compatibilidad?
Las pruebas de compatibilidad verifican si el software funciona en diferentes entornos.

### Tipos de Pruebas de Compatibilidad

#### 1. Compatibilidad de Navegadores
- Diferentes navegadores (Chrome, Firefox, Safari, Edge)
- Diferentes versiones de navegadores

#### 2. Compatibilidad de Sistemas Operativos
- Windows, macOS, Linux
- Diferentes versiones de SO

#### 3. Compatibilidad de Dispositivos
- Escritorio, móvil, tablet
- Diferentes tamaños de pantalla y resoluciones

#### 4. Compatibilidad de Red
- Diferentes condiciones de red
- Variaciones de ancho de banda

#### 5. Compatibilidad de Bases de Datos
- Diferentes sistemas de bases de datos
- Diferentes versiones de bases de datos

### Herramientas para Pruebas de Compatibilidad
- **BrowserStack**: Pruebas multi-navegador
- **Sauce Labs**: Plataforma de pruebas en la nube
- **LambdaTest**: Pruebas de compatibilidad de navegadores
- **CrossBrowserTesting**: Pruebas multi-navegador
