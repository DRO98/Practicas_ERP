# Guía de formación — Panel de administración del ERP

> **¿Para qué sirve esta guía?**
> Sois los primeros ojos frescos que prueban esta aplicación. Vuestro trabajo no es programar ni entender el código: es usar el panel como lo haría un administrador de club real, explorar cada rincón, intentar cosas raras y anotar todo lo que encuentréis. Cuanto más detalle, mejor. Esta guía os explica qué hace cada pantalla, qué deberíais ver si todo va bien y qué situaciones hay que forzar a propósito.

---

## Antes de empezar — lo que necesitáis tener claro

### Teneis que inciar sesion con la cuenat y contraseña que os he facilitado, y tendreis que hacer esta practica en paralelo con el erp abierto, para ir entendiendo todo al mismo tiempo (https://app.sportimizer.es/) esta es la app.

### ¿Qué es este panel?

Es la herramienta de gestión interna de un club deportivo. Desde aquí, el administrador controla quién forma parte del club, cuánto paga cada familia, los equipos de cada temporada y las cuentas del club. Vosotros entraréis con el rol de **Admin**, que tiene acceso a todo.

### Regla de oro: trabajad solo con datos ficticios

Usad nombres inventados, correos del tipo `prueba1@test.com`, IBANs de ejemplo (podéis usar `ES91 2100 0418 4502 0005 1332`, es un IBAN de prueba estándar). **Nunca uséis datos reales de personas.**

### Cómo documentar un fallo

Cuando algo no funciona como esperabais, anotad exactamente:

1. **Qué hicisteis** paso a paso (tan detallado que otra persona pueda repetirlo sin preguntar).
2. **Qué esperabais que pasara.**
3. **Qué pasó en realidad** (con captura de pantalla).

Si la pantalla muestra un mensaje de error, copiad el texto exacto del mensaje.

---

## 1. Conceptos clave — qué significa cada cosa

### El club y sus datos

Cada administrador solo ve los datos de su propio club. Si en algún momento vierais nombres, números o equipos que no habéis creado vosotros, es un problema grave: documentadlo con capturas.

### Los roles: quién es quién

La aplicación tiene distintos tipos de cuenta. Es importante entenderlo porque muchas pantallas se comportan diferente según el rol del usuario que estáis editando.

| Rol | Qué hace en el club |
|-----|---------------------|
| **Administrador** | Gestiona todo desde este panel. Sois vosotros durante las pruebas. |
| **Entrenador** | Gestiona convocatorias y plantilla de su equipo. |
| **Jugador** | El deportista. Si es menor de edad, suele tener un tutor que paga por él. |
| **Padre / Madre / Familiar** | Tutor vinculado a un jugador; normalmente es quien paga las cuotas del menor. |
| **Fisio** | Acceso a citas y notas médicas del club. |

**Detalle importante:** cada dirección de email debe corresponder a una sola cuenta. Si la app permite crear dos cuentas con el mismo correo, es un fallo a documentar.

### Tipos de registro: ¿ya puede entrar o no?

No todos los usuarios en la lista tienen acceso real a la app. Hay tres situaciones:

- **Cuenta activa:** la persona puede entrar normalmente con su email y contraseña.
- **Preinscripción:** el club ya la ha dado de alta (por ejemplo, importando un Excel), pero la persona todavía no ha completado su registro. Aparece en los listados, pero no puede entrar hasta que termine el proceso.
- **Ficha interna:** borrador creado por administración para gestión interna, por ejemplo un jugador del que aún no se tiene email.

Si después de que un preinscrito completa su registro desaparecen sus datos (cuotas, hijos vinculados, pagador), es un fallo grave.

### La temporada deportiva

El club trabaja por temporadas (ejemplo: 2025–2026). Solo una está **activa** en cada momento, y es la que usa la app de referencia para mostrar equipos, jugadores y datos.

Si cambiáis la temporada activa a mitad de las pruebas, puede que veáis equipos "antiguos" o jugadores sin equipo asignado. Anotad siempre si la pantalla avisa de este cambio o si simplemente os deja en un estado confuso sin ningún mensaje.

### Quién paga las cuotas de un menor

Este concepto aparece mucho en las pruebas, así que conviene tenerlo claro:

1. Si el jugador es menor, suele haber un tutor marcado como **pagador principal** → las cuotas van asociadas a ese tutor.
2. Si el jugador es mayor y no tiene tutor, puede pagar él mismo → aparece como **"Propio"** en la contabilidad.
3. Si hay tutores vinculados pero ninguno está marcado como pagador → **situación incorrecta**. La tarjeta "Estado del sistema" en Usuarios muestra cuántos jugadores están en esta situación y debería ser siempre 0.

### Qué es un movimiento y qué es una cuota

- **Cuota (plantilla):** una regla del tipo "este jugador paga 50 € cada mes". La plantilla genera movimientos automáticamente.
- **Movimiento:** cada línea individual de cargo en la contabilidad (un pago concreto, con su fecha, estado e importe).

---

## 2. El menú lateral — visión general

Al entrar veréis un menú a la izquierda con estas secciones:

| Sección | Para qué sirve |
|---------|----------------|
| **Usuarios** | Altas, bajas, edición de personas, vínculos tutor–hijo, pagadores. |
| **Ligas y equipos** | Temporadas, categorías, equipos, importación masiva desde Excel. |
| **Contabilidad** | Ingresos, cuotas, gastos, cobros, informes. |
| **Herramientas** | Impagos, diagnósticos, configuración del club. |
| **Estadísticas** | Gráficas y resumen financiero del club. |
| **Auditoría** | Historial de acciones: quién hizo qué y cuándo. |
| **Comunicación** | Mensajes internos entre roles. |
| **Documentación** | Fichas, licencias y documentos del personal. |
| **Calendario** | Eventos y notas internas. |
| **Stock** | Inventario y tienda del club. |
| **Marketing** | Generador de textos para redes sociales. |
| **Patrocinadores** | Catálogo de patrocinadores del club. |

**Norma antes de pulsar "Eliminar" o "Guardar":** leed siempre el mensaje de confirmación si aparece. Si la acción es definitiva y no hay ninguna confirmación previa, anotadlo como posible mejora.

**Orden de trabajo:** el camino recomendado para practicar está en **§3 y siguientes** (Herramientas → Contabilidad → Estadísticas → Usuarios → Ligas). No coincide con el orden en que aparecen las entradas en el menú lateral; seguid la numeración de esta guía.

---

## 3. Cómo está organizada esta guía y cuaderno de datos

### 3.1 Qué vais a hacer en cada parte

Esta guía alterna **dos tipos de contenido**:

1. **Teoría del módulo** — qué pantalla es, qué botones tiene y qué debería pasar en condiciones normales.
2. **Misiones** — ejercicios concretos para que **interactuéis con la aplicación** justo después de haber leído ese módulo.

El **protocolo beta** (preguntas sobre documentación y UX por módulo) está en **§3.3**.

Las misiones **no** aparecen “de la nada”: cuando lleguéis a una, ya habréis tenido delante la explicación del flujo. Si una misión necesita algo de **otro** módulo (por ejemplo, contabilidad necesita **cuentas bancarias**), el texto lo dice explícitamente: *creáis antes la cuenta en Herramientas, como haría un administrador real*.

El orden de lectura recomendado sigue una **cadena realista**: primero lo que habilita el resto (cuentas del club), luego el dinero (contabilidad), luego el resumen (estadísticas), luego personas (usuarios), luego deportivo (ligas). El menú lateral del ERP no coincide con ese orden; **seguid la numeración de esta guía**, no el orden alfabético del menú.

### 3.2 Cuaderno de datos ficticios (usad siempre los mismos valores)

Para que otro compañero pueda reproducir vuestras pruebas y los números cuadren entre sí, usad **exactamente** esta tabla. No improviséis variantes salvo que el enunciado pida algo distinto.

| Clave | Valor fijo |
|-------|------------|
| Cuenta caja | **Caja Prueba ALPHA** (tipo caja) |
| Cuenta banco | **Banco Prueba BETA** (tipo banco) |
| IBAN de ejemplo | `ES91 2100 0418 4502 0005 1332` |
| Categoría ingreso | **Cuotas formación** |
| Categoría gasto | **Material formación** |
| Texto externo ingreso | **Donante Club Prueba S.L.** |
| Jugadora | **Lucía Demo Ruiz** — `lucia.demo.lab@test.com` |
| Tutor | **Carlos Tutor Demo** — `carlos.tutor.demo@test.com` |
| Temporada ligas | **2026-2027 Formación** |
| Categoría deportiva | **Alevín Formación** |
| Equipo | **Tiburones Formación** |

**Hoja de control:** tras las misiones de **Estadísticas** y las de **Contabilidad** (importe / ingreso vinculado), anotad en papel los KPI de **Estadísticas** (Global + Flujo real + Bruto): Ingresos / Gastos / Margen / Impuestos.

### 3.3 Protocolo beta — documentación y UX

Esta guía es **borrador** de lo que será la documentación oficial para gestores de club. Por eso necesitamos vuestra lectura crítica.

- **Documentación:** en **cada ejercicio guiado o misión numerada**, anotad **qué parte de esta guía** (apartado, tabla o frase concreta) **no** habéis entendido, habéis tenido que releer varias veces o **no coincide** con lo que muestra la aplicación. Cuanto más preciso sea el parágrafo que citéis, mejor.
- **UX por módulo:** al terminar cada bloque **§4 a §11** (teoría + pruebas previstas en esa sección), responded siempre la pregunta de cierre: **¿Mejorarías algo notorio del UX?**

*(En algunos apartados la pregunta sobre documentación se repite explícitamente al pie del ejercicio.)*

---

## 4. Herramientas

### 4.1 Las tres pestañas

**General:** tarjetas en cuadrícula con varias herramientas:
- **Configuración del club:** URL de tienda externa.
- **Alertas de administración:** notificaciones del sistema con botón "Marcar leída".
- **Alertas de stock:** artículos por debajo del mínimo.
- **Cuentas bancarias:** lista de cuentas del club con opción de añadir, editar y borrar.
- **Impagos / vencidos:** tabla con fecha de corte, retraso e importe. Exportable a Excel.
- **Diagnóstico de equipos:** herramienta de **consistencia de datos** entre la **temporada activa** del club y las **plantillas** (equipos) en las que está cada jugador.

**Qué es exactamente el diagnóstico de equipos**

La aplicación trabaja con una **temporada activa** (la elegida en Ligas como referencia actual). Cada jugador puede estar asignado a un equipo que pertenece a **una temporada concreta**. Si **cambiáis la temporada activa** o hay datos cargados a medias, puede ocurrir que una persona **siga apareciendo en el equipo de una temporada que ya no es la de referencia**, o que la lógica del sistema detecte que esa asignación **no encaja** con la temporada marcada como activa.

En ese caso, la herramienta **no “juzga” al jugador**: muestra una **tabla de avisos** con filas que resumen el problema (por ejemplo, jugador X ligado a un equipo de la temporada antigua). **Esperado en clubes bien mantenidos:** tabla vacía. **Si hay filas:** son personas que el administrador debería revisar en **Ligas / Usuarios** para alinear temporada y equipo. Sin jugadores en equipos (club nuevo), lo normal es que la tabla salga **vacía** — no es un fallo vuestro.

**Identidad del Club:** colores del club, logo, nombre visible en la app. Tiene protección contra edición simultánea de dos administradores (debe aparecer un mensaje de conflicto si dos admins guardan a la vez).

**Verificaciones (Bizum):** lista de pagos que los socios han marcado como realizados por Bizum o transferencia, pendientes de que el admin los confirme o deniegue.

### 4.2 Lectura: comportamiento esperado (sin hacer pruebas aún)

Estos párrafos **explican qué deberíais entender** antes de pulsar nada. Las **preguntas concretas** (“¿qué veis en pantalla?”) están en los apartados **4.3** y **4.5**, y solo donde haga falta crear datos antes os lo indicamos.

**Configuración del club — URL de tienda**

Si guardáis una dirección **sin** `https://` (por ejemplo solo `www.club.es`), la aplicación suele **validar el campo** y rechazar el guardado o **normalizar** la URL. Lo importante para las pruebas es si el **mensaje** dice claramente qué falta; eso se puede comprobar **sin haber creado usuarios ni equipos**.

**Impagos / vencidos — fecha de corte en el futuro**

La fecha de corte significa “hasta qué día miramos los vencimientos”. Si ponéis una fecha **en el futuro**, es normal que la lista salga **vacía**: ningún movimiento aparece como “ya pasado” respecto a un día que aún no ha llegado. **Vacío en ese caso suele ser comportamiento correcto**, no bug.

**Diagnóstico de equipos — después de trabajar con Ligas**

Esta herramienta solo tiene sentido cuando en el club hay **jugadores asignados a equipos** y habéis tocado **temporadas**. Si ejecutáis el diagnóstico en un club sin esos datos, veréis sobre todo una tabla vacía o un mensaje genérico: **no interpretéis eso como error**. Cuando ya tengáis temporadas y plantillas (véase **§8** y la misión **LG1**), podréis seguir el **§4.5** para ver si, al cambiar la temporada activa, aparecen filas en la tabla del diagnóstico que correspondan a asignaciones antiguas.

**Identidad del club — dos pestañas abiertas**

El panel guarda la configuración en el servidor. Si dos administradores (o dos pestañas) guardan casi a la vez, el segundo puede recibir un **conflicto** (en API suele codificarse como **409**): significa “otro guardado ganó antes”. La interfaz debería mostrar un **mensaje comprensible**, no una pantalla rota sin texto.

**Verificaciones Bizum**

Si no hay solicitudes pendientes, la pantalla puede estar **vacía**. Lo que debéis documentar es si hay **texto de ayuda** (“no hay pagos pendientes”, etc.) o si parece un fallo (pantalla en blanco sin contexto).

### 4.3 Ejercicios rápidos (no requieren jugadores en equipos)

Haced solo lo que encaje con vuestro entorno; anotad **qué visteis**.

1. **URL:** en Configuración del club, escribid solo `www.ejemplo-de-prueba.local` y guardad. ¿La app muestra un **mensaje claro** o corrige sola la URL?
2. **Identidad — dos pestañas:** abrid Identidad del club en **dos pestañas** del mismo navegador; guardad en la primera y luego guardad en la **segunda sin recargar**. ¿Aparece un aviso de **conflicto** o código **409**?
3. **Vencidos — fecha futura:** abrid la tarjeta de vencidos, poned fecha de corte **dentro de dos meses** y pulsad Ver Vencidos. ¿La tabla sale **vacía** sin error técnico?
4. **Bizum:** abrid Verificaciones Bizum. Si no hay datos, ¿hay **mensaje orientativo** o solo blanco?

