# Mejores Prácticas

## Estrategias de Testing

### Testing Shift-Left
**Concepto**: Mover las pruebas más temprano en el ciclo de vida del desarrollo

**Beneficios**:
- Detección temprana de defectos
- Menor costo de corrección de errores
- Mejor colaboración entre equipos
- Calidad mejorada

**Implementación**:
- Involucrar QA en fase de requisitos
- Escribir pruebas antes/durante el desarrollo
- Usar análisis estático de código
- Implementar pruebas continuas

### Estrategia de Pirámide de Pruebas

```
        /\
       /  \
      / UI \
     /------\
    /        \
   /   API    \
  /------------\
 /              \
/ Pruebas Unitarias \
----------------------
```

**Concepto**: Equilibrar diferentes tipos de pruebas

**Capas**:
1. **Pruebas Unitarias (Base - 70%)**
   - Rápidas, aisladas, numerosas
   - Probar funciones/métodos individuales

2. **Pruebas de Integración/API (Medio - 20%)**
   - Probar interacciones de componentes
   - Validar APIs y servicios

3. **Pruebas UI/E2E (Superior - 10%)**
   - Probar flujos completos del usuario
   - Menos pero escenarios críticos

**Beneficios**:
- Retroalimentación rápida
- Rentable
- Suite de pruebas mantenible

### Testing Basado en Riesgos
**Concepto**: Priorizar pruebas basándose en riesgo

**Pasos**:
1. **Identificar Riesgos**
   - Impacto en el negocio
   - Complejidad técnica
   - Frecuencia de cambios
   - Historial de defectos

2. **Evaluar Riesgos**
   - Probabilidad de fallo
   - Impacto si ocurre fallo

3. **Priorizar Pruebas**
   - Enfocarse en áreas de alto riesgo
   - Asignar recursos en consecuencia

4. **Monitorear y Ajustar**
   - Rastrear resultados
   - Reevaluar riesgos regularmente

### Estrategia de Pruebas Exploratorias
**Cuándo Usar**:
- Nuevas funciones
- Escenarios complejos
- Complementar pruebas escritas
- Pruebas con restricción de tiempo

**Técnicas**:
- **Pruebas Basadas en Sesiones**: Sesiones con tiempo definido y objetivos específicos
- **Exploración Libre**: Exploración no estructurada
- **Pruebas de Escenarios**: Exploración basada en historias de usuario

**Documentación**:
- Notas de sesión de prueba
- Problemas descubiertos
- Áreas de cobertura de prueba
- Ideas para pruebas futuras

## Prácticas de Calidad de Código

### Revisiones de Código
**Propósito**: Mejorar calidad del código mediante revisión por pares

**Beneficios**:
- Detectar defectos temprano
- Compartir conocimiento
- Mantener estándares
- Mejorar diseño

**Mejores Prácticas**:
1. **Mantener Revisiones Pequeñas**
   - Limitar a 200-400 líneas de código
   - Revisar en 60 minutos

2. **Usar Listas de Verificación**
   - Estándares de codificación
   - Errores comunes
   - Preocupaciones de seguridad
   - Problemas de rendimiento

3. **Ser Constructivo**
   - Enfocarse en el código, no en la persona
   - Sugerir mejoras
   - Explicar razonamiento

4. **Automatizar Lo Que Se Pueda**
   - Usar linters
   - Herramientas de análisis estático
   - Pruebas automatizadas

**Lista de Verificación de Revisión**:
- [ ] El código sigue las guías de estilo
- [ ] La lógica es correcta y eficiente
- [ ] El manejo de errores es adecuado
- [ ] Se incluyen pruebas
- [ ] La documentación está actualizada
- [ ] No hay vulnerabilidades de seguridad
- [ ] No hay problemas de rendimiento
- [ ] El código es legible y mantenible

### Análisis Estático de Código
**Propósito**: Analizar código sin ejecutarlo

**Herramientas**:
- **SonarQube**: Análisis multi-lenguaje
- **ESLint**: JavaScript/TypeScript
- **Pylint**: Python
- **RuboCop**: Ruby
- **Checkstyle**: Java

**Beneficios**:
- Encontrar errores temprano
- Aplicar estándares de codificación
- Mejorar mantenibilidad
- Reducir deuda técnica

