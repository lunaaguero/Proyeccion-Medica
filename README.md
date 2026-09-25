# Proyección económica de trayectorias médicas

Calculadora web interactiva que compara, a diez años (2027–2036), el ingreso neto anual de una médica recién egresada en Argentina según tres trayectorias profesionales:

- Residencia de especialidad en Argentina.
- Formación MIR en España, previa homologación del título.
- Trabajo remoto en health tech desde Argentina, con ingresos en moneda fuerte.

**Demo:** https://lunaaguero.github.io/proyeccion-medica/

## El problema

Quien egresa de Medicina en Argentina y evalúa formarse en el exterior o reorientarse a health tech enfrenta una decisión con variables difíciles de comparar: sueldos en pesos frente a sueldos en euros, inflación y devaluación, años de demora por la homologación y diferencias en el costo de vida. Las comparaciones habituales convierten los sueldos al tipo de cambio del día y omiten estas dinámicas. Esta herramienta permite modelarlas de forma explícita y ajustar cada supuesto.

## Metodología

- Horizonte de diez años desde 2027.
- Los sueldos argentinos se ingresan en pesos, con 13 pagos anuales (aguinaldo), y se convierten a euros al tipo de cambio elegido.
- Un parámetro de brecha entre salarios y devaluación capta la erosión (o recuperación) del ingreso argentino medido en euros.
- La ruta española incluye una etapa de homologación con ingresos reducidos y costos de traslado.
- La ruta remota interpola el salario en dólares entre el nivel inicial y el senior (crecimiento implícito ≈ 14% anual con los valores de referencia), suma una prima opcional por perfil médico, descuenta impuestos y comisiones de cobro y convierte a euros. Permite modelar años de búsqueda antes del primer puesto.
- Un ajuste opcional por poder de compra pondera los ingresos gastados en Argentina frente al costo de vida en Madrid. Se aplica también a la ruta remota, porque el ingreso se cobra en moneda fuerte pero se gasta en Argentina.
- Vistas de ingreso anual y acumulado, con el total a diez años por trayectoria.

## Fuentes de los valores iniciales

- Residencia y planta en Argentina: grilla salarial CICOP, provincia de Buenos Aires, abril de 2026.
- MIR y facultativos especialistas en España: retribuciones de residentes de la Comunidad de Madrid 2026 y promedios publicados.
- Tipo de cambio EUR/ARS de junio de 2026 e inflación interanual de marzo de 2026.
- Health tech remoto: guía salarial 2026 de HireTalent.lat para Health Informatics Specialist en Argentina, contratado de forma remota por empresas de EE.UU. Nivel inicial (1–3 años de experiencia): US$ 14.000 anuales. Nivel senior (6+ años): US$ 31.000 anuales. Datos a marzo de 2026, elaborados a partir de Deel, Glassdoor, PayScale y otras fuentes.
- Tipo de cambio euro/dólar: cotización de julio de 2026 (1 € ≈ 1,15 US$).
- Supuestos propios, sin fuente directa y editables: prima por perfil médico (0%), costo impositivo y de cobro (5%), crecimiento posterior al nivel senior (3% anual).

Los valores son de referencia y todos son editables. Es un modelo exploratorio, no un asesoramiento financiero.

## Tecnología

- HTML, CSS y JavaScript en un único archivo, sin backend.
- Gráficos con Chart.js.
- Los supuestos se guardan en el navegador de cada usuario (localStorage).
- Diseño responsive con modo claro y oscuro.

## Autoría

Diseño del problema, definición de variables, selección de fuentes y validación del modelo: **Luna Agüero**, estudiante de Medicina, Universidad Nacional del Sur (Bahía Blanca, Argentina).

Construcción del código con asistencia de IA (Claude, de Anthropic).

[LinkedIn](https://www.linkedin.com/in/luna-ag%C3%BCero/)
