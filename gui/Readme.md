# Práctica de UI/UX

Este repositorio contiene un proyecto para practicar UI/UX en el que se sirven interfaces HTML interactivas a través de un contenedor Docker basado en Nginx. El objetivo de la práctica es mejorar diseños de formularios existentes siguiendo buenas prácticas de usabilidad y experiencia de usuario.

## Contenido del Proyecto

- **Dockerfile:** Configuración para construir la imagen Docker con Nginx.
- **/html:** Carpeta que contiene las páginas HTML con ejemplos y ejercicios de UI/UX.
  - **index.html:** Página de inicio con enlaces o descripción de los ejercicios.
  - **form_pintura.html:** Ejercicio 1 – Formulario para solicitar el servicio de pintura de casas, que incluye campos para contacto, ubicación y dimensiones.
  - **form_congreso.html:** Ejercicio 2 – Formulario para inscripción a un congreso internacional, que permite la inscripción de asistentes y expositores (con opción para subir un archivo y proceso de pago simulado a través de Mercado Pago).

## Requisitos

- [Docker](https://www.docker.com/get-started) instalado en tu máquina.
- Git para clonar el repositorio.

## Uso

### Clonación del Repositorio

Clonar el repositorio:

```bash
git clone https://github.com/UTN-FRD/practicas-dds.git
```

Ingresar al directorio gui del proyecto clonado:

```
cd practicas-dds
cd gui
```

### Construir la Imagen Docker:

Desde la raíz del proyecto, ejecuta el siguiente comando para construir la imagen Docker usando el Dockerfile:

```
docker build -t practicas-dds-gui .
```

### Ejecutar el Contenedor:

Para ejecutar el contenedor y montar el directorio "html" como volumen (de modo que los cambios realizados en los archivos HTML se reflejen de forma inmediata en el contenedor), utilizar el siguiente comando:

```
docker run -d -p 80:80 -v /c/github/practicas-dds/gui/html:/usr/share/nginx/html practicas-dds-gui
```

Abrir el navegador y acceder a [http://localhost]() 

## Ejercicios de UI/UX:

### Ejercicio 1 – Servicio de Pintura de Casas:

Objetivo: Diseñar un formulario que permita capturar los datos de un usuario interesado en solicitar el servicio de pintura.
Campos propuestos:

* Datos de contacto.
* Ubicación del inmueble.
* Dimensiones.

### Ejercicio 2 – Inscripción al Congreso Internacional:

Objetivo: Crear un formulario para la inscripción a un congreso presencial, el cual incluye el proceso de pago (simulado mediante Mercado Pago) y además permite la inscripción de expositores.
Requisitos adicionales:

* Permitir la subida de archivos para expositores.
* Incluir un campo para el número de documento, de modo que se evite la inscripción duplicada.
* Simular el envío de un correo electrónico con la información al completar el formulario.
