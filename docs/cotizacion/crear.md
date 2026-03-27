# Crear Nueva Cotizacion

1. Seleccionar **Crear Cotizacion** desde el [listado](listado.md).

2. Completar los datos comunes de la cotizacion:
    - Cliente
    - Producto
    - Puerto
    - Es paquetes reefer (Si / No)
    - Canal
    - Tipo de Llenado
    - Servicio
    - Aplica

   ![Formulario de datos comunes](../img/image23.png)

3. Agregar al menos una fila en la tabla de cotizacion.

   ![Agregar fila a la cotizacion](../img/image24.png)

   ![Fila agregada a la tabla](../img/image25.png)

4. Completar por fila: Naviera, Modalidad y Terminal de ingreso.

   ![Datos de fila - Naviera y Modalidad](../img/image26.png)

   ![Datos de fila - Terminal](../img/image27.png)

5. Generar las tarifas por servicio. Si el sistema muestra la opcion **Agregar tarifa**, la tarifa debe crearse manualmente desde el modal correspondiente.

   ![Generacion de tarifas](../img/image28.png)

   ![Modal de agregar tarifa](../img/image29.png)

   ![Tarifa agregada](../img/image30.png)

6. Opcional: editar los campos de **Adicionales** y **Handling Profit**.

   ![Seccion de adicionales y handling](../img/image31.png)

   Adicionales:

   ![Edicion de adicionales](../img/image32.png)

   Handling Profit:

   ![Edicion de handling profit](../img/image33.png)

   ![Handling profit ingresado](../img/image34.png)

7. Seleccionar **Crear Cotizacion** para confirmar.

!!! warning "Regla importante"
    No es posible crear la cotizacion si existen filas incompletas o servicios sin tarifa asignada.

!!! info "Criterio especial de puerto"
    Para puertos con reglas de negocio particulares (por ejemplo, Pisco), la validacion de Gate Out puede variar. Consulte con el administrador del sistema ante dudas sobre un puerto especifico.