**Integración**:
```yaml
# Ejemplo de GitHub Actions
- name: Ejecutar SonarQube
  uses: sonarsource/sonarcloud-github-action@master
  env:
    GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
    SONAR_TOKEN: ${{ secrets.SONAR_TOKEN }}
```

### Desarrollo Guiado por Pruebas (TDD)
**Proceso**:
1. **Escribir una prueba que falla**
2. **Escribir código mínimo para pasar**
3. **Refactorizar código**
4. **Repetir**

**Beneficios**:
- Mejor diseño
- Pruebas de regresión incorporadas
- Mayor confianza
- Documentación viva

**Ejemplo de Flujo**:
```python
# Paso 1: Escribir prueba
def test_calculate_total():
    cart = ShoppingCart()
    cart.add_item(Item("Libro", 10))
    assert cart.calculate_total() == 10

# Paso 2: Implementar
class ShoppingCart:
    def __init__(self):
        self.items = []
    
    def add_item(self, item):
        self.items.append(item)
    
    def calculate_total(self):
        return sum(item.price for item in self.items)

# Paso 3: Refactorizar si es necesario
```

### Desarrollo Guiado por Comportamiento (BDD)
**Propósito**: Definir comportamiento en lenguaje legible para el negocio

**Formato (Gherkin)**:
```gherkin
Característica: Inicio de Sesión de Usuario
  Como usuario registrado
  Quiero iniciar sesión en el sistema
  Para poder acceder a mi cuenta

  Escenario: Inicio de sesión exitoso con credenciales válidas
    Dado que estoy en la página de inicio de sesión
    Cuando ingreso nombre de usuario válido "testuser"
    Y ingreso contraseña válida "Test123!"
    Y hago clic en el botón de inicio de sesión
    Entonces debería ser redirigido al tablero
    Y debería ver un mensaje de bienvenida
```

**Herramientas**:
- **Cucumber**: Multi-lenguaje
- **SpecFlow**: .NET
- **Behave**: Python
- **JBehave**: Java

## Mantenimiento de Pruebas

### Mantener Pruebas Mantenibles

#### 1. Seguir Principio DRY
**Malo**:
```python
def test_login_chrome():
    driver = webdriver.Chrome()
    driver.get("https://example.com/login")
    driver.find_element(By.ID, "username").send_keys("user")
    driver.find_element(By.ID, "password").send_keys("pass")
    driver.find_element(By.ID, "login").click()
    driver.quit()

def test_login_firefox():
    driver = webdriver.Firefox()
    driver.get("https://example.com/login")
    driver.find_element(By.ID, "username").send_keys("user")
    driver.find_element(By.ID, "password").send_keys("pass")
    driver.find_element(By.ID, "login").click()
    driver.quit()
```

**Bueno**:
```python
def login(driver, username, password):
    driver.get("https://example.com/login")
    driver.find_element(By.ID, "username").send_keys(username)
    driver.find_element(By.ID, "password").send_keys(password)
    driver.find_element(By.ID, "login").click()

@pytest.mark.parametrize("browser", ["chrome", "firefox"])
def test_login(browser):
    driver = get_driver(browser)
    login(driver, "user", "pass")
    driver.quit()
```

#### 2. Usar Modelo de Objeto de Página (POM)
**Propósito**: Separar lógica de prueba de interacción UI

**Ejemplo**:
```python
# Objeto de Página
class LoginPage:
    def __init__(self, driver):
        self.driver = driver
        
    def enter_username(self, username):
        self.driver.find_element(By.ID, "username").send_keys(username)
    
    def enter_password(self, password):
        self.driver.find_element(By.ID, "password").send_keys(password)
    
    def click_login(self):
        self.driver.find_element(By.ID, "login").click()
    
    def login(self, username, password):
        self.enter_username(username)
        self.enter_password(password)
        self.click_login()

# Prueba
def test_login():
    login_page = LoginPage(driver)
    login_page.login("user", "pass")
    assert dashboard_page.is_displayed()
```

#### 3. Usar Nombres Significativos
**Malo**:
```python
def test1():
    # Probar inicio de sesión
    pass

def test2():
    # Probar cierre de sesión
    pass
```

