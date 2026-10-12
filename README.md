# Ejercicio 20 - Modelo Entidad-Relación de un Sistema de Coworking

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de gestión de espacios de coworking. El modelo permite administrar espacios de trabajo, miembros registrados, reservas de espacios, controles de acceso mediante fichaje y consumos adicionales.

## Entidades y atributos

### 1. Espacio Trabajo
Representa las áreas, salas o puestos disponibles para alquiler dentro del coworking.
- **id_espacio**: identificador único del espacio de trabajo.
- **nombre**: nombre o denominación del espacio.
- **tipo**: categoría del espacio (ej. oficina privada, sala de reuniones, escritorio flexible).
- **capacidad maxima**: número máximo de personas admitidas.
- **tarifa hora**: costo por hora de uso del espacio.

### 2. Miembro
Representa a los usuarios o profesionales registrados en la comunidad de coworking.
- **id_miembro**: identificador único del miembro.
- **dni**: documento nacional de identidad.
- **nombre**: nombre y apellido del miembro.
- **empresa**: organización o compañía a la que pertenece.
- **correo**: correo electrónico de contacto.
- **nro tarjeta rfid**: número identificador de la tarjeta de proximidad para acceso.

### 3. Reserva
Representa las solicitudes de reserva de los espacios de trabajo realizadas por los miembros.
- **id_reserva**: identificador único de la reserva.
- **id_miembro**: identificador del miembro solicitante.
- **id_espacio**: identificador del espacio reservado.
- **fecha uso**: fecha programada para el uso del espacio.
- **hora inicio**: hora de comienzo de la reserva.
- **hora fin**: hora de finalización de la reserva.

### 4. Control Acceso
Representa el registro de fichajes o entradas y salidas de los miembros mediante tarjetas RFID.
- **id_fichaje**: identificador único del registro de acceso.
- **id_miembro**: identificador del miembro que accede.
- **nro tarjeta leida**: número de la tarjeta escaneada en el lector.
- **fecha hora**: marca temporal del acceso.
- **sentido**: dirección del movimiento (ej. entrada, salida).

### 5. Consumo
Representa los consumos adicionales o extras realizados por los miembros (ej. cafetería, impresiones).
- **id_consumo**: identificador único del consumo.
- **id_miembro**: identificador del miembro que realiza el consumo.
- **fecha hora**: marca temporal de la transacción.
- **descripcion item**: detalle o nombre del producto o servicio consumido.
- **cantidad**: unidades consumidas.
- **precio unitario**: costo por unidad del ítem.

## Relaciones y cardinalidades
- **Espacio Trabajo – Reserva (Bloqueado / 1:N)**: un espacio de trabajo puede estar involucrado en múltiples reservas programadas.
- **Miembro – Reserva (Solicita / 1:N)**: un miembro puede realizar diversas reservas de espacios de trabajo.
- **Miembro – Control Acceso (Registra / 1:N)**: un miembro genera múltiples registros de fichaje de entrada y salida mediante su tarjeta.
- **Miembro – Consumo (Extra / 1:N)**: un miembro puede registrar diversos consumos adicionales dentro de las instalaciones.

## Objetivo
Diseñar una base de datos para la gestión integral de un espacio de coworking que permita administrar la disponibilidad de los espacios de trabajo, registrar los datos de los miembros y sus tarjetas de acceso, controlar las reservas de salas, llevar un registro detallado del control de accesos (fichajes) y gestionar los consumos adicionales de la comunidad.
