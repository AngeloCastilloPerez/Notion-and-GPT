# 📘 Notion-and-GPT

Este proyecto define una especificación **OpenAPI 3.1.0** para interactuar con la API de **Notion**, permitiendo crear páginas, agregar bloques de contenido, recuperar información estructurada y realizar búsquedas dentro del espacio de trabajo. Ideal para integrar funcionalidades de Notion en asistentes inteligentes como **ChatGPT**.

---

## 🧩 Estructura del archivo `openapi.yaml`

### 1. Encabezado de la especificación

**openapi: "3.1.0"**  
**info**:  
&nbsp;&nbsp;**title**: "Notion GPT Demo"  
&nbsp;&nbsp;**version**: "1.0.0"

**Explicación:**  
Define el estándar OpenAPI y contiene metadatos del API como el nombre y la versión.

---

### 2. Servidor base

**servers**:  
&nbsp;&nbsp;- url: "https://api.notion.com/v1"  
&nbsp;&nbsp;&nbsp;&nbsp;description: "Notion API Base URL"

**Explicación:**  
Establece la URL base para todas las peticiones a la API de Notion.

---

### 3. Endpoint `/pages` → Crear nueva página

**/pages**:  
&nbsp;&nbsp;**post**:  
&nbsp;&nbsp;&nbsp;&nbsp;**summary**: "Create Page in Notion"  
&nbsp;&nbsp;&nbsp;&nbsp;**description**: "Crea una nueva página dentro de la página existente 'My GPT Page'."

**Explicación:**  
Define un `POST` que permite crear una nueva página en Notion dentro de una página principal existente.  
Requiere definir el `parent`, propiedades como el `title`, y contenido opcional en `children`.

---

### 4. Endpoint `/blocks/{block_id}/children` → Obtener bloques hijos

**/blocks/{block_id}/children**:  
&nbsp;&nbsp;**get**:  
&nbsp;&nbsp;&nbsp;&nbsp;**summary**: "Retrieve Block Children"  
&nbsp;&nbsp;&nbsp;&nbsp;**description**: "Recupera los bloques hijos de un bloque o página."

**Explicación:**  
Define un `GET` para obtener los bloques hijos de una página o bloque específico.  
Se debe pasar el `block_id` en la URL y el `Notion-Version` en los headers.

---

### 5. Endpoint `/blocks/{block_id}/children` → Agregar bloques hijos

**/blocks/{block_id}/children**:  
&nbsp;&nbsp;**patch**:  
&nbsp;&nbsp;&nbsp;&nbsp;**summary**: "Append Block Children"  
&nbsp;&nbsp;&nbsp;&nbsp;**description**: "Agrega bloques a un bloque/página."

**Explicación:**  
Permite usar `PATCH` para agregar nuevos bloques de contenido (títulos, párrafos, etc.) a una página o bloque ya existente.

---

### 6. Endpoint `/search` → Buscar contenido

**/search**:  
&nbsp;&nbsp;**post**:  
&nbsp;&nbsp;&nbsp;&nbsp;**summary**: "Search in Notion"  
&nbsp;&nbsp;&nbsp;&nbsp;**description**: "Realiza una búsqueda en todo el espacio de trabajo."

**Explicación:**  
Realiza una búsqueda global en el espacio de trabajo de Notion.  
Permite personalizar el texto a buscar (`query`) y ordenar los resultados (`sort`).

---

## 🚀 ¿Qué puedes hacer con esta especificación?

- Crear páginas dinámicamente desde una app externa.  
- Consultar contenido estructurado desde Notion.  
- Agregar información a páginas usando bloques.  
- Hacer búsquedas inteligentes en tu espacio de trabajo.

---
