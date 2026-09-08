# PLANTILLA — INICIO DE NUEVO MANIFIESTO

Usá esta plantilla como prompt de entrada para iniciar un trabajo nuevo.

Los tokens `{{...}}` deben materializarse con los valores reales del trabajo antes de usarla.

No es obligatorio usar esta plantilla para que `metodo-manifiestos-ai` funcione; es una entrada recomendada para reducir ambigüedad y omisiones.

---

Necesito que me hagas un manifiesto de trabajo y, una vez que yo lo apruebe y quede publicado, me entregues también el prompt completo y listo para iniciar al ORQUESTADOR.

## Autoridades

El método para entrevistarme, redactar, aprobar, publicar el manifiesto y producir el prompt de arranque está en:

```text
METODO_MANIFIESTOS_REPO={{METODO_MANIFIESTOS_REPO}}
METODO_MANIFIESTOS_LOCAL={{METODO_MANIFIESTOS_LOCAL}}
```

Las reglas autoritativas del ORQUESTADOR están en:

```text
RULES_ORCHESTRATOR_REPO={{RULES_ORCHESTRATOR_REPO}}
RULES_ORCHESTRATOR_LOCAL={{RULES_ORCHESTRATOR_LOCAL}}
```

El método y las reglas con las que trabajan el AUDITOR y el CONSTRUCTOR están en:

```text
REVOLUTIONS_REPO={{REVOLUTIONS_REPO}}
REVOLUTIONS_LOCAL={{REVOLUTIONS_LOCAL}}
```

Los manifiestos aprobados deben publicarse en:

```text
MANIFEST_LIBRARY_REPO={{MANIFEST_LIBRARY_REPO}}
MANIFEST_LIBRARY_LOCAL={{MANIFEST_LIBRARY_LOCAL}}
```

Antes de producir el paquete final de constitución y el prompt del ORQUESTADOR, obtené de Git las identidades exactas necesarias conforme a `metodo-manifiestos-ai`.

No inventes ni abrevies SHAs.

## Identidad del trabajo

```text
WORK_ID={{WORK_ID}}
CARRIL={{CARRIL}}
```

Si `WORK_ID` todavía no está definido, ayudame a cerrarlo durante la entrevista.

## Runtimes de los actores

```text
AUDITOR_RUNTIME={{AUDITOR_RUNTIME}}
CONSTRUCTOR_RUNTIME={{CONSTRUCTOR_RUNTIME}}
```

## Repositorios de ejecución

AUDITOR:

```text
AUDIT_REPO={{AUDIT_REPO}}
AUDIT_LOCAL_PATH={{AUDIT_LOCAL_PATH}}
```

CONSTRUCTOR:

```text
WORK_REPO={{WORK_REPO}}
WORK_LOCAL_PATH={{WORK_LOCAL_PATH}}
```

El CONSTRUCTOR debe abrirse localmente exactamente en `WORK_LOCAL_PATH`.

El AUDITOR debe saber inequívocamente:

- cuál es su repositorio de trabajo;
- cuál es el repositorio de trabajo del CONSTRUCTOR;
- dónde trabaja localmente el CONSTRUCTOR;
- qué repositorios GitHub y locales están disponibles como fuentes;
- cuáles son sus propias fronteras de escritura;
- cuáles son las fronteras de escritura del CONSTRUCTOR.

## Raíz local

```text
ROOT_LOCAL={{ROOT_LOCAL}}
```

Los repositorios locales relevantes están bajo esa raíz cuando así se declare en la constitución.

## Mapa de repositorios GitHub y locales

```text
MANIFEST_LIBRARY_REPO={{MANIFEST_LIBRARY_REPO}}
MANIFEST_LIBRARY_LOCAL={{MANIFEST_LIBRARY_LOCAL}}

METODO_MANIFIESTOS_REPO={{METODO_MANIFIESTOS_REPO}}
METODO_MANIFIESTOS_LOCAL={{METODO_MANIFIESTOS_LOCAL}}

WORK_REPO={{WORK_REPO}}
WORK_LOCAL={{WORK_LOCAL_PATH}}

AUDIT_REPO={{AUDIT_REPO}}
AUDIT_LOCAL={{AUDIT_LOCAL_PATH}}

REVOLUTIONS_REPO={{REVOLUTIONS_REPO}}
REVOLUTIONS_LOCAL={{REVOLUTIONS_LOCAL}}

RULES_ORCHESTRATOR_REPO={{RULES_ORCHESTRATOR_REPO}}
RULES_ORCHESTRATOR_LOCAL={{RULES_ORCHESTRATOR_LOCAL}}

{{REPOS_ADICIONALES_GITHUB_Y_LOCAL}}
```

Estos pares GitHub/local son coordenadas de localización.

No amplían por sí mismos ninguna frontera de escritura.

## Trabajo que quiero realizar

