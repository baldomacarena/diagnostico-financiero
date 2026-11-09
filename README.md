# 📊 Diagnóstico Financiero

🔗 **Ver la app online en GIT PAGES:** [baldomacarena.github.io/diagnostico-financiero](https://baldomacarena.github.io/diagnostico-financiero/)

Plantilla web para armar, mes a mes, los tres estados que muestran la situación real de una empresa:
**estado de resultado**, **cashflow** y **balance**. Se cargan los números del mes y los resultados
se calculan solos, con un semáforo que marca en qué etapa se rompe el negocio.

## Qué incluye

| Vista | Pregunta que responde | Resultado principal |
|---|---|---|
| **Estado de resultado** | ¿El negocio gana plata? | Ganancia bruta → EBITDA → Resultado neto → Después de deudas |
| **Cashflow** | ¿Alcanza la plata? | Saldo inicial + entradas − salidas = saldo final (con control contra el saldo real) |
| **Balance** | ¿Dónde está parada la empresa? | Activo − Pasivo = Patrimonio neto, liquidez y capital de trabajo |

Cada vista tiene **carga mensual** y **vista anual** con los 12 meses y el total.

## Estado de resultado

```
  Ventas (por canal)
− CMV
= Ganancia bruta
+ Ingresos por envíos
− Estructura y costos (sueldos, servicios, logística, publicidad, plataformas…)
= EBITDA
− Intereses e impuestos
= Resultado neto
− Deuda (cuotas de capital)
= Lo que queda después de pagar deudas
```

- Cada importe se carga **sin IVA o con IVA**: la app calcula el otro según la alícuota del rubro
  (0 %, 10,5 %, 21 % o 27 %), y todo se puede ver de las dos formas.
- **Semáforo por etapa:** *Bien* (queda más del 5 % de las ventas), *Justo* (entre 0 y 5 %),
  *En rojo* (negativo). La primera etapa en rojo se marca como **Falla acá**.
- **Punto de equilibrio:** cuánto hay que vender por mes para cubrir la estructura.
- Pestaña **Cómo se lee**, con un ejemplo de $100 para explicar la cascada.

## Cashflow

Cajas (bancos, billeteras, efectivo, inversiones) con saldo inicial y saldo final real; entradas
(cobros por ventas y otras entradas); salidas operativas; deuda y otras salidas. El saldo inicial
se toma automáticamente del saldo final del mes anterior, y se compara el saldo calculado con el real.

## Balance

Activo corriente y no corriente, pasivo corriente y no corriente. *Caja y bancos* se completa sola
con el saldo final real del cashflow. Calcula patrimonio neto, liquidez corriente y capital de trabajo.

## Personalizar

Con **Editar conceptos** se agregan, renombran o quitan canales, rubros y conceptos, y se elige la
alícuota de IVA de cada rubro. Cada concepto se puede marcar con el pincel: **rojo** = revisar,
**amarillo** = falta completar.

## Datos

No hay servidor ni base de datos: todo se guarda en el **navegador** (`localStorage`) de quien la usa.
Los datos no se envían a ningún lado, pero tampoco se comparten entre computadoras: cada navegador
tiene los suyos. *Limpiar plantilla* borra los números del mes seleccionado.

## Ejecutarla

Abrir `index.html` en cualquier navegador. No requiere instalación.

## Tecnologías

HTML, CSS y JavaScript puro, en un solo archivo. Sin dependencias ni proceso de build.

## Autora

Macarena Baldo
