# Manual de Usuario — New Transport Quoter

**Version:** 1.0
**Fecha:** 24 de marzo de 2026
**Elaborado por:** Boxting Labs

---

## Tabla de Contenido

1. [Descripcion General](#1-descripcion-general)
2. [Alcance](#2-alcance)
3. [Perfiles de Usuario](#3-perfiles-de-usuario)
4. [Acceso al Sistema](#4-acceso-al-sistema)
5. [Navegacion General](#5-navegacion-general)
6. [Modulo de Cotizacion](#6-modulo-de-cotizacion)
   - 6.1 [Listado de Cotizaciones](#61-listado-de-cotizaciones)
   - 6.2 [Acciones por Cotizacion](#62-acciones-por-cotizacion)
   - 6.3 [Crear Nueva Cotizacion](#63-crear-nueva-cotizacion)
   - 6.4 [Ver Cotizacion](#64-ver-cotizacion)
   - 6.5 [Generar PDF](#65-generar-pdf)
7. [Variables de Cotizacion (Tarifas)](#7-variables-de-cotizacion-tarifas)
   - 7.1 [Funciones Comunes](#71-funciones-comunes)
   - 7.2 [Crear y Editar Tarifa](#72-crear-y-editar-tarifa)
8. [Base de Datos Maestros](#8-base-de-datos-maestros)
   - 8.1 [Catalogos Disponibles](#81-catalogos-disponibles)
   - 8.2 [Funcionalidad](#82-funcionalidad)
9. [Mensajes y Validaciones Frecuentes](#9-mensajes-y-validaciones-frecuentes)
10. [Buenas Practicas Operativas](#10-buenas-practicas-operativas)
11. [Control de Cambios del Documento](#11-control-de-cambios-del-documento)

---

## 1. Descripcion General

New Transport Quoter es una plataforma web diseñada para la creacion, consulta y gestion de cotizaciones de transporte de carga. El sistema centraliza la administracion de tarifas por servicio, catalogo de datos maestros y la generacion de documentos PDF formales para clientes.

El sistema esta orientado a equipos de operaciones y comerciales que requieren generar cotizaciones precisas, controladas y trazables, integrando multiples variables logisticas como navieras, terminales, aduanas y servicios conexos.

---

## 2. Alcance

Este manual cubre los tres modulos principales accesibles desde el menu lateral:

- **Modulo de Cotizacion:** creacion dinamica, consulta, aprobacion y generacion de documentos PDF.
- **Variables de Cotizacion:** administracion de tarifas por tipo de servicio (Derecho de Embarque, Gate Out, Aduanas, Agenciamiento Maritimo, Transporte, Termografos, Filtros, Movilidad Senasa).
- **Base de Datos Maestros:** consulta de catalogos de referencia utilizados en el proceso de cotizacion.

---

## 3. Perfiles de Usuario

| Perfil | Acciones permitidas |
|---|---|
| Operador de Cotizaciones | Crear cotizaciones, generar PDF, consultar estados |
| Administrador de Tarifas | Crear, editar y eliminar tarifas por servicio |
| Usuario Consultor | Consultar cotizaciones y catalogos maestros |

---

## 4. Acceso al Sistema

1. Ingresar a la URL del sistema en el navegador.

   <img src="manual_images/media/image1.png" width="700" alt="Pantalla de acceso al sistema" />

2. Completar los campos de Usuario y Contrasena.

   <img src="manual_images/media/image2.png" width="700" alt="Formulario de login" />

3. Presionar el boton **Login**. El sistema redirigira al menu principal.

   <img src="manual_images/media/image3.png" width="700" alt="Acceso exitoso al sistema" />

> **Nota:** Si la sesion expira, el sistema redirige automaticamente al modulo de autenticacion. Consulte la seccion [Mensajes y Validaciones Frecuentes](#9-mensajes-y-validaciones-frecuentes) para mas detalle.

---

## 5. Navegacion General

El sistema cuenta con un panel lateral fijo desde el cual se accede a todos los modulos disponibles.

<img src="manual_images/media/image4.png" width="700" alt="Panel lateral de navegacion" />

La pantalla inicial del dashboard muestra el listado de cotizaciones.

<img src="manual_images/media/image5.png" width="700" alt="Dashboard principal" />

Para cerrar sesion, el usuario autenticado dispone de la opcion en la parte superior del panel lateral.

<img src="manual_images/media/image6.png" width="700" alt="Opcion de cierre de sesion" />

Al seleccionar **Salir**, el sistema muestra un modal de confirmacion antes de cerrar la sesion.

<img src="manual_images/media/image7.png" width="700" alt="Modal de confirmacion de cierre de sesion" />

---

## 6. Modulo de Cotizacion

El modulo de Cotizacion es el nucleo del sistema. Permite gestionar el ciclo completo de una cotizacion: desde su creacion hasta la generacion del documento PDF para el cliente.

### 6.1 Listado de Cotizaciones

Desde esta vista se puede filtrar y gestionar el universo de cotizaciones registradas.

**Filtrar por cliente:**

<img src="manual_images/media/image8.png" width="700" alt="Filtro por cliente" />

<img src="manual_images/media/image9.png" width="700" alt="Selector de cliente" />

El campo de busqueda permite localizar cualquier cliente disponible en el sistema.

<img src="manual_images/media/image10.png" width="700" alt="Busqueda de cliente" />

**Filtrar por estado:** los estados disponibles son Generado, Aprobado y Rechazado.

<img src="manual_images/media/image11.png" width="700" alt="Filtro por estado" />

<img src="manual_images/media/image12.png" width="700" alt="Selector de estado" />

<img src="manual_images/media/image13.png" width="700" alt="Opciones de estado disponibles" />

**Filtrar por tarifas expiradas:**

<img src="manual_images/media/image14.png" width="700" alt="Filtro de tarifas expiradas" />

<img src="manual_images/media/image15.png" width="700" alt="Vista con tarifas expiradas" />

<img src="manual_images/media/image16.png" width="700" alt="Resultado de filtro de expiracion" />

**Limpiar filtros activos:**

<img src="manual_images/media/image17.png" width="700" alt="Boton limpiar filtros" />

**Crear nueva cotizacion:** el boton se encuentra en la parte superior derecha del listado.

<img src="manual_images/media/image18.png" width="700" alt="Boton crear cotizacion" />

---

### 6.2 Acciones por Cotizacion

Cada cotizacion dispone de un menu de acciones accesible desde el icono de tres puntos al final de cada fila.

<img src="manual_images/media/image19.png" width="700" alt="Menu de acciones de cotizacion" />

Las acciones disponibles dependen del estado actual de la cotizacion:

- **Generar PDF** y **Ver** — disponibles en todos los estados.

  <img src="manual_images/media/image20.png" width="700" alt="Acciones generales" />

- **Aprobar Cotizacion** y **Eliminar** — disponibles solo para estado **Generado**.

  <img src="manual_images/media/image21.png" width="700" alt="Acciones para estado Generado" />

- **Actualizar Cotizacion** — disponible solo para estado **Aprobado**.

  <img src="manual_images/media/image22.png" width="700" alt="Accion para estado Aprobado" />

---

### 6.3 Crear Nueva Cotizacion

1. Seleccionar **Crear Cotizacion** desde el [listado](#61-listado-de-cotizaciones).

2. Completar los datos comunes de la cotizacion:
   - Cliente
   - Producto
   - Puerto
   - Es paquetes reefer (Si / No)
   - Canal
   - Tipo de Llenado
   - Servicio
   - Aplica

   <img src="manual_images/media/image23.png" width="700" alt="Formulario de datos comunes" />

3. Agregar al menos una fila en la tabla de cotizacion.

   <img src="manual_images/media/image24.png" width="700" alt="Agregar fila a la cotizacion" />

   <img src="manual_images/media/image25.png" width="700" alt="Fila agregada a la tabla" />

4. Completar por fila: Naviera, Modalidad y Terminal de ingreso.

   <img src="manual_images/media/image26.png" width="700" alt="Datos de fila - Naviera y Modalidad" />

   <img src="manual_images/media/image27.png" width="700" alt="Datos de fila - Terminal" />

5. Generar las tarifas por servicio. Si el sistema muestra la opcion **Agregar tarifa**, la tarifa debe crearse manualmente desde el modal correspondiente.

   <img src="manual_images/media/image28.png" width="700" alt="Generacion de tarifas" />

   <img src="manual_images/media/image29.png" width="700" alt="Modal de agregar tarifa" />

   <img src="manual_images/media/image30.png" width="700" alt="Tarifa agregada" />

6. Opcional: editar los campos de **Adicionales** y **Handling Profit**.

   <img src="manual_images/media/image31.png" width="700" alt="Seccion de adicionales y handling" />

   Adicionales:

   <img src="manual_images/media/image32.png" width="700" alt="Edicion de adicionales" />

   Handling Profit:

   <img src="manual_images/media/image33.png" width="700" alt="Edicion de handling profit" />

   <img src="manual_images/media/image34.png" width="700" alt="Handling profit ingresado" />

7. Seleccionar **Crear Cotizacion** para confirmar.

> **Regla importante:** no es posible crear la cotizacion si existen filas incompletas o servicios sin tarifa asignada.

> **Criterio especial de puerto:** para puertos con reglas de negocio particulares (por ejemplo, Pisco), la validacion de Gate Out puede variar. Consulte con el administrador del sistema ante dudas sobre un puerto especifico.

---

### 6.4 Ver Cotizacion

La vista de detalle de una cotizacion muestra la informacion completa del registro:

- Datos de cabecera: Cliente, Producto, Puerto, indicador de Paquetes Reefer y Estado.

  <img src="manual_images/media/image35.png" width="700" alt="Cabecera de la cotizacion" />

- Tabla completa de filas con costos por servicio y totales.

  <img src="manual_images/media/image36.png" width="700" alt="Tabla de cotizacion" />

  <img src="manual_images/media/image37.png" width="700" alt="Totales de cotizacion" />

- Acceso directo para [generar el PDF](#65-generar-pdf) de la cotizacion.

  <img src="manual_images/media/image38.png" width="700" alt="Boton generar PDF desde detalle" />

Vista completa del modulo:

<img src="manual_images/media/image39.png" width="700" alt="Vista completa de cotizacion" />

---

### 6.5 Generar PDF

Desde esta pantalla se configuran los parametros del documento antes de descargarlo.

<img src="manual_images/media/image40.png" width="700" alt="Pantalla de generacion de PDF" />

<img src="manual_images/media/image41.png" width="700" alt="Configuracion del PDF" />

**Opciones disponibles:**

- Editar datos de cabecera: fecha, telefono, direccion, cliente y puerto.

  <img src="manual_images/media/image42.png" width="700" alt="Edicion de cabecera del PDF" />

- Editar texto introductorio y texto de cierre del documento.

  <img src="manual_images/media/image43.png" width="700" alt="Edicion de textos del PDF" />

- Adjuntar hasta 3 imagenes en formato JPG o PNG.

  <img src="manual_images/media/image44.png" width="700" alt="Carga de imagenes para el PDF" />

- Seleccionar el tipo de PDF: **Resumido** o **Detallado**.

  <img src="manual_images/media/image45.png" width="700" alt="Seleccion de tipo de PDF" />

**Vista previa del documento:**

Resumido:

<img src="manual_images/media/image46.png" width="700" alt="Vista previa PDF resumido" />

Detallado:

<img src="manual_images/media/image47.png" width="700" alt="Vista previa PDF detallado" />

Para descargar el PDF directamente sin visualizar la vista previa, utilizar el boton **Generar y Descargar PDF**.

<img src="manual_images/media/image48.png" width="700" alt="Boton generar y descargar PDF" />

---

## 7. Variables de Cotizacion (Tarifas)

Este modulo agrupa la administracion de tarifas utilizadas en el proceso de cotizacion. Cada tipo de servicio tiene su propia seccion, pero todas comparten el mismo comportamiento de listado y mantenimiento.

**Servicios disponibles:**

- Derecho de Embarque

  <img src="manual_images/media/image49.png" width="700" alt="Listado Derecho de Embarque" />

- Gate Out

  <img src="manual_images/media/image50.png" width="700" alt="Listado Gate Out" />

- Aduanas

  <img src="manual_images/media/image51.png" width="700" alt="Listado Aduanas" />

- Agenciamiento Maritimo

  <img src="manual_images/media/image52.png" width="700" alt="Listado Agenciamiento Maritimo" />

- Transporte

  <img src="manual_images/media/image53.png" width="700" alt="Listado Transporte" />

- Termografos

  <img src="manual_images/media/image54.png" width="700" alt="Listado Termografos" />

- Filtros

  <img src="manual_images/media/image55.png" width="700" alt="Listado Filtros" />

- Movilidad Senasa

  <img src="manual_images/media/image56.png" width="700" alt="Listado Movilidad Senasa" />

---

### 7.1 Funciones Comunes

Todos los modulos de tarifas comparten las siguientes funcionalidades:

**Listado paginado con ordenamiento por columna:**

<img src="manual_images/media/image57.png" width="700" alt="Listado paginado con ordenamiento" />

Las columnas que muestran el indicador de ordenamiento permiten organizar los resultados de forma ascendente o descendente.

<img src="manual_images/media/image58.png" width="700" alt="Indicador de columna ordenable" />

**Mostrar y ocultar filtros de columna:**

<img src="manual_images/media/image59.png" width="700" alt="Boton mostrar filtros" />

<img src="manual_images/media/image60.png" width="700" alt="Filtros de columna visibles" />

**Limpiar filtros:** el boton realiza una limpieza total de todos los filtros activos. Adicionalmente, cada filtro individual cuenta con su propio boton de limpieza.

<img src="manual_images/media/image61.png" width="700" alt="Boton limpiar filtros de tarifas" />

**Crear tarifa:**

<img src="manual_images/media/image62.png" width="700" alt="Boton crear tarifa" />

**Editar registro existente:**

<img src="manual_images/media/image63.png" width="700" alt="Boton editar tarifa" />

<img src="manual_images/media/image64.png" width="700" alt="Formulario de edicion de tarifa" />

**Eliminar registro** — requiere confirmacion en un modal de confirmacion.

<img src="manual_images/media/image65.png" width="700" alt="Boton eliminar tarifa" />

<img src="manual_images/media/image66.png" width="700" alt="Modal de confirmacion de eliminacion" />

---

### 7.2 Crear y Editar Tarifa

Al registrar una tarifa se solicita la siguiente informacion:

- Variables comerciales y logisticas (cliente, producto, terminales, zona, etc.).
- Precio.
- Vigencia: fecha de inicio y fecha de fin.

El siguiente ejemplo corresponde a la creacion de una tarifa de **Derecho de Embarque**:

<img src="manual_images/media/image67.png" width="700" alt="Formulario crear tarifa - parte 1" />

<img src="manual_images/media/image68.png" width="700" alt="Formulario crear tarifa - parte 2" />

Edicion de tarifa existente:

<img src="manual_images/media/image69.png" width="700" alt="Formulario editar tarifa" />

> **Nota:** en el modo de edicion, segun el modulo, algunos campos base pueden estar bloqueados para mantener la consistencia historica de los registros.

---

## 8. Base de Datos Maestros

El modulo de **Administracion de Base de Datos Maestros** permite consultar los catalogos de referencia que se utilizan en el proceso de cotizacion. Al ingresar, el sistema presenta por defecto el catalogo de **Puertos de Embarque**.

### 8.1 Catalogos Disponibles

| Catalogo |
|---|
| Puertos de embarque |
| Terminales de ingreso |
| Terminales de retiro |
| Terminales de retorno |
| Modalidades de ingreso |
| Clientes |
| Consignatarios |
| Mayoristas |
| Agentes de Aduana |
| Jurisdicciones de aduana |
| Transportistas |
| Navieras |
| Puertos |
| Tipos de contenedor |
| Plantas |
| Zonas |
| Termografos |
| Filtros |
| Paquetes refrigerados |

<img src="manual_images/media/image70.png" width="700" alt="Vista general del modulo de maestros" />

### 8.2 Funcionalidad

**Seleccionar catalogo:** mediante el selector en la parte superior de la pantalla.

<img src="manual_images/media/image71.png" width="700" alt="Selector de catalogo" />

**Buscar por texto:** mediante la barra de busqueda disponible en cada catalogo.

<img src="manual_images/media/image72.png" width="700" alt="Busqueda en catalogo" />

**Navegar por paginas:** el catalogo presenta los resultados paginados.

<img src="manual_images/media/image73.png" width="700" alt="Paginacion del catalogo" />

> **Nota:** los catalogos maestros son de solo lectura desde este modulo. La administracion de los datos de referencia se realiza desde el backend del sistema.

---

## 9. Mensajes y Validaciones Frecuentes

| Mensaje o situacion | Causa probable | Accion recomendada |
|---|---|---|
| No permite crear cotizacion | Filas incompletas o servicios sin tarifa | Revisar que todas las filas tengan Naviera, Modalidad, Terminal y tarifa en cada servicio. Ver [Crear Nueva Cotizacion](#63-crear-nueva-cotizacion) |
| Error al cargar datos | Problemas de conectividad o sesion | Verificar conexion a internet, sesion activa y permisos del usuario |
| Redireccion al login | Sesion expirada o tokens invalidos | Iniciar sesion nuevamente. Ver [Acceso al Sistema](#4-acceso-al-sistema) |
| Error al generar PDF | Imagenes con formato o tamano incorrecto | Reintentar y verificar que las imagenes sean JPG o PNG. Ver [Generar PDF](#65-generar-pdf) |

---

## 10. Buenas Practicas Operativas

1. Actualizar periodicamente las tarifas antes de iniciar un proceso de cotizacion. Ver [Variables de Cotizacion](#7-variables-de-cotizacion-tarifas).
2. Utilizar los filtros disponibles para reducir errores en la seleccion de datos. Ver [Listado de Cotizaciones](#61-listado-de-cotizaciones).
3. Verificar las vigencias de las tarifas antes de aprobar una cotizacion.
4. Utilizar la vista previa del PDF antes de descargar el documento final. Ver [Generar PDF](#65-generar-pdf).
5. Mantener la informacion de los catalogos maestros actualizada para garantizar la precision de las cotizaciones. Ver [Base de Datos Maestros](#8-base-de-datos-maestros).

---

## 11. Control de Cambios del Documento

| Version | Fecha | Descripcion | Responsable |
|---|---|---|---|
| 1.0 | 24/03/2026 | Primera version del manual de usuario | Boxting Labs |
