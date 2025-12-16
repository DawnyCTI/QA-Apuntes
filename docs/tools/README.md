# Herramientas y Tecnologías

## Frameworks de Pruebas

### Frameworks de Pruebas Web

#### Selenium
**Descripción**: Framework de código abierto para automatizar navegadores web

**Características Clave**:
- Soporte multi-navegador (Chrome, Firefox, Safari, Edge)
- Múltiples lenguajes (Java, Python, C#, JavaScript)
- Gran comunidad y documentación extensa

**Ejemplo (Python)**:
```python
from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()
driver.get("https://example.com")
element = driver.find_element(By.ID, "login-button")
element.click()
driver.quit()
```

#### Cypress
**Descripción**: Framework moderno de pruebas end-to-end para aplicaciones web

**Características Clave**:
- Rápido, configuración fácil
- Espera automática
- Depuración con viaje en el tiempo
- Recarga en tiempo real

**Ejemplo (JavaScript)**:
```javascript
describe('Prueba de Inicio de Sesión', () => {
  it('debería iniciar sesión exitosamente', () => {
    cy.visit('/login')
    cy.get('#username').type('testuser')
    cy.get('#password').type('password123')
    cy.get('#login-button').click()
    cy.url().should('include', '/dashboard')
  })
})
```

#### Playwright
**Descripción**: Framework de automatización moderno de Microsoft

**Características Clave**:
- Soporte multi-navegador
- Capacidades de espera automática
- Intercepción de red
- Emulación móvil

**Ejemplo (JavaScript)**:
```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch();
  const page = await browser.newPage();
  await page.goto('https://example.com');
  await page.click('#login-button');
  await browser.close();
})();
```

### Frameworks de Pruebas Móviles

#### Appium
**Descripción**: Framework de automatización de código abierto para aplicaciones móviles

**Características Clave**:
- Multiplataforma (iOS y Android)
- Soporta aplicaciones nativas, híbridas y web
- Soporte de múltiples lenguajes

**Ejemplo (Python)**:
```python
from appium import webdriver
from appium.webdriver.common.appiumby import By

desired_caps = {
    'platformName': 'Android',
    'deviceName': 'Android Emulator',
    'app': '/path/to/app.apk'
}

driver = webdriver.Remote('http://localhost:4723/wd/hub', desired_caps)
driver.find_element(By.ID, 'com.example:id/button').click()
driver.quit()
```

#### Detox
**Descripción**: Framework de pruebas end-to-end de caja gris para React Native

**Características Clave**:
- Ejecución rápida
- Sincronización automática
- Multiplataforma

### Frameworks de Pruebas de API

#### REST Assured (Java)
**Descripción**: Biblioteca Java para probar APIs REST

**Ejemplo**:
```java
given()
    .contentType("application/json")
    .body("{\"username\":\"test\",\"password\":\"pass\"}")
.when()
    .post("/api/login")
.then()
    .statusCode(200)
    .body("token", notNullValue());
```

#### Postman/Newman
**Descripción**: Plataforma de desarrollo y pruebas de API

**Características Clave**:
- Ejecutor de colecciones
- Pruebas automatizadas
- Integración CI/CD
- Gestión de entornos

#### pytest-requests (Python)
**Ejemplo**:
```python
import requests

def test_api_endpoint():
    response = requests.get('https://api.example.com/users')
    assert response.status_code == 200
    assert 'users' in response.json()
```

### Frameworks de Pruebas Unitarias

#### JUnit (Java)
```java
import org.junit.Test;
import static org.junit.Assert.*;

public class CalculatorTest {
    @Test
    public void testAddition() {
        Calculator calc = new Calculator();
        assertEquals(5, calc.add(2, 3));
    }
}
```

#### pytest (Python)
```python
def test_addition():
    assert add(2, 3) == 5

def test_subtraction():
    assert subtract(5, 3) == 2
```

#### Jest (JavaScript)
```javascript
test('suma 1 + 2 para igualar 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

#### NUnit (.NET)
```csharp
[Test]
public void TestAddition()
{
    var calculator = new Calculator();
    Assert.AreEqual(5, calculator.Add(2, 3));
}
```

## Integración CI/CD

### ¿Qué es CI/CD?
**Integración Continua (CI)**: Construcción y prueba automática de cambios de código
**Entrega Continua (CD)**: Despliegue automático de código a producción

### Plataformas CI/CD Populares

#### GitHub Actions
**Descripción**: CI/CD nativo para repositorios de GitHub

**Ejemplo de Flujo de Trabajo**:
```yaml
name: Suite de Pruebas

on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Configurar Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.9'
      - name: Instalar dependencias
        run: pip install -r requirements.txt
      - name: Ejecutar pruebas
        run: pytest
```

#### Jenkins
**Descripción**: Servidor de automatización de código abierto

**Características Clave**:
- Ecosistema extenso de plugins
- Construcciones distribuidas
- Pipeline como código

**Ejemplo de Pipeline**:
```groovy
pipeline {
    agent any
    stages {
        stage('Construcción') {
            steps {
                sh 'npm install'
            }
        }
        stage('Pruebas') {
            steps {
                sh 'npm test'
            }
        }
        stage('Despliegue') {
            steps {
                sh 'npm run deploy'
            }
        }
    }
}
```

#### GitLab CI
**Descripción**: Plataforma CI/CD integrada

**Ejemplo (.gitlab-ci.yml)**:
```yaml
stages:
  - test
  - deploy

test:
  stage: test
  script:
    - npm install
    - npm test

deploy:
  stage: deploy
  script:
    - npm run deploy
  only:
    - main
```

#### CircleCI
**Descripción**: Plataforma CI/CD basada en la nube

**Ejemplo (config.yml)**:
```yaml
version: 2.1
jobs:
  test:
    docker:
      - image: circleci/node:14
    steps:
      - checkout
      - run: npm install
      - run: npm test
```

#### Azure DevOps
**Descripción**: Plataforma DevOps de Microsoft

**Características Clave**:
- Azure Pipelines
- Planes de prueba
- Gestión de artefactos

## Herramientas de Pruebas de Rendimiento

### Apache JMeter
**Descripción**: Herramienta de pruebas de carga de código abierto

**Características Clave**:
- Soporte de protocolos (HTTP, FTP, JDBC, SOAP)
- Pruebas distribuidas
- Plugins extensos

**Casos de Uso**:
- Aplicaciones web
- APIs
- Bases de datos

### Gatling
**Descripción**: Herramienta de pruebas de carga de alto rendimiento

**Características Clave**:
- DSL basado en Scala
- Informes detallados
- Compatible con CI/CD

**Ejemplo**:
```scala
scenario("Viaje del Usuario")
  .exec(http("Página Principal")
    .get("/"))
  .pause(2)
  .exec(http("Inicio de Sesión")
    .post("/login")
    .body(StringBody("""{"username":"test","password":"pass"}""")))
```

### K6
**Descripción**: Herramienta moderna de pruebas de carga

**Características Clave**:
- Basado en JavaScript
- Amigable para desarrolladores
- Ejecución en la nube

**Ejemplo**:
```javascript
import http from 'k6/http';
import { check } from 'k6';

export default function () {
  let response = http.get('https://example.com');
  check(response, {
    'estado es 200': (r) => r.status === 200,
  });
}
```

### Locust
**Descripción**: Herramienta de pruebas de carga basada en Python

**Ejemplo**:
```python
from locust import HttpUser, task, between

class WebsiteUser(HttpUser):
    wait_time = between(1, 5)
    
    @task
    def load_homepage(self):
        self.client.get("/")
    
    @task
    def load_about(self):
        self.client.get("/about")
```

## Sistemas de Seguimiento de Errores

### JIRA
**Descripción**: Software popular de seguimiento de problemas y proyectos

**Características Clave**:
- Tableros ágiles (Scrum/Kanban)
- Flujos de trabajo personalizables
- Integraciones extensas
- Informes y tableros

**Mejor Para**: Equipos empresariales, desarrollo ágil

### GitHub Issues
**Descripción**: Seguimiento de problemas integrado en GitHub

**Características Clave**:
- Integración con pull requests
- Etiquetas y milestones
- Tableros de proyecto
- Gratis para repositorios públicos

**Mejor Para**: Proyectos de código abierto, equipos pequeños

### Azure DevOps Boards
**Descripción**: Sistema de seguimiento de trabajo en Azure DevOps

**Características Clave**:
- Elementos de trabajo
- Tableros y backlogs
- Consultas y gráficos

**Mejor Para**: Ecosistema Microsoft, empresa

### Bugzilla
**Descripción**: Sistema de seguimiento de errores de código abierto

**Características Clave**:
- Búsqueda avanzada
- Notificaciones por correo
- Seguimiento de tiempo
- Personalizable

**Mejor Para**: Organizaciones que desean solución auto-hospedada

### Linear
**Descripción**: Seguimiento moderno de problemas para equipos de software

**Características Clave**:
- Rápido y responsivo
- Atajos de teclado
- Integración con GitHub
- Interfaz limpia

**Mejor Para**: Startups de rápido movimiento, equipos de producto

## Herramientas de Calidad de Código

### SonarQube
**Descripción**: Plataforma de análisis de calidad y seguridad de código

**Características Clave**:
- Detección de code smells
- Vulnerabilidades de seguridad
- Medición de deuda técnica
- Soporte de múltiples lenguajes

**Métricas**:
- Errores
- Vulnerabilidades
- Code smells
- Cobertura
- Duplicaciones

### ESLint (JavaScript)
**Descripción**: Herramienta de linting para JavaScript

**Ejemplo (.eslintrc.json)**:
```json
{
  "extends": "eslint:recommended",
  "rules": {
    "no-unused-vars": "error",
    "no-console": "warn"
  }
}
```

### Pylint (Python)
**Descripción**: Herramienta de análisis de código Python

**Uso**:
```bash
pylint mymodule.py
```

### Checkstyle (Java)
**Descripción**: Verificador de estilo de código para Java

**Características**:
- Aplicación de estándares de codificación
- Reglas personalizadas
- Integración con IDE

## Herramientas de Gestión de Datos de Prueba

### Faker
**Descripción**: Biblioteca para generar datos falsos

**Ejemplo (Python)**:
```python
from faker import Faker
fake = Faker()

print(fake.name())  # "Juan Pérez"
print(fake.email()) # "juan@example.com"
print(fake.address()) # "Calle Principal 123, Ciudad, Estado 12345"
```

### Mockaroo
**Descripción**: Generador de datos de prueba en línea

**Características Clave**:
- Generar datos realistas
- Múltiples formatos (CSV, JSON, SQL)
- Esquemas personalizados
- Acceso API

### DBUnit (Java)
**Descripción**: Framework de pruebas de bases de datos

**Características**:
- Siembra de bases de datos
- Verificación de estado
- Pruebas basadas en datos

## Herramientas de Monitoreo y Logging

### ELK Stack (Elasticsearch, Logstash, Kibana)
**Descripción**: Agregación y análisis de logs

**Casos de Uso**:
- Logging de aplicaciones
- Monitoreo de rendimiento
- Seguimiento de errores

### Grafana
**Descripción**: Plataforma de visualización de métricas

**Características**:
- Creación de tableros
- Múltiples fuentes de datos
- Alertas
- Análisis de series temporales

### Sentry
**Descripción**: Seguimiento y monitoreo de errores

**Características**:
- Seguimiento de errores en tiempo real
- Stack traces
- Seguimiento de versiones
- Monitoreo de rendimiento

## Herramientas de Pruebas de Navegadores

### BrowserStack
**Descripción**: Pruebas multi-navegador basadas en la nube

**Características**:
- 2000+ dispositivos y navegadores reales
- Pruebas manuales y automatizadas
- Pruebas locales
- Pruebas de capturas de pantalla

### Sauce Labs
**Descripción**: Plataforma de pruebas en la nube

**Características**:
- Pruebas multi-navegador
- Pruebas móviles
- Pruebas visuales
- Análisis de rendimiento

### LambdaTest
**Descripción**: Plataforma de pruebas multi-navegador

**Características**:
- Pruebas en vivo
- Pruebas automatizadas
- Pruebas de capturas de pantalla
- Pruebas responsive

## Integración con Control de Versiones

### Git Hooks
**Descripción**: Scripts activados por eventos de Git

**Ejemplo (hook pre-commit)**:
```bash
#!/bin/sh
npm test
if [ $? -ne 0 ]; then
    echo "Pruebas fallaron. Commit abortado."
    exit 1
fi
```

### Framework Pre-commit
**Descripción**: Framework para gestionar Git hooks

**Ejemplo (.pre-commit-config.yaml)**:
```yaml
repos:
  - repo: https://github.com/pre-commit/pre-commit-hooks
    rev: v4.0.1
    hooks:
      - id: trailing-whitespace
      - id: end-of-file-fixer
      - id: check-yaml
```

## Elegir las Herramientas Correctas

### Factores a Considerar

1. **Requisitos del Proyecto**
   - Tipo de aplicación (web, móvil, API)
   - Stack tecnológico
   - Necesidades de prueba

2. **Habilidades del Equipo**
   - Lenguajes de programación conocidos
   - Curva de aprendizaje
   - Calidad de documentación

3. **Presupuesto**
   - Código abierto vs. comercial
   - Costos de licencia
   - Costos de infraestructura

4. **Integración**
   - Compatibilidad CI/CD
   - Integración con control de versiones
   - Ecosistema de herramientas existentes

5. **Escalabilidad**
   - Tamaño del equipo
   - Crecimiento del proyecto
   - Requisitos de rendimiento

6. **Soporte y Comunidad**
   - Desarrollo activo
   - Tamaño de comunidad
   - Soporte del proveedor
