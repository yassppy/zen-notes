# 09_prompt
```
Actúa como revisor de seguridad de cadena de suministro para un servicio Python.
Quiero que generes un documento de riesgo en Markdown para este hallazgo.

Contexto:
- El repositorio es `payments-svc`.
- Estamos revisando una dependencia sugerida para el proyecto.
- No debes inventar informacion de GitHub, CI, historial remoto, reputacion del paquete ni datos que no esten en los archivos o evidencia adjunta.
- La existencia de una dependencia debe basarse en la salida del auditor, no en memoria ni suposiciones.

Archivos/evidencia que te adjunto:
- `requirements.txt`
- salida de `python scripts/audit_dependencies.py requirements.txt`

Tarea:
1. Identifica la dependencia sospechosa o inexistente.
2. Explica por que puede representar un riesgo de slopsquatting.
3. Separa claramente evidencia verificable de inferencias.
4. Propon mitigaciones concretas para este repositorio.
5. Genera el contenido final para `docs/slopsquatting-requests-ai-utils.md`.

Restricciones:
- No afirmes que el paquete es meficioso solo porque no existe.
- No recomiendes instalar la dependencia sospechosa.
- No propongas controles que requieran herramientas externas no mencionadas.
- Si falta evidencia, dilo explicitamente.

Formato de salida:
Devuelve solo Markdown, sin bloque de codigo envolvente, con estas secciones:

# Slopsquatting: requests-ai-utils

## Hallazgo

## Evidencia

## Riesgo

## Decisión

## Mitigaciones

## Relación con SBOM y NIST

Contenido de requirements.txt:
[Tomar contenido de requirements.txt]

Salida del auditor:
[Tomar salida de python scripts/audit_dependencies.py requirements.txt
```

