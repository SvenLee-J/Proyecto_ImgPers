# La app debe permitir:

- Administrar sus productos.
- Organizar las reservas de los clientes.
- Gestionar los horario.
- Trabajo de las empleadas.
- Consultar la situación económica del negocio.

# Pantallas.

## Inicio.

- Navbar_V1. / Sin haber iniciado sessión.    
    - Inicio de sessión.
    - Creación de cuenta.
    - Servicios / Carrito.

- Navbar_V2. / Con sessión iniciada.
    - Nombre de la cuenta.
    - Ajustes.
    - Servicios / Carrito.

- Header con un carrusel de enuncios sobre cosas a destacar (Resultados de servicios, promociones, etc).

- Seccion con distintos servicios.

- Footer con fomrulario para dejar comentarios. + Datos de contacto.

### Settings.

Varias opciones del seting como un `log out` / `Idioma` / `Datos de la cuenta`.

### Pagina de listado de serviciós

Columnas con los Servicios disponibles.

### Pagina del servicio.

- Fotos sobre los resultados.
- Breve descripcción del servicio + Duración / Preció.
- Sección de comentarios.

Processo de reserva.
1. Elegir dia y hora.
2. Pago...
3. Aviso de reserva finalizada + Resumen de esta.

### Pag. Panel de Administración.

- Pag. Administración.
    - Administrar Productos y materiales.
    - Administrar clientes + reservas.
    
    - Personal.
        - Trabajo de las empleadas.
        - Gest. Horarios.
    
    - Consulta Economia del negoció.

#### Pag. Administración de productos y material.

Funciones:

- Añadir Productos.
- Consultar listado de productos. (Tabla)
- Modificar datos de un producto. (?)
- Eliminar productos. (?)
- Buscar por nombre. (Formulario + Tabla.)
- Filtrar productos por categoría. (Formulario + Tabla)
- Ordenar productos por tipo de dato. (Formulario + Tabla)
- Avisos de pocas existencias. (Recuadro.)
- Consultar valor economico del inventario. (Suma Precios.)

#### Pag. Administrar clientes + reservas.

##### Apartado de clientes: 

Funciones:

- Dar de alta a los clientes.
- Modificar sus datos.
- Consultar su información.
- Eliminar Clientes.
- Buscar por nombre o teléfono.
- Consultar historial de servicios realizados.

##### Apartado de Reservas.

Funciones:

- Listado de reservas.
- Busqueda por nombre o teléfono.
- Edición de reservas.

#### Pag. Adminstrar Personal.

Funciones:

- Añadir empleados.
- Modificar sus datos.
- Consultar listado de personal.
- Buscar y filtrar empleados/as.
- Consultar horas de trabajo programado.
- Consultar horas de servicios completados.
- Calcular el coste laboral según las horas efectivamente trabajadas y la tarifa establecida. 
- Detectar conflictos de horarios.
- Desactivar empleadas que ya no trabajem en el centro.

#### Pag. Administrar Horarios.

...

### Pag. Administracion economica.

Funciones: 

- Conteo de Servicios Completados.
- Ingresos generadps por los servicios completados.
- Ingresos agrupados por tipo de servicio.
- Gastos por compras de productos.
- Coste del personal.
- Benedicio estimado.
- Evolucion de los ingresos y gastos por periodos.


---

## Modelos Datos.

### Producto:
- Identificador. ``(ID)(UNIC)(PrimaryKey)``
- Nombre. ``(String)``
- Categoría. ``(String)``
- Descripción. ``(String)``
- Precio compra. ``(num)``
- Precio venta. ``(num)``
- Cantidad disponible. ``(num)``
- Cantidad mínima de existencias. ``(num)``

### Material:
- Identificador. ``(ID)(UNIC)(PrimaryKey)``
- Nombre. ``(String)``
- Categoría. ``(String)``
- Descripción. ``(String)``
- Precio compra. ``(num)``
- Cantidad disponible. ``(num)``
- Mínima de existencias. ``(num)``

### Clientes:
- Identificador. ``(ID)(UNIC)(PrimaryKey)``
- Nombre  ``(String)``
- Apellidos. ``(String)``
- Teléfono de contacto. ``(num)``
- Correo. ``(String)``

### Servicios-Reservados_Clientes:
- Identificador Cliente. ``(ID)(UNIC)(PrimaryKey)``
- Identificador Reservas. ``(ID)(UNIC)(ForeignKey)``

### Servicios:
- Identificador. ``(ID)(UNIC)``
- Nombre. ``(String)``
- Categoría. ``(String)``
- Descripción. ``(String)``
- Precio.``(num)``
- Duración estimada. ``(num)``
- Material implicados: ``(String)``
- Especialidades profesionales necesarias. ``(String)``

### Reservas:
- Identificador. ``(ID)(UNIC)(PrimaryKey)``
- ID cliente. ``(ID)(UNIC)(ForeignKey)``
- ID servicio. ``(ID)(UNIC)(ForeignKey)
- ID personal. ``(ID)(UNIC)(ForeignKey)
- Nombre cliente. ``(String)``
- Servicio solicitado. ``(String)``
- Fecha. ``(Date)``
- Hora de inicio. ``(num)``
- Hora de finalización o duración. ``(num)``
- Empleada asignada. ``(String)``
- Precio del servicio. ``(num)``
- Estado de la reserva. ``(String)``

### Personal:
- Identificador. ``(ID)(UNIC)``
- ID servicio. ``(ID)(UNIC)(ForeignKey)
- Nombre y apellidos. ``(String)``
- Teléfono o correo de contacto.  ``(num)``
- Especialidades. ``(String)``
- Listado de servicios completados. ``(String)``
- Horario laboral. ``(num)``
- Máximo de horas de trabajo por jornada. ``(num)``
- Tarifa por hora. ``(num)``
- Estado: activa o inactiva. ``(Bolean)``

### Gestión económica:
- Servicios completados. ``(num)``
- Ingresos generados por servicios. ``(num)``
- Ingresos agrupados por tipo de servicio. ``(num)``
- Gastos compras de productos. ``(num)``
- Coste del personal. ``(num)``
- Beneficio estimado. ``(num)``
- Evolución de los ingresos y gastos por periodos. ``(num)``