**Bueno**:
```python
def test_user_can_login_with_valid_credentials():
    pass

def test_user_can_logout_successfully():
    pass
```

#### 4. Mantener Pruebas Independientes
**Malo**:
```python
def test_create_user():
    user = create_user("test@example.com")
    assert user.id is not None

def test_update_user():
    # Depende de test_create_user
    user = get_user_by_email("test@example.com")
    user.name = "Nuevo Nombre"
    update_user(user)
```

**Bueno**:
```python
def test_create_user():
    user = create_user("test1@example.com")
    assert user.id is not None
    cleanup_user(user)

def test_update_user():
    user = create_user("test2@example.com")
    user.name = "Nuevo Nombre"
    update_user(user)
    assert get_user(user.id).name == "Nuevo Nombre"
    cleanup_user(user)
```

#### 5. Usar Fixtures y Setup/Teardown
```python
import pytest

@pytest.fixture
def test_user():
    """Crear un usuario de prueba"""
    user = create_user("test@example.com")
    yield user
    cleanup_user(user)

def test_user_profile(test_user):
    profile = get_profile(test_user.id)
    assert profile.email == "test@example.com"
```

### Manejo de Pruebas Inestables

**Causas Comunes**:
1. **Problemas de Temporización**
   - Solución: Usar esperas explícitas, no sleeps fijos

2. **Dependencias de Pruebas**
   - Solución: Hacer pruebas independientes

3. **Dependencias Externas**
   - Solución: Mockear servicios externos

4. **Estado Compartido**
   - Solución: Limpiar después de pruebas

5. **Código No Determinístico**
   - Solución: Usar inyección de dependencias, mockear valores aleatorios

**Estrategias**:
```python
# Malo: Sleep fijo
import time
time.sleep(5)  # Esperar que aparezca elemento

# Bueno: Espera explícita
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC

element = WebDriverWait(driver, 10).until(
    EC.presence_of_element_located((By.ID, "element-id"))
)
```

### Optimización de Suite de Pruebas

#### 1. Ejecución Paralela
```python
# pytest con ejecución paralela
pytest -n 4  # Ejecutar con 4 workers
```

#### 2. Ejecutar Solo Pruebas Afectadas
```bash
# Ejecutar pruebas para archivos cambiados
pytest --lf  # Last failed (últimas fallidas)
pytest --ff  # Failed first (fallidas primero)
```

#### 3. Categorizar Pruebas
```python
@pytest.mark.smoke
def test_critical_functionality():
    pass

@pytest.mark.regression
def test_detailed_scenario():
    pass

# Ejecutar solo pruebas de humo
pytest -m smoke
```

#### 4. Limpieza Regular
- Eliminar pruebas obsoletas
- Actualizar sintaxis deprecada
- Consolidar pruebas duplicadas
- Archivar datos de prueba antiguos

## Colaboración en Equipo

### Mejores Prácticas de Comunicación

#### 1. Reuniones Diarias
**Formato**:
- ¿Qué hiciste ayer?
- ¿Qué harás hoy?
- ¿Algún bloqueador?

**Duración**: 15 minutos máximo

#### 2. Reporte de Estado de Pruebas
**Incluir**:
- Resumen de ejecución de pruebas
- Defectos críticos
- Bloqueadores y riesgos
- Próximos pasos

#### 3. Documentación
**Documentos Esenciales**:
- Estrategia de pruebas
- Planes de prueba
- Casos de prueba
- Reportes de errores
- Resultados de pruebas
- Notas de versión

### Compartir Conocimiento

#### 1. Revisiones de Código
- Compartir enfoques de prueba
- Aprender de compañeros
- Mantener consistencia

#### 2. Pair Testing
- Dos probadores trabajan juntos
- Compartir conocimiento
- Encontrar más defectos

#### 3. Guild/Comunidad de Testing
- Reuniones regulares
- Compartir mejores prácticas
- Discutir desafíos
- Demostraciones de herramientas

#### 4. Documentación
- Mantener wiki/confluence
- Documentar enfoques de prueba
- Compartir lecciones aprendidas
- Crear guías

### Herramientas de Colaboración

