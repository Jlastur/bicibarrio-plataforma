# BiciBarrio - SLO del servicio de reservas

## 1. Objetivo

Definir y evaluar el objetivo de nivel de servicio (SLO)
del sistema de reservas de BiciBarrio.

## 2. Indicador de nivel de servicio (SLI)

El SLI utilizado es la disponibilidad del servicio,
calculada a partir de las peticiones que no devuelven
errores HTTP 5xx.

Datos del periodo de 30 días:

- Peticiones totales: 1.200.000
- Errores HTTP 5xx: 1.140
- Peticiones sin errores 5xx: 1.198.860

Disponibilidad = (1.198.860 / 1.200.000) × 100

Resultado: 99,905 %

## 3. Objetivo de nivel de servicio (SLO)

Se establece un SLO de disponibilidad del 99,9 %
para un periodo de 30 días.

## 4. Presupuesto de errores

Con un SLO del 99,9 %, el presupuesto mensual
es de 1.200 peticiones fallidas.

- Errores registrados: 1.140
- Presupuesto consumido: 95 %
- Presupuesto restante: 60 errores

El SLO se cumple, aunque el margen restante
es reducido.

## 5. Política de presupuesto de errores

Se establecen las siguientes medidas según el porcentaje
del presupuesto de errores consumido:

- Más del 50 %: revisar los cambios y reforzar las pruebas.
- A partir del 80 %: priorizar la fiabilidad y detener
  los despliegues no esenciales.
- Al alcanzar el 100 %: detener los cambios no urgentes
  hasta recuperar un presupuesto disponible.

## 6. Postmortem del incidente

### Descripción

Durante la tercera semana, el martes a las 14:10,
un despliegue provocó un incremento de errores HTTP 5xx
en el servicio de reservas.

El incidente duró aproximadamente 40 minutos y
se realizó una reversión del despliegue a las 14:50.

### Impacto

Durante la tercera semana se registraron 640 errores
HTTP 5xx.

No se dispone de información suficiente para atribuir
todos esos errores exclusivamente al incidente.

### Acciones de mejora

- Mejorar la monitorización y las alertas.
- Validar la configuración antes de cada despliegue.
- Reforzar las pruebas previas a producción.
- Reducir el tiempo necesario para revertir cambios.
- Evitar despliegues en horarios críticos cuando sea posible.
- Valorar despliegues progresivos para reducir riesgos.
