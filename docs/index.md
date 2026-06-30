# API de recall vehicular en Argentina

[![Docs](https://img.shields.io/badge/docs-patente.ar-0A66C2)](https://patente.ar/api-recall)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-public%20docs-181717)](https://patente-ar.github.io/api-recall-argentina/)
[![Argentina](https://img.shields.io/badge/market-Argentina-38BDF8)](https://patente.ar)
[![Endpoint](https://img.shields.io/badge/endpoint-POST%20%2Fv1%2Fconsultas-111827)](https://patente.ar/api-recall)
[![Payload](https://img.shields.io/badge/payload-JSON-334155)](../openapi/openapi.yaml)
[![Auth](https://img.shields.io/badge/auth-Bearer%20API%20key-2563EB)](#request)
[![Webhooks](https://img.shields.io/badge/webhooks-HMAC%20SHA--256-7C3AED)](#webhooks)
[![Idempotency](https://img.shields.io/badge/idempotency-Idempotency--Key-059669)](#request)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.1-16A34A)](../openapi/openapi.yaml)
[![Examples](https://img.shields.io/badge/examples-curl%20%7C%20Node.js%20%7C%20Python-F97316)](#inicio-rapido)
[![License: MIT](https://img.shields.io/badge/license-MIT-yellow.svg)](../LICENSE)

Consulta campanas de recall por VIN para posventa, seguros, garantias, talleres, CRM y procesos de entrega vehicular.

Este kit publico esta escrito para busquedas tecnicas y comerciales como "API recall vehicular", "API de recall vehicular en Argentina", "API patente Argentina", "consulta por patente API" e "integracion vehicular Argentina".

## Inicio rapido

- Endpoint: `https://api.patente.ar/v1/consultas`
- Producto: `recall`
- Entrada: `vin`
- Ejemplo: `8AJXXXXXXXX123456`
- OpenAPI: [openapi.yaml](../openapi/openapi.yaml)
- Ejemplos: [curl](../examples/curl/consulta.sh), [Node.js](../examples/node/consulta.mjs), [Python](../examples/python/consulta.py)

## Casos de uso

- Posventa.
- Seguros.
- Garantias.
- Talleres.
- Crm.

## Request

```http
POST /v1/consultas HTTP/1.1
Host: api.patente.ar
Authorization: Bearer pa_live_xxx
Content-Type: application/json
Idempotency-Key: orden-externa-001
x-token: orden-externa-001
```

```json
{
  "vin": [
    "8AJXXXXXXXX123456"
  ],
  "marca": "toyota"
}
```

## Webhooks

Los resultados asincronicos pueden recibirse por webhook firmado con HMAC SHA-256. Guardar `requestId`, validar `x-patente-signature` y usar `Idempotency-Key` para reintentos seguros.

## Confianza operativa

- Entrada principal por VIN y marca.
- Pensada para flujos de seguridad vehicular y posventa.
- Webhook firmado para integrar resultados en sistemas propios.



## Links

- Producto comercial: [https://patente.ar/api-recall](https://patente.ar/api-recall)
- Sitio principal: [https://patente.ar](https://patente.ar)
- Repositorio: [https://github.com/patente-ar/api-recall-argentina](https://github.com/patente-ar/api-recall-argentina)
