# 04_prompt
```
No escribas codigo.

No cambies tests.

No cambies archivos.

lee este reporte de mutation testing y ayudame a claseificar visualmente los mutantes, entrega una tabla con:

- Mutante:

- Funcion:

- Que cambio hizo:

- Que comportamiento podria estar sin cubrir:

- Clasificacion: accionable|equivalente|no accionable|pendiente de decision

- Por que:

- Lo resolveriamos en una siguiente iteracion de test: si|no|requiere decision

No propongas todavia el codigo de los test. Solo quiero entender el reporte.
```


```
No cambies código de producción.

No cambies FAILURE-MODES.md.

No agregues dependencias.

Analiza mutation-report.txt, mutation-report-analysis.md, src/payment\_svc/refuels.py y tests/test\_refuels.py.

Queremos mejorar la suite de tests usando mutation testing, pero sin perseguir mutantes por score.

Para cada mutante sobreviviente:

- identifica qué cambio hizo el mutante

- explica qué comportamiento observable quedó sin cubrir.

- Clasifícalo como actionable|equivalente|no actionable|pendiente de decisión.

- Si es accionable, relaciónalo con un contrato confirmado o una regla observable del módulo.

- Si no hay un contrato claro, no escribas un test para este mutante.

Después, modifícalo solo test/test\_refults.py.

Agrega únicamente tests para mutantes accionables que representen comportamiento observable y relevante para pagos.

No escribas tests para:

- type hints, decoradores

- detalles internos sin contrato

- mutantes equivalentes

- cambios que no alteran comportamiento observable.

Mantén unittest.

Mantén import simple desde payments\_svc.refults.

Al final explica:

- ¿Qué tes agregaste?

- ¿Qué mutantes deberías matar?

- ¿Qué mutantes decidiste no perseguir y por qué?
```

Luego en terminal 

```sh
.\.venv\Scripts\cosmic-ray.exe init cosmic-ray.toml mutation.sqlite --force

.\.venv\Scripts\cosmic-ray.exe exec cosmic-ray.toml mutation.sqlite

.\.venv\Scripts\cr-report.exe mutation.sqlite | Tee-Object -FilePath MUTATION-REPORT.txt
```