**Feedback documentación (beta):** ¿Qué parte de lo que acabáis de leer (**§4.3** o la guía entera hasta aquí) **no** habéis entendido del todo?

### 4.4 Ejercicio guiado — **Impagos / vencidos** (“Ver Vencidos”)

> Práctica recomendada **después** de la **misión de cuentas** al final de esta sección y de saber crear un ingreso en **§5**, porque el paso 1 usa Contabilidad.

En **Herramientas → pestaña General**, localizad la tarjeta de **impagos o movimientos vencidos** (en código aparece como listado con **Fecha de corte**, botón **Ver Vencidos**, tabla con columnas **ID, Estado, Fecha Pago, Retraso, Importe, Usuario** y botones **Limpiar** y **Excel**).

**Qué significa la fecha de corte**

La fecha que elegís es el **día de referencia** (“como si hoy fuera ese día”). La aplicación calcula **retraso en días** respecto al **inicio de ese día** en vuestra zona horaria.

- Movimientos en estado **pendiente** que entran en el listado: tienen **fecha de pago anterior** al comienzo del día de corte (es decir, ya “vencieron” respecto a ese calendario). Un pendiente con fecha de pago **el mismo día** que la fecha de corte **no** suele aparecer como vencido.
- Movimientos en estado **impago**: en la práctica se incluyen en el resultado **sin aplicar ese filtro de fecha** en el navegador (sí debéis verlos si el API los devuelve).

**Pasos recomendados**

1. **Antes:** en **Contabilidad → Ingresos**, cread un ingreso o cuota **Pendiente** con **fecha de pago** **varios días en el pasado** (ej. hace 15 días) e importe ficticio pequeño.
2. Id a **Herramientas → General** → tarjeta **Impagos / vencidos**. Poned la **Fecha de corte** en **hoy** (o en un día **posterior** a la fecha de pago del movimiento).
3. Pulsad **Ver Vencidos**.

**Esperado:** la fila **pendiente** aparece, con **Retraso** ≥ 1 días e **importe** coherente.

4. Pulsad **Excel** y abrid el archivo: ¿las columnas coinciden con la tabla?

5. Pulsad **Limpiar**: la tabla de resultados debe vaciarse (no confundir con borrar movimientos en BD).

6. Cambiad el movimiento en Contabilidad a **Pagado** y volved a ejecutar **Ver Vencidos** con la misma fecha de corte.

**Esperado:** ese recibo **ya no** debe salir como vencido (o debe cambiar el criterio visible). Si sigue apareciendo, documentadlo como posible bug con capturas.

**Conexión con otros módulos**

- Los importes de esta tabla deben ser **coherentes** con lo que veis en **Contabilidad** para el mismo **ID** de movimiento.
- El **informe PDF** usa otros agregados (flujo cobrado, morosidad por usuario); si quien coordine las pruebas pide contrastar, buscad el apartado de morosidad / pendientes en el PDF y verificad que no contradice gravemente el listado de vencidos para el mismo periodo.

**Feedback documentación (beta):** ¿Qué parte de **§4.4** no queda clara al usar la pantalla real?

### 4.5 Ejercicios con temporadas y plantillas (después del §8 o cuando ya haya jugadores en equipos)

**Cuándo hacerlos:** cuando existan **jugadores asignados a equipos** en **Ligas** (por ejemplo tras la misión **LG1** o datos que ya trajera el club).

1. Anotad **cuántas filas** muestra el diagnóstico **antes** de cualquier cambio (puede ser 0).
2. En **Ligas**, cambiad la **temporada activa** a otra distinta (según permisos del entorno de prueba).
3. Volved a **Herramientas → Diagnóstico de equipos** y ejecutad de nuevo.
4. **Qué observar:** si hay jugadores que **siguen figurando solo en equipos de la temporada ya no activa**, es habitual que **aparezcan nuevas filas** en la tabla del diagnóstico describiendo esa situación (texto que indica desajuste temporada/equipo — el wording exacto depende de la versión). Si la tabla **sigue vacía** pero sabéis que hay desajuste manual, documentadlo como posible mejora de detección.
5. **Opcional:** volved a dejar la temporada activa como estaba y comprobad si el diagnóstico vuelve al estado anterior.

**Feedback documentación (beta):** ¿Qué parte de **§4.5** o del diagnóstico de equipos no habéis entendido?

---

### Misión — Cuentas bancarias (previo obligatorio para Contabilidad)

**Dependencias:** ninguna; es el primer paso práctico típico de un club nuevo.

**Dónde:** **Herramientas → pestaña General → Cuentas bancarias**.

1. Crear **Caja Prueba ALPHA** (tipo **caja**, saldo inicial **0**, salvo indicación de quien coordine las pruebas).
2. Crear **Banco Prueba BETA** (tipo **banco**, IBAN de la tabla del §3.2 si el formulario lo pide, saldo **0**).

**Comprobación:** en **Contabilidad → Nuevo ingreso**, ambas deben aparecer en el desplegable **Cuenta**. Si no, no sigáis con las misiones de contabilidad hasta que esto funcione.

**Feedback documentación (beta):** ¿Qué parte de las instrucciones de **§4** (misión cuentas incluida) no se entiende sin ayuda externa?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 5. Contabilidad — ingresos, gastos y cuotas

### 5.0 Léeme primero — vocabulario en castellano claro

Esta sección usa a veces palabras que en informática suenan familiar pero **no** son obvias si no habéis tocado una app contable. Aquí van en lenguaje normal:

| Lo que podéis leer | Qué significa en la práctica |
|--------------------|-----------------------------|
| **Mensaje emergente** | Aviso **breve** que aparece en pantalla (muchas veces **arriba a la derecha**), sin tapar del todo el trabajo, y que **se oculta solo** al cabo de unos segundos. En documentación técnica se llama a veces *toast*; **en esta guía usamos solo “mensaje emergente”**. Si la app solo muestra texto rojo dentro del cuadro del formulario, eso **no** es lo mismo: contadlo como “mensaje de error en el modal”. |
| **Gráfico circular / “donut”** | El **gráfico en forma de rosca** en **Estadísticas** que parte el pastel entre categorías (gastos o ingresos). Cada porción es una categoría económica. |
| **Flujo de Caja Real** | Modo en Estadísticas: solo cuenta movimientos **Pagados** (dinero que ya habéis cobrado o pagado de verdad). |
| **Proyección contable** | Modo en Estadísticas: cuenta **Pagados + Pendientes** (incluye cobros emitidos que aún no habéis cobrado). |
| **Plantilla de cuota** | Regla tipo “cada mes generar un cargo de X € con este concepto”. Los cobros concretos aparecen como **filas en la tabla de Ingresos** cuando el sistema los crea (en algunos entornos es al momento; en otros puede tardar o necesitar proceso interno — si tras unos minutos no hay nada, **preguntad al coordinador del ensayo**, no asumáis bug). |
| **Nombre en texto / externo** | En un ingreso o gasto, cuando **no** elegís a nadie del listado de socios y **escribís** el nombre a mano (ej. un patrocinador). La tabla debe mostrar **exactamente ese texto**. |
| **Justificante** | Archivo adjunto (foto de ticket, PDF de factura…). |
| **PDF / Informe** | Documento que generáis con **Generar Informe**: sirve para revisar en un solo archivo lo cobrado/pagado en un **rango de fechas**. |

Si algo en los ejercicios os suena a “paso mágico”, es que falta contexto: **parad y releed el párrafo “Qué estáis comprobando”** antes de ejecutar clics.

### 5.1 Estructura de la pantalla

La página tiene tres zonas principales:

1. **Ingresos y cuotas** — tabla de entradas de dinero del club.
2. **Gastos** — tabla de salidas de dinero.
3. **Cuotas recurrentes** — plantillas que generan cargos periódicos automáticamente.

En la zona superior de la página (toolbar de contabilidad) suelen estar:

| Botón / acción | Para qué |
|----------------|----------|
| **Importar datos económicos (Excel)** | Abre el modal de importación: el **navegador lee** el Excel, comprueba datos y envía el resultado al servidor (no es una subida “ciega” del archivo tal cual). |
| **Generar Informe** | Modal con fecha inicio y fin; genera **PDF** en el navegador con los datos del periodo. |
| **Gestionar categorías económicas** | Modal para crear categorías con **aplica a**: ingreso / gasto / ambas. |

**Sobre la tabla de Ingresos** (botones propios de esa sección en `Contabilidad.jsx`):

| Botón | Para qué |
|-------|----------|
| **+ Nuevo Ingreso** | Alta con autocomplete de usuario o nombre externo, fiscalidad, cuenta, etc. |
| **Avisar deudores** | Tras confirmar, envía avisos por email; suele aparecer un **mensaje emergente** con cuántas personas se han notificado (copiad el texto exacto en vuestra entrega). |
| **Descargar remesa SEPA (PAIN.008)** | Solo si el club tiene modo compatible (`manual_xml` o `ambos`). Requiere **filas seleccionadas**; admite **cuota** o **ingreso** en **pendiente** o **impago** con titular; **excluye** cobros «procesando» por pasarela. Tras generar, los válidos pueden pasar a **Enviado al banco**. |
| **Editar** / **Eliminar** | Operan sobre la **selección** de la tabla (una o varias filas). Eliminación suele pedir confirmación. |
| **Filtrar** | Panel lateral de filtros de ingresos (ver §5.11). |
| **Exportar Excel** | Exporta **Ingresos y Gastos** juntos a un `.xlsx` (útil para auditoría cruzada). |
| **Interruptor Bruto / Neto** | Solo afecta a **cómo se muestra la columna Monto** en esa tabla (no edita el movimiento). Ingresos y gastos llevan **toggle independiente**. |

**Sobre la tabla de Gastos:** mismas ideas (**Nuevo gasto**, selección, editar/eliminar, filtrar, Bruto/Neto). No tiene remesa ni «avisar deudores».

### 5.1.1 Tablas de Ingresos y Gastos — columnas que podéis mostrar u ocultar

En cada tabla hay un control tipo **▾** en la cabecera: podéis elegir **hasta 5 columnas visibles** a la vez (si añadís una sexta, la sustituye).

**Ingresos — nombres de columna en pantalla**

| Columna | Qué es |
|---------|--------|
| **Nombre** | Socio/usuario vinculado o texto libre si el cobro es “externo”. |
| **Monto** | Importe **bruto** (o **neto** si activáis el interruptor Bruto/Neto encima de la tabla). |
| **IVA / Neto** | Resumen fiscal (tasa + base aproximada). |
| **Pagado** | Cuánto del cargo ya se ha cobrado (incluye pagos parciales si aplica). |
| **Estado** | Pendiente, Pagado, Impago, Enviado al banco, etc. |
| **Cuenta de cobro** | Banco/caja donde se contabiliza la entrada. |
| **Categoría** | Etiqueta económica (donut de ingresos en Estadísticas). |
| **Fecha** | Fecha de referencia del movimiento. |
| **Método Pago** | Bizum, transferencia, efectivo… |
| **Justificante** | Archivo adjunto si lo hay. |
| **Observación** | Nota interna. |

**Gastos — columnas**

| Columna | Qué es |
|---------|--------|
| **Nombre** | Proveedor/usuario o texto libre. |
| **Monto** | Bruto o neto según el interruptor de la sección Gastos. |
| **IVA / Neto** | Desglose fiscal. |
| **Método de pago** | Cómo se pagó. |
| **Categoría** | Etiqueta (donut de **gastos** en Estadísticas). |
| **Observación** | Nota. |
| **Fecha** | Fecha del gasto/pago. |
| **Justificante** | Archivo. |
| **Cuenta de pago** | Desde qué cuenta sale el dinero. |
| **Estado de pago** | Pagado, pendiente, etc. |

**Ideas de prueba:** ocultad **Monto** y mostrad solo **IVA / Neto** + **Estado**; comprobad que seguís entendiendo la fila. Cambiad el toggle **Bruto/Neto** y verificad que el número de la celda cambia sin editar el movimiento.

---

### 5.1.2 Formulario **Nuevo ingreso** — campo a campo

| Campo | Obligatorio | Para qué sirve |
|-------|-------------|----------------|
| **Nombre** | Sí (usuario elegido de la lista **o** texto escrito como “externo”) | Quién aparece en la tabla; si elegís un usuario del club, el ingreso queda vinculado a su ficha. |
| **Importe total (bruto)** | Sí | Dinero efectivo del cobro **con IVA incluido** si aplica (ver §5.3). |
| **Fiscalidad y descuentos** | No | Bloque **IVA** (0 %, 4 %, 10 %, 21 % o personalizado), **% descuento** y **importe antes de descuento (PVP)** para becas o ventas rebajadas; la app puede calcular el % si PVP > monto. |
| **Estado** | Sí | Pagado, Pendiente, Enviado al banco, Procesando, Impago. |
| **Cuenta** | Sí | Dónde se registra el cobro (debéis tener al menos una cuenta creada en **Herramientas** o vía import). |
| **Categoría** | No | Clasificación para informes y donas (solo categorías que aplican a ingreso o “ambas”). |
| **Fecha** | Sí | Se envía como fecha de pago; afecta a informes y estadísticas por periodo. |
| **Método Pago** | Sí | Bizum, transferencia, efectivo, tarjeta, Apple/Google Pay, domiciliación SEPA. |
| **Justificante** | No | Archivo (PDF/imagen). Si adjuntáis fichero, el guardado puede tardar un poco más porque sube el archivo junto con los datos del formulario. |
| **Observación** | No | Texto libre interno. |

**Ejemplo guiado:** ingreso **121 €**, IVA **21 %**, estado **Pagado**, categoría “Cuotas”, método **Transferencia**, fecha **hoy**. En la tabla, columna fiscal debe sugerir base ~100 € y 21 % de IVA.

---

### 5.1.3 Formulario **Nuevo gasto** — campo a campo

| Campo | Obligatorio | Notas |
|-------|-------------|--------|
| **Nombre** | Sí | Igual que ingresos: podéis escribir texto o elegir usuario. |
| **Importe total (bruto)** | Sí | Lo que habéis pagado **con IVA incluido** si aplica. |
| **Fiscalidad y descuentos** | No | Mismo bloque que ingresos. |
| **Método de pago** | Sí | |
| **Categoría** | No | Solo categorías de **gasto** o “ambas”. |
| **Observación** | No | |
| **Fecha** | Sí | |
| **Justificante** | No | Muy útil para auditoría (factura). |
| **Cuenta** | Sí | Desde qué cuenta sale el pago. |
| **Estado** | Sí | Pagado / Pendiente / … |

---