A continuación te voy a explicar en lenguaje natural qué quiero hacer.

```text
{{TRABAJO_DESCRIPCION}}
```

Usá `METODO-MANIFIESTOS.md` para entrevistarme solamente sobre aquello que todavía sea materialmente necesario cerrar.

No vuelvas a preguntarme datos que ya estén inequívocamente presentes en este mensaje.

Ayudame a definir, cuando corresponda:

- objetivo;
- resultado observable;
- alcance;
- exclusiones;
- restricciones;
- riesgos;
- criterios de éxito;
- superficies de trabajo;
- capacidades;
- necesidades humanas;
- política de relevo;
- reproducibilidad;
- fuentes auxiliares;
- cualquier decisión que deba quedar reservada al humano.

## Política de relevos

Si la política todavía no está definida, preguntame qué quiero para cada rol.

Debe poder expresarse, entre otras opciones, como:

```text
- sólo manual;
- nunca automáticamente;
- cada N intervenciones;
- en determinados límites de unidad;
- combinación explícita de políticas.
```

Si ya está definida, usá:

```text
POLITICA_RELEVO_CONSTRUCTOR={{POLITICA_RELEVO_CONSTRUCTOR}}
POLITICA_RELEVO_AUDITOR={{POLITICA_RELEVO_AUDITOR}}
```

La política concreta debe quedar constituida conforme a `metodo-manifiestos-ai`.

El ORQUESTADOR nunca debe contar, derivar ni decidir relevos.

Una directiva humana como:

```text
RELEVAR CONSTRUCTOR
RELEVAR AUDITOR
```

nunca autoriza directamente al ORQUESTADOR a abrir una instancia `fresh`.

El relevo debe pasar por el actor con autoridad conforme a REVOLUTIONS y `rules-orchestrator-ai`.

Sólo un sobre válido con:

```text
next_instance=fresh
```

autoriza al ORQUESTADOR a abrir una instancia nueva.

## Secuencia obligatoria

Trabajá en este orden:

```text
1. Leer las autoridades declaradas.
2. Entender mi intención.
3. Entrevistarme sólo por los puntos materialmente abiertos.
4. Proponer el MANIFIESTO_TRABAJO.md.
5. Esperar mi aprobación humana explícita.
6. No publicar antes de esa aprobación.
7. Una vez aprobado, publicar el manifiesto en manifiestos-trabajo-ai.
8. Obtener su SHA exacto y las demás identidades Git necesarias.
9. Materializar el paquete de constitución.
10. Materializar plantillas/ARRANQUE_ORQUESTADOR.md con todos los valores reales.
11. Entregarme el prompt completo del ORQUESTADOR listo para copiar y pegar.
```

## Requisito del prompt final del ORQUESTADOR

El prompt final debe incluir inequívocamente:

- `WORK_ID`;
- `CARRIL`;
- método y SHA exacto;
- manifiesto, path y SHA exacto;
- reglas del ORQUESTADOR y SHA exacto;
- repositorio del AUDITOR;
- repositorio del CONSTRUCTOR;
- todos los repositorios GitHub relevantes;
- todos los paths locales relevantes;
- `ROOT_LOCAL`;
- runtime de cada actor;
- directorio exacto en que debe abrirse Claude Code;
- superficies de lectura y escritura;
- política de relevo constituida;
- guardrails de `current/fresh`;
- guardrails de relevos humanos;
- guardrail que prohíbe abrir un `fresh` sin un sobre válido que lo ordene;
- transporte literal;
- paths locales Windows materializados en forma transport-safe con barras `/`;
- ausencia de escapes de presentación dentro de identificadores, delimitadores, URLs y paths;
- preflight de integridad del paquete inicial antes del envío, incluida lectura de vuelta de la interfaz cuando pueda transformar texto;
- fail-closed si aparecen adjuntos o artefactos laterales no pertenecientes al string fuente;
- separación mecánica entre instrucciones privadas del ORQUESTADOR y `PAQUETE_AUDITOR_INICIAL`;
- instrucción inequívoca de que el primer AUDITOR se abre como conversación NUEVA de ChatGPT web cuando ese sea el runtime declarado.

El primer AUDITOR debe recibir únicamente `PAQUETE_AUDITOR_INICIAL`, nunca las instrucciones privadas del ORQUESTADOR.

No me entregues un prompt genérico con placeholders una vez terminado el proceso: el prompt final debe estar completamente materializado con las coordenadas reales de este trabajo.

Para el prompt final, si yo proporcioné paths Windows con barras invertidas, canonicalizalos para
transporte como `C:/ruta/repo` sin cambiar su significado. No agregues escapes Markdown como
`WORK\_ID`, `BEGIN\_PAQUETE...` o `C:/Franco\_Metodos\_AI`; el texto entregado debe contener
los caracteres reales que debe recibir el ORQUESTADOR.
