# BiciBarrio - Decisión de arquitectura cloud

## 1. Objetivo

Documentar la elección del proveedor cloud y el diseño
propuesto para la plataforma BiciBarrio.

## 2. Proveedor seleccionado

Se selecciona Amazon Web Services (AWS) como proveedor
de servicios cloud.

## 3. Regiones

- Región principal: eu-south-2 (España).
- Región secundaria: eu-west-3 (París).

La región principal alojaría los servicios de producción.

La región secundaria se utilizaría para apoyar la
estrategia de recuperación ante desastres.

## 4. Disponibilidad y recuperación

Se propone distribuir los componentes necesarios
entre dos zonas de disponibilidad de la región principal.

Objetivos de recuperación:

- RTO: 45 minutos.
- RPO: 10 minutos.

Estos valores son objetivos de diseño que deberán
validarse mediante pruebas de recuperación.

## 5. Modelos de servicio

- Aplicación web: IaaS.
- API: PaaS.
- Base de datos: PaaS.
- Pasarela de pagos: SaaS.
- Correo electrónico: SaaS.
- Monitorización: PaaS.

## 6. Seguridad y responsabilidades

- Aplicar el principio de mínimo privilegio.
- Utilizar MFA para proteger los accesos.
- Controlar los permisos de usuarios y servicios.
- Proteger los datos almacenados mediante cifrado.
- Evitar el acceso público innecesario a los servicios.
- Gestionar las credenciales y secretos de forma segura.
- Delegar el procesamiento de pagos en una pasarela
  especializada, sin almacenar datos de tarjetas.

La responsabilidad sobre la seguridad se comparte
entre AWS y el cliente, según el modelo de servicio.