### 5.1.4 Plantilla **Nueva cuota** (Configurar cuotas) — campo a campo

Al pulsar **+ Nueva cuota** aparece un texto de ayuda: los cobros se generan **por cada pagador del club** (jugadores / hijos en familia); la **fecha final es exclusiva** (un cobro el mismo día del “hasta” no se genera).

| Campo | Qué hace |
|-------|----------|
| **Tipo** | **Ingreso** (cobro a socios) o **Gasto** recurrente (menos habitual); la categoría desplegable cambia según el tipo. |
| **Monto** | Importe **por cobro generado**, IVA incl. si aplica (placeholder en pantalla). |
| **Fiscalidad y descuentos** | IVA/PVP/dto aplicados a **cada** línea que genere la plantilla. |
| **Frecuencia** | Mensual, Anual o Matrícula. |
| **Concepto** | Texto del cargo (aparecerá en los movimientos generados). |
| **Día** | Día del mes en que “cae” el cargo (1–31). |
| **Fecha inicio / Fecha final** | Rango en el que la regla está activa; **fin exclusivo**. |
| **Categoría** | **Obligatoria** para poder pulsar **Crear**: si la dejáis vacía, la app muestra error (“Selecciona una categoría económica…”). Debe ser una categoría válida para ingreso/gasto según el **Tipo** elegido. |

En la **tabla** de plantillas podéis mostrar columnas: **Monto**, **Frecuencia**, **Concepto**, **Día**, **Fecha inicio**, **Fecha fin** (hasta 5 visibles).

**Prueba conectada:** cread una cuota mensual ficticia de **5 €**, IVA 0 %, concepto “Prueba cuotas demo”, fechas de inicio/fin coherentes, **categoría** que permita ingresos, y **Crear**. La fila debe aparecer en **Configurar cuotas**. Si en vuestro entorno los movimientos se generan automáticamente (tarea en segundo plano), esperad unos minutos y revisad **Ingresos**; si no aparece nada, **preguntad a quien coordine las pruebas** cómo se dispara la generación en ese club (no asumáis bug al instante). Cuando existan movimientos **pagados** derivados, contrastad **Estadísticas** e **informe PDF** como en §5.4–5.6.

---

### 5.2 Estados de los movimientos

| Estado | Qué significa |
|--------|---------------|
| **Pendiente** | Aún no se ha cobrado. |
| **Pagado** | Cerrado, el dinero ha entrado o salido. |
| **Parcial** | Se cobró algo pero queda saldo. |
| **Esperando transf.** | El socio ha marcado que ha hecho una transferencia o Bizum; el admin debe confirmar. |
| **Enviado al banco / Procesando / Impago** | Estados propios del ciclo de domiciliación SEPA. |

### 5.3 Entender el IVA en la aplicación

Este es el concepto que más confusión genera. Leedlo con atención.

Cuando creáis un movimiento con IVA del 21 %, **el importe que escribís es el total final con IVA incluido** (lo que aparecería en un ticket). La aplicación calcula automáticamente:

- **Base (sin IVA)** = Total ÷ 1,21
- **Cuota de IVA** = Total − Base

**Ejemplo:** escribís **121 €** con IVA 21 % → base **100 €**, cuota IVA **21 €**. No escribís 100, escribís 121.

Referencia para las pruebas:

| Tipo | Total que escribís | IVA | Base resultante | Cuota IVA |
|------|-------------------|-----|-----------------|-----------|
| Ingreso prueba | **50,00 €** | 21% | ~41,32 € | ~8,68 € |
| Gasto prueba | **30,00 €** | 21% | ~24,79 € | ~5,21 € |

Con estas dos líneas:

| Concepto | Resultado esperado |
|----------|--------------------|
| Margen en Bruto | 50 − 30 = **20,00 €** |
| Margen en Neto | 41,32 − 24,79 = **16,53 €** |
| Posición IVA (repercutido − soportado) | 8,68 − 5,21 = **3,47 €** |

Si veis una diferencia de 0,01 € en las bases, puede ser redondeo normal. Lo importante es que los **totales brutos** cuadren exactamente.

### 5.4 Ejercicio guiado 1 — Todo pagado

> Si ya hicisteis las **misiones prácticas del §5** (C2–C6 del bloque de Contabilidad), este bloque y los **§5.5–5.6** son **opcionales** (repiten ideas con otros importes). Si entráis primero solo por la teoría de esta sección, haced **5.4 → 5.5 → 5.6** en orden.

**Objetivo:** ver cómo suben los KPI cuando los movimientos están cerrados como "Pagado".

1. En **Estadísticas**, anotad los valores actuales de Ingresos, Gastos, Margen e Impuestos (con filtros Global + Flujo de Caja Real + Bruto).
2. En **Contabilidad → Ingresos**: cread un ingreso de **50 € con IVA 21 %**, estado **Pagado**, fecha de hoy.
3. En **Contabilidad → Gastos**: cread un gasto de **30 € con IVA 21 %**, estado **Pagado**, fecha de hoy.
4. Volved a **Estadísticas** con los mismos filtros.

Lo que debería haber cambiado respecto a los valores anotados:

- **Ingresos** → +50,00 € (el total bruto, no la base).
- **Gastos** → +30,00 €.
- **Margen** → +20,00 €.
- **Impuestos** → +3,47 €.

5. Cambiad a **Neto**. Los incrementos deben ser: Ingresos +41,32 €, Gastos +24,79 €, Margen +16,53 €. La tarjeta de impuestos debe mostrar el mismo valor que en Bruto (el IVA no cambia, solo cambia cómo se muestran los ingresos y gastos).

6. Cambiad a **Proyección Contable**. Como todo está Pagado, los totales no deben cambiar respecto al modo "solo pagados".

### 5.5 Ejercicio guiado 2 — Ingreso pendiente

**Objetivo:** entender la diferencia entre "dinero en el banco" y "dinero que esperamos cobrar".

1. Cread **otro ingreso de 50 €**, IVA 21 %, pero esta vez con estado **Pendiente**.
2. En Estadísticas:

| Modo | ¿Sube el ingreso pendiente? |
|------|-----------------------------|
| **Flujo de Caja Real** | **No.** Solo cuenta lo Pagado. |
| **Proyección Contable** | **Sí.** Cuenta también los pendientes. |

Esto es clave para entender por qué "el club tiene cuotas emitidas" no significa que ya tenga ese dinero disponible.

### 5.6 Ejercicio guiado 3 — Informe PDF

1. En Contabilidad, pulsad **Generar Informe**. Elegid como fecha de inicio el primer día del mes actual y como fecha de fin el último día del mes.
2. Descargad el PDF.

Comprobad en el PDF:

- Los **50 € cobrados** y los **30 € pagados** del Ejercicio 1 aparecen en la sección de flujo de caja.
- El **segundo ingreso de 50 € pendiente** del Ejercicio 2 **no** aparece en la parte de "cobrado", aunque puede aparecer en apartados de pendientes.
- En la sección de IVA: el repercutido incluye ~8,68 € por cada ingreso de 50 €; el soportado incluye ~5,21 € por el gasto de 30 €.

Si los movimientos de prueba no aparecen en el PDF, comprobad que el rango de fechas cubre la fecha exacta que pusisteis al crear los movimientos.

### 5.7 Lista de comprobación — Contabilidad

| # | Prueba | Qué debe pasar |
|---|--------|----------------|
| 1 | Crear ingreso con usuario del club | Aparece en tabla con nombre correcto. |
| 2 | Marcar como pagado | Badge Pagado; Estadísticas lo recoge en modo Flujo Real. |
| 3 | Pago parcial | Estado Parcial con saldo restante visible. |
| 4 | Eliminar movimiento | Desaparece y los totales se recalculan. |
| 5 | Generar cuotas desde plantilla | Nuevas líneas con concepto e importe correctos. |
| 6 | Generar el mismo período dos veces | La app avisa de duplicado sin crear líneas repetidas. |

### 5.8 Más prácticas en Contabilidad — lectura y ejercicios ampliados

#### Lectura (qué ideas vais a comprobar)

- **Cuota con IVA:** una plantilla mensual con IVA genera líneas en **Ingresos** con **base** y **cuota de IVA** calculadas igual que un alta manual (véase **§5.3**: el importe que escribís es el **total con IVA incluido**).
- **Nombre solo en texto:** podéis cobrar a alguien que **no** tiene usuario en el club escribiendo el nombre a mano; debe verse tal cual en la tabla y sumar en **Flujo de Caja Real** si está **Pagado**.
- **Importación Excel (datos económicos):** un archivo sin filas útiles o con datos rotos debe dar **mensaje claro** (arriba en pantalla o dentro del cuadro gris del modal), **no** dejar el navegador colgado sin texto.
- **Categoría nueva y gráfico circular:** un gasto con categoría recién creada debe crear un **trozo nuevo** en el gráfico circular de **gastos** en Estadísticas (tras guardar y, si hace falta, **recargar** la página de Estadísticas).
- **Justificantes:** un gasto puede llevar archivo o no; en ambos casos debe guardarse y, si hay archivo, debe poder **verse o descargarse**.
- **Fecha antigua:** un cobro con fecha de hace meses aparece en vista **Global**, pero puede **no entrar** en el filtro **Últimos 1 mes** si ese mes corto no incluye ese día.
- **Borrar categoría usada:** el sistema suele **impedir** borrar una categoría que sigue en movimientos, con **explicación**; si permite borrar y deja datos raros, es grave — documentadlo.

#### Antes de tanteáis — cómo seguir esta lista sin perderos

1. **Pre-requisitos:** **§4** (al menos una cuenta) + misión **C1** (categorías) + idealmente **C2** y **C3** (ya tenéis un ingreso y un gasto de ejemplo en el club).
2. Leed **§5.3** una vez: es la base para entender los euros que veis en tabla, PDF e IVA.
3. Estos ejercicios piden **varias altas distintas** (no una sola fila y fin): id **anotando en papel** cada cosa que creéis (nombre del concepto + importe) para poder contrastar después con Estadísticas y con el PDF.
4. Si un paso dice “esperad a que aparezca el cargo” y en vuestro club **no ocurre nada al cabo de unos minutos**, **no asumáis fallo vuestro**: preguntad cómo se disparan las cuotas en ese entorno y escribid **N/A coordinador** en la entrega.

#### Ejercicio 1 — Plantilla de cuota con IVA 21 % y cruce con PDF

**Objetivo:** verificar que un cargo nacido de **Configurar cuotas** tiene el mismo desglose (**base**, **IVA**, **total**) que la teoría del **§5.3** y que el **informe PDF** del mes coincide.

**Pasos:**

1. **Contabilidad →** sección de cuotas recurrentes **→ Nueva cuota** (o equivalente). Tipo **Ingreso**, **50,00 €**, IVA **21 %**, frecuencia **Mensual**, concepto por ejemplo **Cuota beta mensual IVA**, **día del mes** elegid uno claro (ej. **15**), categoría que permita ingresos (p. ej. **Cuotas formación**), **fecha inicio** antes de hoy y **fecha fin** después de hoy (según el texto de ayuda de la propia pantalla sobre la fecha final).
2. Guardad. **Refrescad** la página de **Ingresos** varias veces o esperad lo que indique quien coordina las pruebas. Buscad una fila **nueva** cuyo concepto sea el de la plantilla.
3. Abrís esa fila (edición o detalle): anotad **total**, **base** y **IVA** que muestra la interfaz.
4. **Generar Informe** con rango desde el **primer día del mes natural** de la **fecha de ese cargo** hasta el **último día de ese mismo mes**. En el PDF, localizad la línea en la zona de movimientos / flujo que corresponda.

**Qué anotar:** ¿Los tres números (base, IVA, total) cuadran entre pantalla, §5.3 y PDF? Si **no aparece ningún ingreso** generado, indicarlo como **N/A** y la causa (tiempo, permisos, proceso manual).

#### Ejercicio 2 — Ingreso solo con nombre escrito a mano (sin usuario del club)

**Objetivo:** comprobar cobros a **terceros** que no están dados de alta como personas en Usuarios.

**Pasos:**

1. **Nuevo ingreso.** En el campo de nombre: **no** elijáis nadie del autocompletado; escribid texto literal **Patrocinador Calle Demo S.L.** Importe **75,00 €**, IVA **0 %**, estado **Pagado**, fecha **hoy**, cuenta y método válidos.
2. Confirmad en la **tabla de Ingresos** que la columna **Nombre** muestra **exactamente** ese texto.
3. **Estadísticas:** modo **Global**, **Flujo de Caja Real**, **Bruto**. Comparad el total de **Ingresos** con el valor que teníais **justo antes** de crear esta línea: debe haber subido **75,00 €**.

**Qué anotar:** captura o transcripción del nombre en tabla; si el incremento no es 75 €, describid el fallo.

#### Ejercicio 3 — Import económico con Excel sin filas de datos

**Objetivo:** ver cómo reacciona la app cuando el Excel es “válido” pero **no trae movimientos**.

**Pasos:**

1. **Importar datos económicos → Descargar plantilla.**
2. En la hoja **Movimientos**, **borrad todas las filas de datos** y dejad **solo la cabecera** (la primera fila con nombres de columnas).
3. Guardad y **Subir archivo** desde el modal.

**Qué anotar:** ¿Os llega un **mensaje emergente** arriba a la derecha? ¿O solo texto dentro del propio cuadro del modal? Copiad el **mensaje literal**. ¿Entendéis sin ayuda **por qué** no se ha importado nada?

#### Ejercicio 4 — Import económico con datos incoherentes

**Objetivo:** comprobar si los errores son **por fila** y **comprensibles**.

**Pasos:**

1. Duplicad la plantilla en un archivo aparte (ej. `prueba_mala.xlsx`).
2. En **Movimientos**, añadid una fila con **fecha imposible** (ej. día 31 de febrero) **o** cantidad vacía **o** datos desplazados una columna respecto a las cabeceras.
3. Intentad importar.

**Qué anotar:** ¿Lista de errores con número de fila? ¿Un mensaje genérico? ¿La pestaña del navegador se queda “pensando” sin fin?

#### Ejercicio 5 — Nueva categoría de gasto y gráfico circular en Estadísticas

**Objetivo:** la clasificación nueva debe verse como **porción nueva** del gráfico de gastos.

**Pasos:**

1. **Gestionar categorías económicas →** alta **Gasto beta gráfico** (solo gasto o ambas), **color** bien distinto del resto.
2. **Nuevo gasto:** importe **40,00 €**, IVA **0 %**, **Pagado**, categoría **Gasto beta gráfico**, cuenta válida, nombre de proveedor ficticio.
3. Id a **Estadísticas** y mirad el **gráfico circular de gastos por categoría**. Si no cambia, **recargad la página** con F5.

