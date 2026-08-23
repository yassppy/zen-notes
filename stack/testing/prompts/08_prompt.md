# 08_prompt
```
Actúa como red team de aplicaciones Python para `payments-svc`.

Quiero generar tests adversariales anclados en OWASP Top 10 para la superficie de búsqueda de clientes.

**Contexto:**

* El repo tiene una función que busca clientes por email.
* Semgrep marcó un riesgo de SQL injection por SQL construido con concatenación.
* También hay funciones seguras que usan parámetros.

**Objetivo:**
Proponer payloads y casos de prueba para demostrar si la superficie es explotable.

**Importante:**

* No busques que todos los tests queden verdes contra el código actual.
* No cambies el código productivo para hacer pasar las pruebas.
* Los tests deben expresar el comportamiento seguro esperado.

**Incluye familias:**

* OWASP A03 Injection: payloads de SQL injection.
* Entradas malformadas: strings vacíos, espacios y caracteres de control.
* Valores de frontera: strings largos.
* Comparación contra una ruta segura o parametrizada si existe.

**Reglas:**

* No inventes endpoints si el repo solo expone funciones.
* Usa los nombres reales de funciones y archivos del repo.
* Cada payload debe tener objetivo, expectativa segura y razón del riesgo.
* Incluye al menos un caso que deba fallar contra la implementación actual si la SQLi es explotable.
* No conviertas la vulnerabilidad en una expectativa aceptada solo para que el test pase.
* No marques como correcto que una búsqueda por email devuelva un cliente cuando el payload no es un email real.
* No pidas dependencias externas.
* Devuelve una lista que pueda convertirse en `samples/security/adversarial-payloads.json` y `tests/test_adversarial.py`.

**Criterio de aceptación:**

* La suite generada debe incluir un test contra `find_customer_by_email`.
* Debe usar un payload tipo tautología SQL, por ejemplo `' OR '1'='1`.
```