#### Comunicación
- **Slack**: Mensajería de equipo
- **Microsoft Teams**: Plataforma de colaboración
- **Discord**: Chat comunitario

#### Documentación
- **Confluence**: Base de conocimiento
- **Notion**: Espacio de trabajo todo-en-uno
- **Google Docs**: Documentos colaborativos

#### Gestión de Proyectos
- **Jira**: Seguimiento de problemas
- **Azure DevOps**: DevOps de extremo a extremo
- **Trello**: Gestión visual de proyectos

## Mejora Continua

### Retrospectivas
**Frecuencia**: Después de cada sprint o versión mayor

**Formato**:
1. **¿Qué salió bien?**
2. **¿Qué podría mejorar?**
3. **Elementos de acción**

### Análisis de Métricas
**Revisión Regular**:
- Tendencias de defectos
- Tendencias de cobertura de pruebas
- Progreso de automatización
- Velocidad del equipo

**Acciones**:
- Identificar cuellos de botella
- Ajustar estrategias
- Asignar recursos

### Aprendizaje y Desarrollo

#### Mantenerse Actualizado
- Seguir blogs y foros de QA
- Asistir a conferencias y webinars
- Tomar cursos en línea
- Leer libros y artículos

#### Certificaciones
- **ISTQB**: International Software Testing Qualifications Board
- **CSTE**: Certified Software Test Engineer
- **CSQA**: Certified Software Quality Analyst

#### Práctica
- Contribuir a código abierto
- Proyectos personales
- Desafíos de codificación en línea
- Experimentación con herramientas

## Cultura de Calidad

### Construir Cultura de Calidad

#### 1. Responsabilidad Compartida
- La calidad es responsabilidad de todos
- Los desarrolladores prueban su código
- QA se enfoca en escenarios complejos

#### 2. Involucramiento Temprano
- QA en discusiones de requisitos
- Planificación de pruebas en fase de diseño
- Enfoque shift-left

#### 3. Mentalidad de Automatización
- Automatizar tareas repetitivas
- Liberar tiempo para pruebas exploratorias
- Mejora continua

#### 4. Filosofía Fail Fast
- Encontrar problemas temprano
- Ciclos de retroalimentación rápidos
- Aprender de fallos

#### 5. Aprendizaje Continuo
- Fomentar experimentación
- Compartir conocimiento
- Invertir en capacitación

### Panel de Métricas de Calidad

**Rastrear y Mostrar**:
- Tasa de éxito de construcción
- Tasa de aprobación de pruebas
- Cobertura de código
- Densidad de defectos
- Tiempo medio de resolución
- Frecuencia de despliegue

**Propósito**:
- Transparencia
- Decisiones basadas en datos
- Mejora continua
- Celebrar éxitos

## Mejores Prácticas de Seguridad

### Prácticas de Testing Seguro

#### 1. Proteger Datos de Prueba
- No usar datos de producción en pruebas
- Enmascarar información sensible
- Usar datos sintéticos
- Seguir regulaciones de protección de datos

#### 2. Entornos de Prueba Seguros
- Entornos aislados
- Controles de acceso
- Escaneos de seguridad regulares
- Configuraciones seguras

#### 3. Gestión de Credenciales
- Nunca hacer commit de credenciales al control de versiones
- Usar variables de entorno
- Usar herramientas de gestión de secretos (HashiCorp Vault, AWS Secrets Manager)

```python
# Malo
username = "admin"
password = "secretPassword123"

# Bueno
import os
username = os.getenv("TEST_USERNAME")
password = os.getenv("TEST_PASSWORD")
```

#### 4. Integración de Testing de Seguridad
- Escaneos de vulnerabilidades regulares
- Verificación de dependencias
- Análisis de seguridad estático
- Pruebas de penetración

### Cumplimiento y Estándares

**Estándares Comunes**:
- **ISO 25010**: Modelo de calidad de software
- **ISO 29119**: Estándares de pruebas de software
- **GDPR**: Protección de datos (Europa)
- **HIPAA**: Datos de salud (EE.UU.)
- **PCI DSS**: Datos de tarjetas de pago

**Mejores Prácticas**:
- Comprender regulaciones aplicables
- Documentar medidas de cumplimiento
- Auditorías regulares
- Capacitación para miembros del equipo