**Qué anotar:** ¿Aparece la nueva etiqueta y el color esperado?

#### Ejercicio 6 — Dos gastos: uno con justificante y otro sin él

**Objetivo:** el archivo adjunto es **opcional** y no debe romper el alta.

**Pasos:**

1. **Gasto con archivo:** cualquier importe pequeño y adjuntad un **PDF o imagen** de prueba en **Justificante**.
2. **Gasto sin archivo:** mismo tipo de datos pero **sin** elegir fichero.
3. En la tabla, para el que tiene archivo: pulsad el enlace o icono de justificante y comprobad si **abre o descarga**.

**Qué anotar:** ¿Los dos gastos figuran en lista? ¿El archivo del primero se obtiene bien?

#### Ejercicio 7 — Ingreso con fecha de hace tres meses vs filtros de Estadísticas

**Objetivo:** entender la diferencia entre **toda la historia** y **solo el último mes**.

**Pasos:**

1. **Nuevo ingreso Pagado**, **22,00 €**, IVA **0 %**, fecha **el mismo día del mes pero tres meses atrás** en el calendario (ej. si hoy es mayo, usad febrero del mismo año).
2. **Estadísticas → Global + Flujo de Caja Real + Bruto:** los ingresos totales deben **incluir** esos **22 €** respecto al instante anterior al alta.
3. Cambiad el filtro temporal a **Últimos 1 mes** (si ese mes corto **no** incluye la fecha del paso 1): esos **22 €** **no** deben contarse ahí.

**Qué anotar:** números antes/después o capturas; si la app se comporta distinto, describidlo.

#### Ejercicio 8 — Intentar borrar una categoría que aún usa un movimiento

**Objetivo:** comprobar protección de datos vinculados.

**Pasos:**

1. Cread categoría **Temporal uso categoría demo** aplicable a **gasto**.
2. Cread un gasto cualquiera usando esa categoría y guardad.
3. Desde **Gestionar categorías económicas**, intentad **eliminar** **Temporal uso categoría demo**.

**Qué anotar:** ¿Mensaje que impide borrar con motivo claro? ¿O borra y deja la fila del gasto sin sentido?

#### Relación con las misiones C8–C15

Justo **debajo** de la misión **C7**, esta guía incluye **misiones C8–C15** con **valores guía** para los mismos tipos de caso (cuota, nombre texto, import vacío/erróneo, categoría+gráfico, justificantes, fecha antigua, borrar categoría). Podéis hacer **primero §5.8** a vuestro ritmo y luego **C8–C15** para dejar constancia fija en la entrega, o al revés.

**Feedback documentación (beta):** ¿Algún paso de **§5.8** os obligó a saltar a **§5.12** sin saber por qué? ¿Qué frase faltaba?

### 5.9 Importación guiada de **datos económicos** (Excel)

Desde **Contabilidad**, botón **Importar datos económicos**. Se abre el modal **Importación de datos económicos**.

**Qué debéis saber antes de empezar**

- El Excel tiene sentido con **dos hojas** reconocidas por el programa: **Cuentas** y **Movimientos** (también acepta nombres parecidos; la plantilla trae esos nombres).
- Hay una tercera hoja **Instrucciones** en la plantilla: leedla una vez; resume columnas y reglas.
- **Importante:** el fichero **no** se guarda tal cual en una carpeta pública: el **navegador lee** el Excel en vuestro ordenador, comprueba reglas y envía al servidor solo **los datos ya interpretados** (filas de movimientos y cuentas). Sirve para tranquilizar al club sobre qué viaja por red.
- Cada fila de movimiento necesita **cantidad > 0**, **fecha válida** y **cuenta**: o bien el **nombre** de una cuenta que ya exista en el club, o el **ID numérico** de cuenta, o una fila equivalente en la hoja Cuentas que vaya a crearse en la misma importación.
- **Cantidad** en el Excel = **bruto** (igual que en los formularios). Columnas opcionales: **Porcentaje_impuesto** (IVA %), **Porcentaje_descuento**, **Importe_antes_descuento** (PVP).
- **Estado** en Excel: si ponéis **pagado** / **cobrado**, el sistema tratará el movimiento como cobrado; **vacío** u otro valor → **pendiente** (salvo impago/remesa según texto; ver código de plantilla).

**Opciones del modal (marcare/desmarcar según el caso)**

| Casilla | Efecto |
|---------|--------|
| **Aplicar saldo inicial del Excel en cuentas nuevas** | Si la hoja **Cuentas** crea una cuenta nueva, se guarda el **Saldo_inicial** de la fila. Desmarcadla si esos movimientos ya “incluyen” ese saldo para no **duplicar** dinero en el balance. |
| **No crear cuentas duplicadas (mismo nombre)** | Evita crear otra cuenta si ya existe una con el mismo nombre en el club. |

**Ejercicio guiado A — Primera importación mínima (recomendado en entorno de prueba)**

1. En **Herramientas → General**, anotad el nombre **exacto** de una cuenta bancaria del club (ej. “Cuenta principal”). Si no hay ninguna, cread una ficticia.
2. En **Contabilidad**, abrid **Importar datos económicos** → **Descargar plantilla**.
3. Abrir el `.xlsx`. En **Movimientos**, **borrad las filas de ejemplo** o dejad solo una fila de prueba para no mezclar datos raros.
4. Añadid **una fila** (podéis copiar cabeceras de la plantilla):
   - `ingreso`, cantidad **25,50**, concepto “Import prueba Excel demo”, **fecha de hoy** en formato `AAAA-MM-DD`, en **Cuenta** el **mismo texto** que el paso 1, método `transferencia`, observación libre, estado **pagado**, IVA **0** o vacío.
5. **No** pongáis filas en **Cuentas** si la cuenta ya existe (así evitáis duplicados).
6. Guardad el Excel, volved al modal, **arrastrad el archivo** o seleccionadlo → **Subir archivo**.

**Resultado esperado**

- Mensaje de **éxito** tipo “Importación completada. Movimientos creados: **1**.” (o el número que sea).
- En la tabla **Ingresos** debe aparecer la nueva línea al refrescar (la pantalla suele refrescar sola).
- En **Estadísticas** (Global, Flujo real, Bruto), los **Ingresos** deben haber subido **25,50 €** respecto al valor anterior si el movimiento quedó **pagado** y la fecha cae en el periodo que estáis mirando.

**Ejercicio guiado B — Error controlado**

1. En el Excel, poned en **Cuenta** un nombre que **no exista** y **no** esté en la hoja Cuentas.
2. Intentad importar.

**Esperado:** error claro del servidor o validación (no “pantalla en blanco”). Documentad el texto exacto.

**Ejercicio guiado C — Cuenta nueva + saldo**

1. En la hoja **Cuentas**, una fila: nombre “Banco prueba Excel demo”, IBAN vacío o de prueba, tipo `banco`, saldo inicial **1000**.
2. En **Movimientos**, un **gasto** de **50** con esa misma cuenta por nombre, fecha hoy, **pagado**.
3. Importad con **Aplicar saldo inicial** marcado.

**Esperado:** cuenta creada (o enlazada), movimiento visible en **Gastos**, y en **Herramientas** la cuenta muestra coherencia con vuestro criterio de saldo (si algo “dobla”, probad de nuevo con la casilla de saldo **desmarcada** y anotad la diferencia).

### 5.10 Después de importar: cadena de comprobación (Estadísticas + Informe + Auditoría)

Solo tiene sentido **después** de una importación que el servidor confirme como exitosa y con movimientos creados. Entonces haced esta checklist **en orden**:

1. **Contabilidad:** ¿el número de filas nuevas coincide con `movimientos_creados` del mensaje?
2. **Estadísticas:** ¿suben Ingresos/Gastos en **Bruto** con **Flujo real** si los estados eran **pagado**?
3. **Estadísticas:** tarjetas **Cobros últimos 30 días** — si importasteis solo **ingresos/cuotas** con fecha hoy, ¿cambia el **número** de recibos en cada estado y por tanto los %?
4. **Generar informe PDF** con rango que incluya las **fechas** de las filas importadas: ¿aparecen en **Flujo de caja** los importes **cobrados/pagados**?
5. **Auditoría:** ¿hay entradas recientes de tipo creación o configuración relacionadas con la importación (según cómo registre el backend)?

Si **2** falla pero **1** está bien, revisad **estado** y **fecha**. Si **4** falla, casi siempre es el **rango de fechas** del PDF.

### 5.11 Mapa rápido según el código de la pantalla (`Contabilidad.jsx`)

Sirve para que sepáis **qué existe de verdad** en el front y no inventéis flujos imposibles.

