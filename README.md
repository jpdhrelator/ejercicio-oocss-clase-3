
# Actividad Refactorización OOCSS - "Tabla de Precios"
Objetivo: Aplicar la metodología OOCSS para eliminar código repetido y crear componentes reutilizables.

## Contexto del Proyecto
Eres el desarrollador Frontend en una startup. Un compañero junior ha creado una página de "Planes de Precios" para el sitio web. Funciona visualmente, pero el código es un desastre: ha copiado y pegado los estilos tres veces (uno para cada plan) cambiando solo los colores. Tu jefe te ha pedido que refactorices (reescribas) el CSS aplicando OOCSS para separar la Estructura de la Piel.

### El Código "Sucio" (Problema Actual)
Tu compañero creó tres clases monolíticas: .plan-basico, .plan-pro y .plan-enterprise. Observa cómo se repiten las propiedades de ancho, padding y bordes.

```css
/* ¡NO USES ESTO! ESTO ES LO QUE DEBES ARREGLAR */
.plan-basico {
  width: 30%;
  padding: 20px;
  text-align: center;
  border: 1px solid #ddd; /* Estructura */
  border-radius: 8px;     /* Estructura */
  display: inline-block;  /* Estructura */
  margin: 1%;             /* Estructura */
  background-color: #fff; /* Piel */
}
.plan-basico h3 { color: #666; } /* Piel */

.plan-pro {
  width: 30%;
  padding: 20px;
  text-align: center;
  border: 1px solid #007bff; /* Estructura repetida + Piel */
  border-radius: 8px;        /* Estructura repetida */
  display: inline-block;     /* Estructura repetida */
  margin: 1%;                /* Estructura repetida */
  background-color: #e3f2fd; /* Piel */
  transform: scale(1.05);    /* Piel/Estado */
}
.plan-pro h3 { color: #007bff; } /* Piel */

.plan-enterprise {
  width: 30%;
  padding: 20px;
  text-align: center;
  border: 1px solid #28a745; /* Estructura repetida + Piel */
  border-radius: 8px;        /* Estructura repetida */
  display: inline-block;     /* Estructura repetida */
  margin: 1%;                /* Estructura repetida */
  background-color: #e8f5e9; /* Piel */
}
.plan-enterprise h3 { color: #28a745; } /* Piel */
```


### Instrucciones del Ejercicio
##### Paso 1: Análisis 

Identifica qué propiedades son Estructura (se repiten en todos) y cuáles son Piel (cambian según el plan).

Pista: Ancho, padding, text-align, display y margin son estructura.

Pista: Colores de fondo y colores de borde son piel.

##### Paso 2: Crear la Clase Estructural
Crea una clase llamada .pricing-card.

Mueve todas las propiedades estructurales compartidas a esta clase.

Esta clase NO debe tener colores (o solo colores neutros base).

##### Paso 3: Crear las Clases de Piel 
Crea tres clases de piel independientes:

.skin-basic: Fondo blanco, bordes grises.

.skin-pro: Fondo azul claro, bordes azules.

.skin-enterprise: Fondo verde claro, bordes verdes.

##### Paso 4: Implementación y Botones 
Escribe el HTML completo para los 3 planes.

Cada plan debe tener ambas clases ej: 
```html
<div class="pricing-card skin-pro">
```
#####  Bonus: 
Aplica OOCSS también a los botones de "Contratar". Crea una estructura .btn y reutiliza las mismas pieles (.skin-basic, etc.) o crea nuevas.

##### Rama y Carpeta de trabajo

Debe crear una rama con esta estructura nombre-apellido, luego crear una carpeta con la misma estructura y desarrollar su trabajo , luego debe crear una pr hacia la rama main.
##### Debe usar esta estructura de carpetas y archivos:

- nombre-apellido/
  - components/
    - pricing-cards/
  - index.html