| Área | Detalle para testers |
|------|----------------------|
| **Listados** | Los **ingresos** combinan en una sola vista movimientos tipo `ingreso` y tipo `cuota` (cuotas recurrentes aparecen aquí). Los **gastos** son otro fetch aparte. |
| **Ordenación** | Las filas se ordenan por fecha relevante (prioridad aprox.: fecha de pago, fecha, fechas de cuota, creación). Lo último en tiempo suele arriba. |
| **Columnas visibles** | En cabecera, menú **▾**: máximo **5 columnas** visibles por tabla; la sexta sustituye a una. Podéis dejar solo **Estado** + **IVA / Neto** + **Nombre** para pruebas de legibilidad. |
| **Columna IVA / Neto** | Muestra tasa y base; con **0 %** sigue mostrando base (ej. `0% · 25,50 €`). Movimientos antiguos sin categoría pueden mostrar **sector** legado (Material, Instalaciones, etc.). |
| **Filtros Ingresos** | Panel **Filtrar**: texto libre en nombre, estado (pendiente, enviado al banco, procesando, pagado, impago), método, cuenta, categoría, rango de fechas. Hay un campo etiquetado **«Fila (#)»** en el front (uso interno/legacy): probad si filtra por lo que esperáis o documentad comportamiento confuso. |
| **Filtros Gastos** | Similar: nombre, método, observación, estado, cuenta, categoría, fechas. Los filtros **no** suelen aplicarse hasta que confirmáis desde el panel (comprobad si hay que cerrar o pulsar «Aplicar» según vuestra build). |
| **Edición de ingreso** | **Editar** con usuario: el campo nombre puede usar **autocomplete** (`/api/usuarios/buscar_usuarios/`). En tabla, el nombre visual puede **quitarse un sufijo** tipo `(rol)` al final — no es bug si el detalle del modal muestra más texto. |
| **Historial de pagos** | Ingresos pueden abrir un **drawer** de historial de pagos (`PaymentHistoryDrawer`) cuando aplique — útil para **Parcial** o varios cobros. Documentad si no abre o si el importe no cuadra con «Pagado». |
| **Import económico** | Opciones típicas: **aplicar saldo inicial** en cuentas nuevas; **no duplicar cuentas** por nombre. Tras éxito, el navegador puede guardar **marca de tiempo** de última importación (solo local). |
| **Stripe / SEPA administración** | Al **final** de la página hay secciones **Stripe** y **SEPA** (`StripePagosPanel`, `SepaAdminPanel`). Son configuraciones y listados distintos del alta manual de movimientos. Documentad si cada bloque **carga**, muestra **estado vacío con texto útil** o devuelve **error** (p. ej. sin integración configurada). |

### 5.12 Batería ampliada de casos en Contabilidad (muchas variantes)

Haced **al menos** los bloques **A–E** además de las **misiones del §5** (o sustituid solapes marcados como opcional). Marcad en vuestra entrega **pasos → esperado → obtenido**.

#### A — Fiscalidad (IVA y descuentos)

| ID | Caso | Pasos resumidos | Qué comprobar |
|----|------|-----------------|---------------|
| A1 | Ingreso **IVA 4 %** | Bruto 104 €, 4 % | Base ~100 € en columna fiscal / coherencia en Estadísticas (Neto). |
| A2 | Ingreso **IVA 10 %** | Bruto 110 €, 10 % | Base ~100 €. |
| A3 | Ingreso **IVA 0 %** | Cualquier importe | Columna **IVA / Neto** muestra `0%` y base = bruto. |
| A4 | Gasto **IVA 21 %** pequeño | 12,10 € | Base ~10 €; sumad varios gastos y contrastad **Impuestos** global vs repercutido − soportado. |
| A5 | **IVA personalizado** | Si el formulario ofrece % manual (p. ej. 7,5 %) | ¿Guarda? ¿La tabla muestra el % correcto? ¿PDF e Informe coherentes? |
| A6 | **Descuento / PVP** | Rellenad **importe antes de descuento** y **% descuento** (o solo uno) según UI | El **monto** final debe ser el cobrado real; la columna fiscal debe cuadrar con ese monto. Si el backend rechaza combinaciones raras, capturad el mensaje. |

#### B — Estados y flujo de caja

| ID | Caso | Pasos | Qué comprobar |
|----|------|-------|---------------|
| B1 | **Gasto pendiente** | 40 € IVA 0 %, pendiente | **No** suma en Estadísticas **Flujo real**; **sí** o según reglas en **Proyección contable**. |
| B2 | **Ingreso → Pendiente → Pagado** | Crear pendiente, luego marcar pagado (desde fila o flujo que use `markMovimientoPagado`) | Salto de KPI correcto al pasar a pagado; fecha coherente en PDF. |
| B3 | **Impago** | Ingreso en impago | Visible en filtros; en **Cobros — últimos 30 días** (Estadísticas) cuenta como recibo impago; **no** como cobrado en PDF. |
| B4 | **Parcial** | Si vuestro entorno permite registrar cobro parcial | Estado **Parcial**, columna **Pagado** menor que **Monto**; drawer de historial si existe. |
| B5 | **Enviado al banco** | Tras **remesa SEPA** simulada (solo si tenéis cuotas/ingresos válidos e IBANs de prueba) | Estado cambia; **mensaje emergente** sobre el XML u **error legible** en pantalla si faltan datos. |

#### C — Cuenta, método y categoría

| ID | Caso | Qué comprobar |
|----|------|---------------|
| C1 | Mismo importe en **dos cuentas distintas** | Filtro por cuenta muestra solo la mitad esperada; Estadísticas no debe «mezclar» sin cambiar filtro. |
| C2 | **Todos los métodos de pago** del desplegable (Bizum, transferencia, efectivo, tarjeta, Apple/Google Pay, domiciliación) | Al menos creación **sin error** y etiqueta correcta en tabla/export Excel. |
| C3 | **Cambiar solo categoría** en edición | Gráfico circular de ingresos/gastos en Estadísticas se actualiza tras refrescar o navegar. |
| C4 | **Sin categoría** en ingreso/gasto | ¿Permite guardar? Si sí, ¿aparece «—» o sector legado en viejas filas? |

#### D — Tabla, selección y operaciones masivas

| ID | Caso | Qué comprobar |
|----|------|---------------|
| D1 | Seleccionar **dos ingresos** + **Eliminar** | Modal de confirmación; tras OK, ambos IDs desaparecen y KPI bajan. |
| D2 | **Editar** selección múltiple | ¿Permite edición en bloque o solo una fila? Documentad el comportamiento real. |
| D3 | **Exportar Excel** tras filtros | ¿El Excel respeta filtros o exporta todo? Debe ser **consistente** en vuestra versión (no asumáis). |
| D4 | Toggle **Bruto/Neto** ingresos vs gastos | Cambiad uno y no el otro: ¿solo cambia la sección esperada? |

#### E — Import económico (matriz de errores)

| ID | Caso | Qué comprobar |
|----|------|---------------|
| E1 | **Dos filas**: una ingreso pagado, una gasto pagado, misma fecha | Mensaje `movimientos_creados: 2`; ambas tablas actualizadas. |
| E2 | **IVA en Excel** (`Porcentaje_impuesto` 21) + cantidad bruta | Misma lógica que formulario manual. |
| E3 | **Descuento en Excel** (`Porcentaje_descuento`, `Importe_antes_descuento`) | Coherencia con §A6. |
| E4 | Archivo **vacío** / solo cabeceras | Mensaje claro, sin pantalla rota. |
| E5 | **Cuenta inventada** sin hoja Cuentas | Error legible (ya en §5.9 B). |
| E6 | **Duplicar import** mismo fichero dos veces | ¿Duplica movimientos o el backend deduplica? Documentad riesgo para el club. |

#### F — Informe PDF e hipótesis de fecha

| ID | Caso | Qué comprobar |
|----|------|---------------|
| F1 | Movimiento con **fecha de ayer** vs rango «este mes» | Incluido solo si el rango cubre ese día. |
| F2 | **Último día del mes** como `fecha_fin` | No se pierde el movimiento del día 31 (regresión frecuente). |

#### G — Integraciones al pie de página

| ID | Caso | Qué comprobar |
|----|------|---------------|
| G1 | **StripePagosPanel** | ¿Lista intents/pagos?, ¿empty state útil?, ¿error si Stripe no configurado? |
| G2 | **SepaAdminPanel** | Mandatos, estado del club, mensajes si falta credencial (sin datos reales reales). |

#### H — Notificaciones y remesas (solo con permiso de quien coordine las pruebas)

| ID | Caso | Qué comprobar |
|----|------|---------------|
| H1 | **Avisar deudores** | Modal «¿Seguro…?» → **mensaje emergente** con **notificados**, **omitidos**, **periodo**. ¿Spam si pulsáis dos veces seguidas? |
| H2 | **Remesa** sin selección | Botón deshabilitado o mensaje claro. |
| H3 | Remesa con fila **procesando pasarela** | Debe **excluir** la fila y avisar con **texto en pantalla** (tooltip o mensaje emergente), según versión. |

---

### Misiones — Contabilidad (hacedlas en orden cuando lleguéis aquí tras leer todo el §5)

**Orden sugerido:** **C1 → C7** forma la secuencia base que encadena con **§6 Estadísticas**. Después, **§5.8** (explicaciones paso a paso) y/o **C8 → C15** añaden **más tipos** de ingresos, gastos, cuotas e importaciones sin limitaros a una sola fila de ejemplo.

#### Misión C1 — Categorías económicas

**Dependencias:** ninguna dentro de contabilidad (las cuentas ya están creadas en **§4 Herramientas**).

**Dónde:** **Contabilidad → Gestionar categorías económicas** (desde la barra superior de la página).

1. **Cuotas formación** — aplica a **ingreso** o **ambas**.
2. **Material formación** — aplica a **gasto** o **ambas**.

**Comprobación:** visibles en **Nuevo ingreso** / **Nuevo gasto**.

#### Misión C2 — Ingreso con IVA (pagado)

| Campo | Valor |
|-------|--------|
| Nombre | Texto **Donante Club Prueba S.L.** (sin usuario) |
| Importe total (bruto) | **121,00** |
| IVA | **21 %** |
| Estado | **Pagado** |
| Cuenta | **Banco Prueba BETA** |
| Categoría | **Cuotas formación** |
| Fecha | **Hoy** |
| Método | **Transferencia** |

**Comprobación:** desglose ~100 € base + ~21 € IVA.

#### Misión C3 — Gasto con IVA (pagado)

| Campo | Valor |
|-------|--------|
| Nombre | **Proveedor Equipaciones Demo** |
| Importe | **30,00** |
| IVA | **21 %** |
| Método | **Tarjeta** |
| Categoría | **Material formación** |
| Fecha | **Hoy** |
| Cuenta | **Caja Prueba ALPHA** |
| Estado | **Pagado** |

**Acumulado teórico (solo C2+C3, Global / Flujo real / Bruto):** respecto al club antes de estas misiones, **Ingresos +121,00 €**, **Gastos +30,00 €**, **Margen +91,00 €**. La tarjeta de **Impuestos** sube aprox. **+15,79 €**; si la app muestra un céntimo distinto por redondeo, **usad el valor de pantalla**.

#### Misión C4 — Ingreso pendiente (50 €)

| Campo | Valor |
|-------|--------|
| Nombre | **Socio pendiente Demo** |
| Importe | **50,00** |
| IVA | **21 %** |
| Estado | **Pendiente** |
| Cuenta | **Banco Prueba BETA** |
| Categoría | **Cuotas formación** |
| Fecha | **Hoy** |
| Método | **Bizum** |

*(La verificación en Estadísticas la haréis en las misiones del §6, cuando sepáis qué es Flujo real vs proyección.)*

#### Misión C5 — Import económico (25,50 €)

**Dónde:** **Contabilidad → Importar datos económicos**.

1. Descargad plantilla. En **Movimientos**, una fila: `ingreso`, **25,50**, concepto **Import formación C5**, fecha **hoy**, cuenta **Banco Prueba BETA** (texto idéntico al nombre creado en **§4**), método `transferencia`, estado `pagado`, sin IVA.
2. Sin hoja **Cuentas** si la cuenta ya existe.
3. **Subir archivo.**

**Comprobación:** tras completar también las misiones del §6 sobre KPI, la diferencia de ingresos encajará con **+25,50 €** en Flujo real / Bruto respecto al punto anterior (además de lo acumulado en C2 y en la misión de barras del §6).

#### Misión C6 — Informe PDF del mes en curso

**Dónde:** **Contabilidad → Generar Informe**.

Rango: **día 1 del mes actual** → **último día del mes actual**. Generad **PDF**.

**Comprobación:** en **flujo de caja** aparecen cobros **pagados** con fecha en ese mes según lo que hayáis creado (ingreso pagado de C2, gasto pagado de C3, etc.). Cruzad un **ID** con Contabilidad.

#### Misión C7 — Vencidos (Contabilidad + Herramientas)

**Dependencias:** habéis leído **§4** (tarjeta de vencidos en Herramientas) y tenéis movimientos en Contabilidad.

1. **Nuevo ingreso:** **Vencido Demo**, **20,00 €**, IVA 0 %, **Pendiente**, cuenta **Banco Prueba BETA**, **fecha de pago hace 20 días**.
2. **Herramientas → General → Ver Vencidos**, fecha de corte **hoy** → debe listarse.
3. Export **Excel** → **Limpiar**.
4. Pasar el movimiento a **Pagado** → **Ver Vencidos** de nuevo: no debe figurar como pendiente vencido.

#### Misión C8 — Segundo ingreso con nombre solo en texto

**Dependencias:** **C1** (y cuentas del §4).

**Objetivo:** mismo caso que **§5.8 ejercicio 2**, con valores fijos para comparar entre testers.

1. **Nuevo ingreso:** escribid manualmente el nombre **Patrocinador Prueba ERP** (sin elegir usuario del club). **75,00 €**, IVA **0 %**, **Pagado**, fecha **hoy**, cuenta **Banco Prueba BETA**, método **Transferencia**, categoría **Cuotas formación** (u otra válida para ingreso).

**Comprobación:** nombre literal en tabla; en **Estadísticas** (Global, Flujo real, Bruto) los ingresos suben **75,00 €** respecto al momento **justo antes** del alta.

#### Misión C9 — Cuota mensual 50 € con IVA 21 % + PDF

**Dependencias:** **C1**.

**Objetivo:** mismo caso que **§5.8 ejercicio 1**, con concepto fijo.

1. **Nueva cuota** tipo **Ingreso**, **50,00 €**, IVA **21 %**, frecuencia **Mensual**, concepto **Cuota misión C9**, **día del mes 10**, categoría de ingreso, fechas de vigencia que incluyan **hoy**.
2. Cuando aparezcan cargos en **Ingresos** (refresco / tiempo / coordinador), abrid la fila correspondiente y anotad **total**, **base**, **IVA**.
3. **Generar Informe** PDF con rango que cubra el **mes natural** de la fecha de ese cargo.

**Comprobación:** coherencia con **§5.3** y con el PDF; si no se genera ningún movimiento, **N/A** + motivo.

#### Misión C10 — Import económico: Excel solo cabeceras

**Dependencias:** saber abrir **Importar datos económicos**.

1. Plantilla descargada: hoja **Movimientos** sin ninguna fila de datos (solo la primera fila de columnas).
2. Subid el archivo.

**Comprobación:** mensaje comprensible (**mensaje emergente** o texto en el modal); copiad el texto en la entrega.

#### Misión C11 — Import económico: fila incorrecta

1. En **Movimientos**, una fila con **fecha inválida** (ej. `2026-02-31`) o **cuenta** que no exista y no esté en la hoja **Cuentas**.

**Comprobación:** error **concreto** o lista de filas; el navegador **no** debe quedarse cargando sin respuesta.

#### Misión C12 — Categoría nueva + gasto + gráfico circular

1. Categoría **Donut misión C12** (gasto o ambas), **color** llamativo.
2. **Nuevo gasto:** **35,00 €**, IVA **0 %**, **Pagado**, categoría **Donut misión C12**, cuenta válida.

**Comprobación:** en **Estadísticas**, el **gráfico circular de gastos** muestra la nueva categoría (quizá tras **F5**).

#### Misión C13 — Gastos con y sin justificante

1. **Gasto A:** importe pequeño **con** archivo en **Justificante** (PDF o imagen de prueba).
2. **Gasto B:** mismo esquema **sin** archivo.

**Comprobación:** ambos en tabla; el justificante del **A** se abre o descarga correctamente.

#### Misión C14 — Ingreso antiguo y filtro “Últimos 1 mes”

1. **Ingreso Pagado** **22,00 €**, IVA **0 %**, fecha **tres meses antes de hoy** (mismo día del mes si es posible).
2. **Estadísticas:** contrastad **Global** vs **Últimos 1 mes** como en **§5.8 ejercicio 7**.

**Comprobación:** los **22 €** cuentan en Global en Flujo real y **no** en “Últimos 1 mes” si ese recorte no incluye la fecha antigua.

#### Misión C15 — Eliminar categoría que sigue en uso

1. Categoría **Tmp categoría C15** (gasto).
2. **Nuevo gasto** usando **Tmp categoría C15**.
3. Intentad **borrar** la categoría **Tmp categoría C15**.

**Comprobación:** bloqueo con **mensaje claro** o comportamiento equivalente aceptable documentado.

#### Más variantes

Para **IVA 4 % / 10 %**, descuentos, remesas, Stripe, matrices de import, etc., seguid la batería **§5.12** y el mapa **§5.11**. Las misiones **C8–C15** y **§5.8** cubren el “núcleo” de variantes típicas (cuotas, externos, import, categorías, justificantes, fechas, borrados).

**Feedback documentación (beta):** ¿Qué parte del **§5** o de las misiones **C1–C15** no habéis entendido o os ha obligado a abrir soporte / código?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---
## 6. Estadísticas — el resumen financiero visual

### 6.1 Qué es esta pantalla

Es el panel de control financiero del club: cifras grandes, tarjetas KPI (indicadores clave) y gráficas. No sustituye al detalle línea a línea de Contabilidad, pero debe mostrar la misma realidad si usáis los mismos criterios de fechas y filtros.

### 6.2 Los filtros del resumen financiero

En la parte superior encontraréis estos controles:

| Control | Qué hace |
|---------|----------|
| **Global** | Muestra toda la historia contable disponible. |
| **Temporada** | Acota al período deportivo activo del club. |
| **Últimos N meses** | Permite ver solo los últimos 1, 2, 3… hasta 12 meses. |
| **Bruto** | Los importes incluyen IVA (precio final). |
| **Neto** | Los importes son la base imponible sin IVA. |
| **✓ Flujo de Caja Real** | Solo cuenta movimientos en estado **Pagado** — el dinero que ya está en el banco. Subtítulo: *(Solo pagados)*. |
| **~ Proyección Contable** | Cuenta pagados + pendientes — lo que el club espera cobrar aunque todavía no lo haya ingresado. Subtítulo: *(Incluye pendientes)*. |

### 6.3 Las tarjetas KPI

| Tarjeta | Qué representa |
|---------|----------------|
| **Ingresos** | Suma de entradas en el rango y modo elegidos. |
| **Gastos** | Suma de salidas. |
| **Margen** | Ingresos menos gastos. |
| **Balance actual / Flujo neto** | Saldo disponible según el modo. Leed el subtexto de la tarjeta: aclara si incluye saldo inicial del banco o solo movimientos del rango. |
| **Impuestos acumulados** | Previsión de posición de IVA del club (IVA cobrado menos IVA pagado). |

También encontraréis:

- **Gráfica "Ingresos vs Gastos"** con líneas de Ingresos, Gastos y una línea de Disponible.
- **Cobros últimos/próximos 30 días:** barras con porcentaje de Pagados, Pendientes e Impagos.
- **Gráficas de donut:** ingresos y gastos por categoría económica.
- **Proyección financiera IA:** botón "Actualizar predicción" con un badge de saldo previsto. Si no hay datos suficientes, debe aparecer un aviso amarillo en lugar de la gráfica.

#### Cobros — últimos 30 días y próximos 30 días (los porcentajes de la barra)

Esas dos tarjetas **no usan** los mismos filtros que el bloque superior (Global / Temporada / últimos meses). Siempre miran ventanas de fechas fijas respecto a **hoy**:

| Tarjeta | Ventana que cuenta el servidor | Qué miden los % |
|---------|--------------------------------|-----------------|
| **Cobros — últimos 30 días** | Desde hace 30 días hasta **hoy** | Solo movimientos de tipo **ingreso** y **cuota** del club cuya fecha de referencia (pago o alta) cae ahí. |
| **Cobros — próximos 30 días** | Desde el **día 1 del mes en curso** hasta **hoy + 30 días** | Igual: solo **ingreso** y **cuota**. |

Los tres porcentajes (**Pagados**, **Pendientes**, **Impagos**) se calculan sobre el **número de recibos** en esa ventana, no sobre euros:

- Si hay **4** movimientos y **3** están pagados → **Pagados ≈ 75 %** (el backend redondea a dos decimales).
- **No** esperéis que la suma de porcentajes refleje importes: un único recibo impagado de 5 € puede ser el 25 % del conteo aunque sea poco dinero.

**Ejercicio guiado — comprobar que entendéis los %**

1. En **Contabilidad**, cread **tres ingresos de prueba** (o cuotas) con **fecha de hoy** y importes distintos (ej. 10 €, 100 €, 1000 €): uno **Pagado**, uno **Pendiente**, uno **Impago**.
2. Id a **Estadísticas** y mirad **Cobros — últimos 30 días**.
3. **Esperado:** tres filas cuentan en el total; **Pagados ~33,33 %**, **Pendientes ~33,33 %**, **Impagos ~33,33 %** (aunque los importes sean muy desiguales).
4. Cambiad uno de ellos a **Pagado** en Contabilidad y recargad Estadísticas.
5. **Esperado:** **Pagados** sube a **66,67 %** y el estado que hayáis dejado solo una vez baja a **33,33 %**.

*(Si en vuestro club ya hay cientos de recibos reales, los porcentajes no serán tan “limpios”; el ejercicio sirve para entender la **lógica**, no el valor exacto en producción.)*

#### Proyección financiera con IA — aviso importante

Ese bloque usa un **modelo estadístico interno** (no es un chat): aprende de la **serie histórica** de movimientos del club.

- Si os dan un **entorno vacío**, un club **recién creado** o una cuenta con **casi ningún movimiento**, es **normal** que la gráfica esté vacía, el mensaje sea confuso o la predicción no tenga sentido.
- **No os rayéis:** en esas condiciones el fallo no sois vosotros; documentad “sin datos suficientes” o “mensaje X” y seguid con el resto de pruebas.
- Solo tiene valor comparar predicciones cuando ya hay **varios meses** de actividad coherente en Contabilidad.

### 6.4 Prueba básica al entrar por primera vez

Los pasos **3 a 5** son **comprobaciones** sobre el ingreso que creáis en el paso **2**; necesitáis haber anotado antes los KPI del paso **1**.

1. Poned **Global + Flujo de Caja Real + Bruto** y anotad en papel los cuatro números grandes (Ingresos, Gastos, Margen, Impuestos).
2. Id a Contabilidad y cread un ingreso de prueba de **10 € pagado** con fecha de hoy.
3. Volved a Estadísticas con los mismos filtros. ¿Subió "Ingresos" en 10 €?
4. Cambiad a **Proyección Contable**: ¿los pendientes inflan el resultado?
5. Cambiad a **Neto**: ¿las cantidades bajan respecto a Bruto (porque se quita el IVA)?

### 6.5 Lectura y ejercicios extra en Estadísticas

#### Lectura

- **Global vs. últimos N meses:** el texto de las tarjetas cambia entre totales **históricos** y totales **del periodo** seleccionado; los números deben ser distintos si hay movimientos fuera del rango corto.
- **Bruto vs. Neto:** en **Neto**, las series usan **base imponible**; la interfaz suele indicarlo en subtítulo o leyenda.
- **Donuts:** la donut de **categoría** reparte **euros**; las barras **Pagado/Pendiente/Impago** reparten **número de recibos**, no importes (véase §6.3).

#### Ejercicios

**A — Tras tener movimientos (p. ej. misión C2–C4 o el §6.4)**

1. Comparad **Global** y **Últimos 1 mes**. ¿Las cifras cambian de forma lógica según en qué mes están vuestros cobros de prueba?
2. Alternad **Bruto** y **Neto** con el mismo filtro. ¿Solo en Neto aparece la indicación de serie **sin IVA**?
3. Cambiad un **gasto** de categoría en Contabilidad y volved: ¿solo se mueve la donut de **gastos**?

**B — Tras el ingreso de prueba del §6.4 (los 10 €)**

4. Eliminad ese ingreso en Contabilidad. ¿Los **cuatro KPI** vuelven a los valores anotados **antes** del alta?

**C — Sin depender de tener muchos datos**

5. **Sin cobros en pantalla:** si el club está vacío, ¿las gráficas muestran **estado vacío sereno** o error técnico?
6. **Proyección IA:** pulsad **Actualizar predicción** varias veces seguidas. ¿Veis un estado tipo **“Calculando…”** o requests duplicados confusos?
7. **Filtros en cadena:** Últimos 3 meses → Temporada → Global. ¿Los totales **saltan** de forma coherente en cada paso (sin valores imposibles)?

---

### Misiones — Estadísticas

#### Misión E1 — Primera verificación de KPI

**Dependencias:** habéis completado **C2, C3 y C4** del §5 (ingreso pagado, gasto pagado, ingreso pendiente).

1. **Global + Flujo de Caja Real + Bruto.** Anotad Ingresos, Gastos, Margen, Impuestos.
2. Respecto a la situación **antes** de C2–C4: ingresos **+121** (C2; C4 **no** suma en Flujo real), gastos **+30**, margen **+91** si solo añadisteis esas líneas.
3. Cambiad a **Proyección contable:** los ingresos deben reflejar **+50** más que en modo real (C4).
4. Cambiad a **Neto:** incrementos en bases (~100 del C2, ~24,79 del C3), no en brutos.

#### Misión E2 — Tres ingresos para % de cobros (hoy)

**Dónde:** **Contabilidad → Nuevo ingreso** (tres filas, fecha **hoy**, cuenta **Banco Prueba BETA**, categoría **Cuotas formación**, IVA **0 %**):

| Nombre | Importe | Estado |
|--------|---------|--------|
| **Test barra Pagado** | 10,00 | Pagado |
| **Test barra Pendiente** | 10,00 | Pendiente |
| **Test barra Impago** | 10,00 | Impago |

**Comprobación:** **Cobros — últimos 30 días** debe contar **tres recibos** más; si solo esos tres estuvieran en la ventana, ~**33,33 %** en cada barra (por **número** de recibos, no por euros).

#### Misión E3 — Importe y KPI tras el import (cruce con §5)

Anotad ingresos en Estadísticas **antes** y **después** de la **Misión C5** del §5: diferencia **+25,50 €** en Flujo real / Bruto.

#### Misión E4 — Proyección IA

**Dónde:** **Estadísticas → Actualizar predicción**.

Si el histórico es corto: gráfica vacía o mensaje poco útil → **documentad**; no es un fallo personal (ver §6.3).

**Feedback documentación (beta):** ¿Qué parte del **§6** (teoría, donuts vs barras, misiones E1–E4) **no** se entiende al mirar la pantalla?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---
## 7. Usuarios — la pantalla más importante

Dedicadle más tiempo que a cualquier otra. Es la más compleja y la que más cosas tiene que comprobar.

### 7.1 Las tres tarjetas de resumen

Al entrar en Usuarios, encima de la tabla aparecen tres tarjetas con datos del club:

**Población del club**
Muestra el total de personas y una barra de colores con el reparto (activos, preinscripciones, inactivos…). El número total debe coincidir aproximadamente con las filas que veis en la tabla si quitáis todos los filtros. Si dice "50 personas" y la tabla apenas muestra 10, algo no cuadra.

**Unidades de facturación**
Cuántos pagadores distintos hay y cuántas unidades de cobro gestiona el club. Si creáis jugadores con pagador asignado y este número no cambia, puede ser un fallo de actualización o de las reglas del sistema.

**Estado del sistema**
El número más importante: cuántos jugadores no tienen pagador correctamente asignado. Lo ideal es **0** con un texto verde tipo "Listos para facturar". Si el número es mayor que 0, debe aparecer un botón **"Ver jugadores →"** que lleva a una lista para corregirlos uno a uno. Después de corregir todos y guardar, el contador debe volver a 0 (puede que necesitéis recargar la página).

### 7.2 Los botones de acción

En la parte superior derecha de la pantalla Usuarios:

| Botón | Qué hace |
|-------|----------|
| **➕ Crear** | Abre el formulario para crear un nuevo usuario. |
| **✏️ Editar** | Abre el formulario de edición. Necesitáis tener exactamente una fila seleccionada; si no hay ninguna o hay varias, la app debe avisaros. |
| **🗑️ Eliminar** | Elimina las filas seleccionadas. Podéis eliminar varias a la vez. Debe pedir confirmación antes de borrar. |
| **Exportar Excel** | Descarga un Excel con los datos visibles en la tabla en ese momento. |
| **🔎 Filtrar** | Abre el panel lateral de filtros. |

### 7.3 La tabla de usuarios

**Límite de 5 columnas:** la tabla solo muestra 5 columnas de datos a la vez (más la columna `#` de número de fila). No es un fallo, es por legibilidad.

**Cómo cambiar las columnas:** en la cabecera de cada columna hay un triángulo pequeño (▾). Al pulsarlo se abre una lista con todos los atributos disponibles. Podéis activar y desactivar columnas como "pastillas". Máximo 5 activas al mismo tiempo. Al cambiar, los datos deben seguir alineados correctamente con sus cabeceras.

**Ordenar:** al pulsar el nombre de una columna (no el triángulo), la tabla se ordena por ese campo. Al pulsarlo de nuevo, invierte el orden.

**Seleccionar filas:** cada fila tiene un punto a la derecha. Punto vacío = no seleccionada. Punto relleno = seleccionada. "Editar" requiere exactamente una selección; "Eliminar" acepta varias.

### 7.4 Qué muestra cada columna

| Columna | Qué información tiene | Qué verificar |
|---------|----------------------|---------------|
| **Nombre** | Nombre de la persona | Que coincide con lo guardado al crear. |
| **Email** | Correo de la cuenta | Debe ser único; dos personas con el mismo email es un fallo. |
| **Teléfono** | Número de contacto | Que no rompe la tabla con caracteres raros. |
| **Rol** | Tipo de cuenta | Debe indicar si es preinscripción o ficha interna, no solo "Jugador". |
| **Equipo** | Equipo deportivo asignado | Si cambiáis de temporada activa, revisad que el equipo mostrado tenga sentido. |
| **Padres** | Tutores vinculados al jugador | Si hay vínculo creado pero esta columna sale vacía, es un fallo. |
| **Hijos** | Jugadores vinculados al tutor (con cuenta) | Para cuentas de padre/madre/familiar. |
| **Hijos (no registrados)** | Menores sin cuenta propia gestionados por el tutor | Solo aplica a tutores con hijos manuales. |
| **Estado** | Activo / Trial / Inactivo | Trial suele ir ligado a preinscripciones. Inactivo no debería tener acceso normal. |
| **DNI/Doc** | Número de documento | Debe coincidir con lo introducido al crear o editar. |
| **Pagador** | Quién paga las cuotas de ese usuario | Si aparece en azul subrayado, al pulsarlo se abre una ventana con el detalle. Si pone "—", no hay pagador. |
| **Pago preferido** | Efectivo, Bizum, domiciliación… | Debe coincidir con lo elegido al crear/editar. |
| **IBAN** | Número de cuenta completo | Verificad que se muestra de forma legible. En vuestras capturas tappad los dígitos por privacidad. |
| **Doc. Adjunto** | Enlace al archivo subido | Al pulsar debe abrirse o descargarse. Sin archivo debe mostrar "—". |
| **Empadronado** | ✓ o ✗ | Debe coincidir con la casilla marcada en el formulario. |
| **Fam. Numerosa** | ✓ o ✗ | Igual que la anterior. |

### 7.5 El panel de filtros

Se abre con **🔎 Filtrar**. Los filtros no se aplican hasta que pulsáis **Aplicar**. "Limpiar" borra los valores del panel pero no necesariamente los quita de la tabla hasta que volváis a pulsar Aplicar.

| Filtro | Opciones |
|--------|----------|
| **Nombre** | Texto libre. |
| **Rol** | Admin, Jugador, Fisio, Entrenador, Padre, Madre, Familiar, Patrocinador. Podéis marcar varios. |
| **Tipo** | Todos / Reales / Manuales. |
| **Estado** | Activo, Trial, Inactivo. |
| **Equipo** | Texto libre por nombre de equipo. |
| **Método de pago** | Desplegable. |
| **Titular / IBAN** | Texto libre. |
| **Empadronado** | Cualquiera / Sí / No. |
| **Familia numerosa** | Cualquiera / Sí / No. |

Con varios filtros activos, la tabla debe mostrar solo las filas que cumplen **todos** a la vez. Si no hay ningún resultado, debe verse la tabla vacía sin ningún error en pantalla.

### 7.6 Crear usuario — campos del formulario

| Campo | ¿Es obligatorio? | Notas |
|-------|-----------------|-------|
| **Nombre** | Sí | Sin nombre, el botón "Crear usuario" debe estar deshabilitado. |
| **Apellidos** | Recomendado | Para distinguir personas con el mismo nombre. |
| **Email** | Necesario para cuentas reales | Un jugador sin email no podrá entrar en la app. |
| **Teléfono** | Opcional | |
| **Rol** | Sí | Jugador, Entrenador, Fisio, Familiar/Padre, Administrador. |
| **Datos personales** | Opcional en el alta | Rellenadlos en las pruebas para comprobar que llegan bien a la tabla. |
| **Método de pago** | Según rol | Si elegís "Domiciliación", aparecen los campos Titular e IBAN. |
| **Empadronado / Familia numerosa** | Opcional | Casillas que deben guardarse y verse al editar de nuevo. |
| **Foto documento** | Opcional | Imagen o PDF. |

Al guardar correctamente debe aparecer un mensaje de confirmación y la nueva fila en la tabla.

### 7.7 Editar usuario — qué campos aparecen según el rol

Los campos comunes a todos los roles son: Nombre, Apellidos, Email, Teléfono, Rol, Estado (activo/trial/inactivo), Empadronado, Familia numerosa y subida de foto de documento.

Campos adicionales según el rol:

**Si es Jugador:** tipo de documento, número de documento, Instagram, dirección, provincia, país, método de pago, titular e IBAN para cobros.

**Si es Entrenador o Fisio:** método de liquidación, titular e IBAN (para pagarles según el club).

**Si es Padre, Madre o Familiar:**
- Método de pago, titular, IBAN.
- Campo para vincular con hijo/a escribiendo el email del jugador + botón **Vincular**. Tras vincularlo, en la columna "Hijos" del tutor y en "Padres" del jugador debe verse la relación.
- Lista de hijos vinculados con un botón **radio** para marcar cuál de los tutores es el **pagador principal** de cada hijo (solo puede haber uno por hijo con etiqueta verde).
- Botón **Desvincular** por cada hijo (puede tener restricciones si ya hay cuotas generadas).
- Sección de **hijos sin cuenta**: menores sin login propio — se les añade nombre, apellidos, documento y archivo adjunto.

### 7.8 Pruebas obligatorias en Usuarios

| # | Qué hacer | Qué debe pasar |
|---|-----------|----------------|
| 1 | Crear un jugador con todos los campos rellenos | Aparece en la tabla; al editar, los datos coinciden. |
| 2 | Crear un padre y vincularlo al jugador por email | Ambos muestran la relación en las columnas Padres/Hijos. |
| 3 | Marcar al padre como pagador principal del jugador | Solo aparece un "Pagador" verde por jugador; la tarjeta "Estado del sistema" baja o se mantiene en 0. |
| 4 | Eliminar al padre que tiene hijos y cuotas | La app debe bloquear la acción o avisar claramente; no debe dejar datos rotos sin mensaje. |
| 5 | Exportar Excel con 5 columnas distintas elegidas | El Excel tiene esas mismas columnas con cabeceras legibles. |
| 6 | Filtrar por Rol Jugador + Estado Activo | Solo aparecen jugadores activos. |
| 7 | Ordenar la tabla por Email | El orden alfabético es estable y correcto. |

### 7.9 Escenarios adicionales para explorar

Todos con **datos ficticios**:

**Familia modelo:** crear padre "María López" (mariaprueba@test.com) → crear jugador "Ana López" (anaprueba@test.com) → vincular al padre por email → marcar a María como pagador principal → comprobar la columna Pagador y la tarjeta Estado del sistema → generar una cuota y verificar que el movimiento va asociado a María, no a Ana.

**Dos tutores, un jugador:** crear dos tutores ficticios y vincularlos al mismo jugador. Alternar el radio de pagador principal entre uno y otro. Comprobar que en Contabilidad el siguiente cobro generado va al tutor correcto después del cambio.

**Jugador mayor independiente:** crear un jugador sin ningún tutor en la app, con método de pago "Propio". Generar una cuota y comprobar que el movimiento aparece a nombre del propio jugador.

**Hueco sin pagador:** vincular un tutor a un jugador pero no marcar el radio de pagador principal (si la interfaz lo permite). Comprobar que la tarjeta "Estado del sistema" sube en 1 y que el jugador aparece en la lista "Ver jugadores →".

**Preinscripción:** si habéis importado un Excel con emails nuevos en Ligas, buscad en filtros los usuarios con estado "Trial" o rol "Preinscripción". Intentad editarlos. Luego simulad que ese usuario completa el registro y comprobad que no desaparecen sus datos (hijos, pagador, cuotas).

**Cambio de estado:** coger un usuario activo y pasarlo a inactivo → comprobar que no puede hacer cosas que debería solo un activo (por ejemplo, recibir mensajes, aparecer en comunicaciones) → volver a activarlo y verificar que todo queda igual que antes.

**Foto de documento:** subir un PDF grande (más de 2 MB si la app lo permite) y uno que esté corrupto o tenga extensión incorrecta. Documentad los límites y los mensajes de error que aparecen.

**Hijo manual:** en un tutor, crear un hijo sin cuenta (sin email) con su documento y un archivo adjunto. Guardarlo. Exportar el Excel y comprobar que aparece en la columna "Hijos (no registrados)".

**Correo duplicado:** intentar crear dos usuarios con exactamente el mismo email. La app debe impedirlo con un mensaje claro.

**Columnas raras en export:** exportar el Excel con combinaciones inusuales de 5 columnas (por ejemplo, solo datos bancarios; o solo datos legales). Abrir el archivo y comprobar que las cabeceras son correctas y que no hay columnas vacías o mezcladas.

**Campos con caracteres especiales:** en nombre y apellidos, probar con acentos, ñ, guiones, apóstrofes y caracteres de otros alfabetos. Comprobar que no se rompe la tabla ni los filtros.

#### Comportamiento del panel de filtros (lectura)

En esta pantalla los filtros suelen aplicarse solo cuando pulsáis **Aplicar**. **Limpiar** suele borrar los valores del formulario del panel, pero **la tabla no tiene por qué cambiar** hasta que volváis a pulsar **Aplicar** con criterios nuevos (depende de la versión; lo que importa es que sea **predecible** y esté **indicado** en la UI si no).

#### Ejercicios de interfaz (no exigen datos previos del club)

1. **Limpiar sin aplicar:** abrid filtros, aplicad Rol **Jugador** + algún criterio que reduzca la tabla; pulsad **Limpiar** en el panel **sin** pulsar **Aplicar**. ¿La tabla sigue mostrando el resultado del filtro anterior hasta que aplicáis de nuevo?
2. **Doble clic en Crear:** en el formulario de alta, pulsad **Crear** dos veces muy rápido con datos válidos. ¿Se genera **un solo usuario** o aparecen **duplicados**?

---

### Misiones — Usuarios

#### Misión U1 — Familia del cuaderno (§3.2)

**Dependencias:** habéis leído todo el **§7 Usuarios** y tenéis claros pagador y vínculos.

1. Crear jugadora **Lucía Demo Ruiz**, `lucia.demo.lab@test.com`, rol **Jugador**, **Activo**.
2. Crear **Carlos Tutor Demo**, `carlos.tutor.demo@test.com`, rol padre/familiar según lista.
3. Editar **Carlos** → **Vincular** con email de Lucía → **pagador principal** de Lucía.

**Comprobación:** tarjeta **Estado del sistema** = **0** jugadores sin pagador.

**Feedback documentación (beta):** ¿Qué parte de **U1** o del **§7** **no** habéis entendido?

#### Misión U2 — Ingreso vinculado al jugador

**Dependencias:** **U1** completada.

**Dónde:** **Contabilidad → Nuevo ingreso**.

| Campo | Valor |
|-------|--------|
| Nombre | Autocomplete: **Lucía Demo Ruiz** |
| Importe | **60,00** |
| IVA | **21 %** |
| Estado | **Pagado** |
| Cuenta | **Banco Prueba BETA** |
| Categoría | **Cuotas formación** |
| Fecha | **Hoy** |
| Método | **Efectivo** |

**Comprobación:** **Estadísticas** (Flujo real, Bruto) **+60,00 €** ingresos vs el valor anotado **antes** de este paso.

**Feedback documentación (beta):** ¿Qué parte de **U2**, del resto del **§7** (teoría **§7.1** en adelante) o de **U1** **no** habéis entendido?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 8. Ligas y equipos

### 8.1 Qué hay en esta pantalla

1. **Selector de temporada:** desplegable con todas las temporadas del club. La activa aparece con el texto "(Activa)".
2. **Botones junto al selector:**
   - **Marcar como Activa:** solo aparece si la temporada seleccionada no es la activa. Al usarlo, el resto se desactivan.
   - **Nueva temporada:** modal con nombre, fechas opcionales y casilla para activarla al crear.
   - **Eliminar temporada:** acción irreversible que borra categorías, equipos, convocatorias y fichas ligadas. Debe pedir una confirmación clara con advertencia.
3. **Importar Excel:** asistente para cargar jugadores, entrenadores y tutores masivamente.
4. **Lista de categorías y equipos:** bloques expandibles con los equipos de cada categoría. Podéis crear categorías, crear equipos, editarlos y eliminarlos.
5. **Detalle de equipo:** al pulsar un equipo se abre la vista con la plantilla de jugadores, opciones para quitar jugadores y ver su ficha.

### 8.2 Ejercicios guiados — Ligas y equipos

Seguid el orden; **las preguntas van después** de haber creado lo que pide cada paso.

#### Paso 1 — Estructura mínima

Cread una temporada **2026-2027 Pruebas** (sin marcarla activa si queréis no alterar el club global), una categoría **Benjamín**, un equipo **Tiburones**. Entrad al **detalle del equipo**.

**Comprobación:** la plantilla de jugadores debe estar **vacía** (0 filas o mensaje equivalente).

#### Paso 2 — Cambiar temporada activa

Si el entorno lo permite, **activad** esa temporada nueva. Volved a **Usuarios**.

**Qué mirar:** la columna **Equipo** de cada persona debe reflejar **la temporada que acaba de quedar activa** (si un jugador solo existía en la temporada antigua, puede quedar **sin equipo** o mostrar **guion** — eso es información útil, no un “fallo” automático). Anotad exactamente qué texto veis.

#### Paso 3 — Eliminar temporada con datos

Intentad **eliminar** la temporada que tiene el equipo **Tiburones** (con o sin jugadores, según hayáis importado).

**Comprobación esperada:** o bien la app **impide** borrar y muestra **advertencia clara**, o bien permite borrar pero con **confirmación explícita** de lo que se pierde. Documentad cuál de los dos comportamientos ocurre.

#### Paso 4 — Mismo nombre en dos categorías

Cread **Equipo A** en Benjamín y **Equipo A** en Alevín.

**Comprobación:** en listados y desplegables debe poder distinguirse **por categoría** (etiqueta compuesta, ruta, etc.). Si la UI **mezcla** los dos sin diferenciarlos, es bug de usabilidad.

#### Paso 5 — Temporada no seleccionada

Dejad el desplegable superior en **“Selecciona temporada…”** (o equivalente).

**Comprobación esperada:** la zona de categorías/equipos debe aparecer **vacía** o con **mensaje** (“elige una temporada”), **no** un error sin texto.

### 8.3 Asistente de importación de Excel (jugadores, entrenadores, tutores)

**Cómo abrirlo:** en **Ligas y equipos**, con una **temporada seleccionada** en el desplegable superior, pulsad **Importar Excel**. El título del cuadro es **“Cargar jugadores y entrenadores desde Excel”**.

**Pasos de la interfaz (orden fijo):**

1. **Paso 1 — Plantilla:** **Descargar plantilla Excel**. Si no hay temporada elegida, el botón está deshabilitado y debe verse un aviso en tono ámbar.
2. **Paso 2 — Tu archivo:** arrastrar o elegir `.xlsx` / `.xls`.
3. Pulsad **Revisar archivo (sin guardar)** (o **Volver a revisar el archivo** si ya habíais simulado). Veréis tres bloques:
   - **Qué hay en el archivo** (personas, equipos nuevos vs existentes).
   - **Jugadores y entrenadores** (coincidencias por email, preinscripciones, tutores, avisos).
   - **Problemas graves** (número de filas bloqueantes). Si es **> 0**, **no** debe habilitarse **Confirmar e importar datos**.
4. Si **Problemas graves = 0** → **Confirmar e importar datos**.
5. Pantalla final **Importación completada** con contadores (equipos creados, jugadores, tutores…) y bloque **Invitaciones enviadas por email** (entrenadores con enlace, jugadores con código, tutores, y posibles errores de envío).

Dentro del modal hay un desplegable **«¿Qué columnas necesita el Excel?»**. El contenido resume obligatorios, opcionales, valores del campo **Rol** (`jugador`, `entrenador`, `padre`, `madre`), el vínculo **recíproco** tutor↔hijo (varios emails en la misma celda separados con **`;`** o **`|`**; la simulación fallará si falta un lado) y compatibilidad con columnas de Excels antiguos (liga, URL externa). También indica que **los usuarios con email recibirán una invitación automática por correo** para completar el registro.

**Instrucciones en pantalla (textos del asistente actual)** que debe poder seguir un gestor sin formación técnica:

- Cabecera: **«Cargar jugadores y entrenadores desde Excel»**.
- Párrafo introductorio: *«Alta masiva de la plantilla: **descarga el Excel, rellénalo y súbelo**. El sistema lo revisa primero sin guardar nada — solo confirmas cuando el resumen te cuadre.»* Si hay temporada seleccionada, se muestra una etiqueta con su nombre.
- Sin temporada seleccionada: mensaje ámbar *«Selecciona una temporada arriba en la página para poder descargar.»*
- **Paso 1 — Plantilla:** botón **Descargar plantilla Excel**.
- **Paso 2 — Tu archivo:** *«Arrastra aquí el Excel rellenado o haz clic para elegirlo»* — formato **`.xlsx` / `.xls`**; nota *«la plantilla ya tiene el formato correcto»*.
- Botón azul: **Revisar archivo (sin guardar)** (tras una primera revisión el mismo botón pasa a **«Volver a revisar el archivo»**).
- Resumen en tres tarjetas: **Qué hay en el archivo** (filas totales, equipos nuevos vs existentes reutilizados), **Jugadores y entrenadores** (coincidencias por email, preinscripciones, entrenadores y tutores nuevos o existentes, avisos informativos), **Problemas graves** con el texto *«Filas que hay que corregir antes de poder importar con seguridad»*. Si hay errores, lista **«Primeras filas con error»** (fila + mensaje).
- Solo si **Problemas graves = 0:** aparece **Confirmar e importar datos**.
- Tras confirmar: **Importación completada** con desglose (equipos creados, jugadores enlazados o actualizados, preinscripciones, entrenadores, tutores, errores de fila si los hay). Cuando procede, bloque **Invitaciones enviadas por email** (entrenadores con link para contraseña, jugadores con código de registro, tutores, **emails que no se pudieron enviar**).

> En esta aplicación, «importación de usuarios vía Excel» en masa equivale a **este asistente en Ligas** (altas de **jugadores, entrenadores y tutores** con cuenta o preinscripción). La pantalla **Usuarios** sirve para altas manuales y edición; no sustituye a esta plantilla.

---

#### Ejercicio beta — Validación de «Importación de usuarios vía Excel»

**Objetivo:** comprobar si un gestor de club **entiende las instrucciones** solo con lo que muestra la app y esta guía, sin soporte externo.

**Tareas (orden recomendado)**

1. En **Ligas y equipos**, seleccionad una temporada de prueba y abrid **Importar Excel**. **Sin pulsar aún** «Revisar archivo», leed la cabecera, el párrafo introductorio y el desplegable **«¿Qué columnas necesita el Excel?»**.
2. Responded por escrito: **¿sabríais qué hacer después**, solo con ese texto?
3. Descargad **Descargar plantilla Excel**, abrid el archivo y contrastad los **encabezados** con lo que decía el desplegable.
4. *(Opcional pero útil)* Subid la plantilla tal cual (o con solo la fila de ejemplo) y pulsad **Revisar archivo (sin guardar)**. El objetivo es ver si **interpretáis** las tres tarjetas del resumen y el número de **Problemas graves**. No confirméis la importación si quien coordina las pruebas no lo permite.

**Evaluación obligatoria (responded por escrito)**

1. **¿Se entiende lo que dicen las instrucciones** (modal + desplegable + pasos 1 y 2), para alguien que nunca ha usado el ERP?
2. **¿Qué partes son confusas** (orden, vocabulario, temporada obligatoria, vínculo tutor↔hijo, diferencia preinscripción / cuenta existente)?
3. **¿Qué añadiríais o quitaríais** en la **interfaz** o en **esta guía (§8.3)** para que el proceso sea más intuitivo?

**Feedback documentación (beta):** ¿Qué parte de **esta guía** (por ejemplo §8.3 o el cuadro de textos «en pantalla» de arriba) **no** habéis entendido o **no coincide** con lo que veis en la aplicación? Citar apartado y frase si podéis.

---

#### Ejercicio guiado L1 — Simulación sin tocar la base de datos

**Objetivo:** aprender el flujo sin crear basura en el club.

1. Seleccionad una temporada de prueba (mejor una vacía o poco usada).
2. Descargad la plantilla, abrid el Excel y **no guardéis** aún: leed la primera fila de ejemplo.
3. Subid el archivo **tal cual** y pulsad **Revisar archivo (sin guardar)**.
4. **Anotad:** cuántos **avisos** y cuántos **problemas graves** salen. ¿El botón de confirmar está bloqueado o no?

**Esperado razonable:** o bien la simulación trata las filas ejemplo como datos a importar (y entonces veréis números en “preinscripción” / equipos), o bien el backend las filtra; lo importante es que **entendáis el informe** antes de confirmar.

5. **No pulséis Confirmar** en esta ronda si quien coordine las pruebas no quiere datos de ejemplo en BD.

**Feedback documentación (beta):** ¿Qué parte del **ejercicio L1** o del **§8.3** **no** habéis entendido?

---

#### Ejercicio guiado L2 — Error de vínculo tutor / hijo

1. Duplicad la plantilla a `prueba_vinculo_malo.xlsx`.
2. En una fila **jugador**, poned un email de tutor en la columna que corresponda según la plantilla.
3. **Quitad** en la fila del **tutor** la referencia al hijo (o el email recíproco).
4. Simulad (**Revisar archivo**).

**Esperado:** **Problemas graves** > 0 y lista de primeras filas con error; **no** debe dejar confirmar hasta corregir el Excel.

**Feedback documentación (beta):** ¿Qué parte del **ejercicio L2** o del **§8.3** **no** habéis entendido?

---

#### Ejercicio guiado L3 — Equipo que no existía

1. En el Excel, en una fila jugador, poned **categoría + equipo** que **no** esté creado en la web (nombres nuevos inventados).
2. Simulad.

**Esperado:** en “Qué hay en el archivo” o listados inferiores, referencia a **equipos nuevos que se crearían** (o mensaje equivalente). Leed el texto y confirmad con quien coordine las pruebas antes de importar de verdad.

**Feedback documentación (beta):** ¿Qué parte del **ejercicio L3** o del **§8.3** **no** habéis entendido?

---

#### Ejercicio guiado L4 — Importación real controlada (solo con permiso)

1. Con el mismo archivo ya **sin errores graves**, **Confirmar e importar datos**.
2. **Usuarios:** buscad por email las filas que habíais puesto; estad **activo / trial / preinscripción** según el caso.
3. **Ligas:** entrad en el **detalle del equipo** que debía crearse: ¿aparecen jugadores o placeholders?
4. **Contabilidad / Estadísticas:** solo si la importación genera usuarios con cuotas automáticas en vuestro entorno; si no aplica, anotad “N/A”.

5. **Auditoría / Comunicación:** si se enviaron emails, comprobad bandeja de prueba o registro de errores de email en el resumen del asistente.

**Archivo corrupto:** renombrad un `.csv` a `.xlsx` e intentad subirlo.

**Esperado:** error legible (texto rojo en pantalla o **mensaje emergente**), sin dejar el navegador cargando sin fin.

**Feedback documentación (beta):** ¿Qué parte del **ejercicio L4** o del **§8.3** **no** habéis entendido?

---

### Misiones — Ligas y equipos

#### Misión LG1 — Temporada, categoría e import (cuaderno §3.2)

**Dependencias:** usuarios del cuaderno creados si el import referencia email.

1. Temporada **2026-2027 Formación**; categoría **Alevín Formación**; equipo **Tiburones Formación**.
2. **Importar Excel:** al menos **Revisar sin guardar** con una fila que use `lucia.demo.lab@test.com` y equipo **Tiburones Formación**; **confirmar** solo con permiso de quien coordine las pruebas.

**Comprobación:** informe de simulación coherente (coincidencias / preinscripción / avisos).

**Feedback documentación (beta):** ¿Qué parte de **LG1** o del **§8.3** **no** habéis entendido?

### Misión libre — Exploración cruzada (elegid ≥ 5)

Combinaciones útiles entre módulos ya explicados:

1. Cambiar solo **categoría** de un ingreso y mirar la **dona** de ingresos en Estadísticas.
2. **Gasto pendiente** → no suma en Flujo real.
3. Tabla ingresos: columnas visibles solo **Estado** + **IVA/Neto**.
4. **Import** con cuenta inexistente → error claro.
5. **Comunicación:** mensaje a rol **Entrenador** (si existe).
6. **Marketing:** partido manual «Victoria 2-1 contra Rival Genérico».
7. **Auditoría:** filtro **Crear** + vuestro email.
8. **Usuarios:** **Exportar Excel** con cinco columnas distintas.

**Feedback documentación (beta):** ¿Qué parte del **§8** (teoría, import Excel, ejercicios L1–L4, LG1 o misión libre) **no** queda clara?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 9. Comunicación

Bandeja de mensajes internos del club. Podéis enviar mensajes a usuarios por rol, por equipo o a todos a la vez.

**Al redactar un mensaje:** título, cuerpo (límite aproximado de 8.000 caracteres), destinatario por rol, usuario concreto o equipo, con opción de broadcast a todos.

### Pruebas — Comunicación

- Enviar un mensaje solo al rol Entrenador con un equipo concreto filtrado. ¿Solo llega a los entrenadores de ese equipo?
- Escribir un mensaje de exactamente 7.990 caracteres y otro de 8.100. ¿El segundo da un mensaje amable de "demasiado largo" o simplemente corta el texto?
- Responder varias veces en una cadena y comprobar que el orden cronológico es correcto.
- Eliminar una notificación. ¿Desaparece de la lista sin afectar a las demás?
- Buscar un mensaje por palabra clave. ¿La búsqueda funciona en el título y en el cuerpo?

**Feedback documentación (beta):** ¿Qué parte del **§9** o de estas pruebas **no** habéis entendido?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 10. Marketing

Genera textos para redes sociales a partir de eventos deportivos del club. Tiene un selector de equipo para cargar convocatorias reales, y un modo manual para escribir un partido ficticio.

**Importante:** nunca uséis datos personales de socios reales en esta sección.

### Pruebas — Marketing

- Evento manual mínimo: "Victoria 3-1 contra Equipo Rival" con fecha y notas genéricas. ¿Genera textos para Instagram y X?
- Probar con un equipo que no tiene ninguna convocatoria cargada. ¿Mensaje orientativo o pantalla en blanco?
- Añadir una instrucción extra ("tono formal" o "en tono humorístico"). ¿El texto generado refleja la instrucción?
- Comprobar que los textos generados no incluyen nombres de socios ni datos personales si solo habéis seleccionado datos deportivos genéricos.

**Feedback documentación (beta):** ¿Qué parte del **§10** **no** queda clara?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 11. Auditoría

Historial completo de acciones del club: quién hizo qué y cuándo.

Filtros disponibles: tipo de acción (Crear, Actualizar, Eliminar, Pago, Configuración, Otro), modelo afectado, texto libre, rango de fechas, email del actor, ID del objeto. Paginación de 25, 50 o 100 registros.

### Pruebas — Auditoría

- Crear un usuario en Usuarios y luego buscar en Auditoría con tipo "Crear" y vuestro email como actor. ¿Aparece el registro?
- Guardar la URL de tienda en Herramientas y buscar el tipo "Configuración". ¿Se registra?
- Marcar un movimiento como pagado y buscar tipo "Pago". ¿El registro muestra el importe y el usuario afectado?
- Poner las fechas en orden inverso (desde > hasta). ¿La app devuelve tabla vacía limpiamente o muestra un error?

**Feedback documentación (beta):** ¿Qué parte del **§11** **no** habéis entendido?

**Cierre del módulo (beta) — UX:** ¿Mejorarías algo notorio del UX?

---

## 12. Pruebas de comportamiento general

Estas pruebas no son de una sección concreta, sino del comportamiento general de la aplicación:

| Situación | Qué observar |
|-----------|--------------|
| **Datos absurdos en formularios** | Números negativos en importes, emojis en campos de nombre, fechas imposibles (31 de febrero). ¿Mensaje claro o pantalla rota? |
| **Doble clic rápido en Crear/Guardar** | ¿Se crean registros duplicados o la app lo previene? |
| **Cambiar de sección a mitad de un formulario** | ¿Se pierde lo escrito sin aviso? ¿O la app pregunta si queréis salir? |
| **Sesión larga sin actividad** | Después de un rato inactivos, ¿la app avisa de sesión caducada o simplemente falla en la siguiente acción sin explicación? |
| **Resoluciones de pantalla** | Probad en ventana estrecha (similar a tablet). ¿Los botones y tablas siguen siendo usables? |
| **Recarga de página a mitad de un proceso** | Si recargáis el navegador mientras tenéis un modal abierto, ¿se pierde el estado o lo recupera? |
| **Varios modales encadenados** | Abrir Editar → dentro, pulsar Vincular → se abre otro modal dentro del modal. ¿Se cierran bien al confirmar o cancelar? |

---

## 13. Números que deben cuadrar entre secciones

| Qué comparar | Dónde |
|--------------|-------|
| Total cobrado / pendiente con el mismo criterio de fechas | Estadísticas ↔ Contabilidad |
| Número de pagadores únicos | Tarjeta Usuarios ↔ filas reales en la tabla |
| Importe de un movimiento | Pantalla de Contabilidad ↔ PDF del informe |
| Jugadores por equipo | Detalle del equipo en Ligas ↔ columna Equipo en Usuarios |
| Acciones registradas | Lo que hicisteis ↔ registros en Auditoría |

---

## 14. Plantilla para vuestra hoja de entrega

Copiad y rellenad esto para cada módulo que probéis:

```
Módulo: _______________
Fecha de prueba: _______________

Comportamientos correctos confirmados:
- 
- 

Fallos encontrados:
- Descripción: 
  Pasos para reproducirlo:
  1.
  2.
  3.
  Captura: [adjuntar]
  
Sugerencias de mejora (textos de ayuda, mensajes más claros, etc.):
- 

Notas adicionales:
-
```

**Tras las misiones integradas en la guía:** si las habéis seguido, anotad en la hoja de entrega los KPI sobre todo tras **E1** (Estadísticas), **C5** (import Excel) y **U2** (ingreso vinculado), y lo que documentéis en **C6** (PDF) y **C7** (vencidos), en lugar de depender solo de la tabla de muestra siguiente. Si habéis hecho **§5.8** y/o **C8–C15**, sumad comprobaciones de cuotas, nombre externo, imports vacíos/erróneos, categorías nuevas, justificantes y fechas antiguas.

Para los ejercicios **§5.4–5.6** (o como repaso con otros importes), rellenad también:

```
Ejercicio 1
  Antes: Ingresos ___ / Gastos ___ / Margen ___ / IVA ___
  Después (Bruto, solo pagados): Ingresos +50? ___ / Gastos +30? ___ / Margen +20? ___ / IVA +3,47? ___
  En Neto: Ingresos +41,32? ___ / Gastos +24,79? ___ / Margen +16,53? ___

Ejercicio 2
  ¿Flujo Real sin cambio en ingreso pendiente? ___
  ¿Proyección Contable sube +50 bruto? ___

Ejercicio 3 (informe PDF)
  Rango de fechas usado: ___
  ¿Aparecen los 50 € cobrados y los 30 € pagados en flujo de caja? ___
  ¿El IVA es coherente con los cálculos? ___
```

---

## 15. Si algo "no cuadra" — checklist rápido

| Síntoma | Qué revisar primero |
|---------|---------------------|
| Estadísticas no sube tras crear un movimiento | ¿El estado es "Pagado"? ¿Estáis en modo "Flujo Real" o "Proyección"? |
| El movimiento no aparece en el PDF | ¿Las fechas del informe cubren la fecha del movimiento? |
| Los céntimos difieren en 0,01 € | Redondeo por línea; es normal en las bases; lo que no debe diferir son los totales brutos. |
| El IVA parece el doble de lo esperado | Posiblemente estáis leyendo el bruto como si fuera la base. Releed la explicación del apartado 5.3. |
| Un usuario desaparece al cambiar de temporada | ¿Ese usuario está asignado a un equipo de la temporada anterior? Comprobad en Ligas. |
| El filtro no funciona como esperáis | ¿Habéis pulsado "Aplicar" después de configurar los filtros? |

---

## 16. Glosario

| Término | En qué consiste |
|---------|-----------------|
| **Club** | La organización que gestionáis. Vuestros datos no se mezclan con los de otros clubs. |
| **Rol** | Tipo de cuenta: admin, jugador, padre, entrenador... |
| **Temporada activa** | El curso deportivo de referencia para listados y equipos. |
| **Pagador principal** | Tutor (o el propio jugador) que encabeza el cobro de cuotas. |
| **Movimiento** | Línea individual de contabilidad: una entrada o una salida. |
| **Cuota (plantilla)** | Regla para generar movimientos periódicos automáticamente. |
| **Preinscripción** | Alta hecha por el club antes de que el usuario complete su registro. |
| **Ficha interna** | Borrador creado por administración, sin acceso a la app para el usuario. |
| **Auditoría** | Historial de acciones importantes: quién hizo qué y cuándo. |
| **KPI** | Indicador clave de rendimiento. En este contexto, los números grandes del resumen financiero. |
| **Bruto** | Importe con IVA incluido. |
| **Neto** | Importe sin IVA (base imponible). |
| **SEPA** | Sistema de cobro por domiciliación bancaria. Requiere IBAN del pagador y mandato firmado. |
| **Flujo de Caja Real** | Solo cuenta dinero que ya ha entrado o salido (estado Pagado). |
| **Proyección Contable** | Cuenta también los cobros pendientes, no solo los realizados. |
| **Proyección IA** | Pronóstico estadístico a partir del histórico de movimientos; con pocos o ningún dato el resultado puede ser vacío o poco fiable (no es un fallo de vuestras pruebas). |
