# API de recall vehicular en Argentina

[![Docs](https://img.shields.io/badge/docs-patente.ar-0A66C2)](https://patente.ar/api-recall)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-public%20docs-181717)](https://patente-ar.github.io/api-recall-argentina/)
[![Argentina](https://img.shields.io/badge/market-Argentina-38BDF8)](https://patente.ar)
[![Endpoint](https://img.shields.io/badge/endpoint-POST%20%2Fv1%2Fconsultas-111827)](https://patente.ar/api-recall)
[![Payload](https://img.shields.io/badge/payload-JSON-334155)](../openapi/openapi.yaml)
[![Auth](https://img.shields.io/badge/auth-Bearer%20API%20key-2563EB)](#request)
[![Cuenta](https://img.shields.io/badge/cuenta-crear%20gratis-0A66C2)](https://patente.ar/registro)
[![Playground](https://img.shields.io/badge/playground-probar%20API-7C3AED)](https://patente.ar/desarrolladores/api?tab=playground)
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

## Activar API y probar en Playground

Para probar API recall vehicular sin armar un backend desde cero, crea una cuenta en patente.ar, pedi habilitar la API `recall` y usa el Playground para ejecutar requests con API keys, payloads de ejemplo, idempotencia, webhooks y logs.

| Paso | Link | Que hacer |
| --- | --- | --- |
| 1 | [Crear cuenta en patente.ar](https://patente.ar/registro) | Registrar la cuenta de empresa o equipo que va a consumir la API. |
| 2 | [Pedir habilitacion de la API](https://patente.ar/contacto?asunto=Habilitar%20API%20recall) | Solicitar que activen el producto `recall` y el esquema de creditos. |
| 3 | [Abrir el Playground](https://patente.ar/desarrolladores/api?tab=playground) | Probar payloads reales de integracion, revisar respuestas y validar webhooks sin publicar credenciales. |
| 4 | [Pasar a produccion](https://patente.ar/api-recall) | Configurar API keys, webhook firmado, idempotencia y trazabilidad por `requestId`. |

El Playground requiere iniciar sesion y tener el modulo API habilitado para la cuenta. Si todavia no aparece, pedi la habilitacion desde el link anterior.


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
- Crear cuenta: [https://patente.ar/registro](https://patente.ar/registro)
- Habilitar API: [https://patente.ar/contacto?asunto=Habilitar%20API%20recall](https://patente.ar/contacto?asunto=Habilitar%20API%20recall)
- Playground: [https://patente.ar/desarrolladores/api?tab=playground](https://patente.ar/desarrolladores/api?tab=playground)
- Sitio principal: [https://patente.ar](https://patente.ar)
- Paginas por jurisdiccion: [jurisdicciones](./jurisdicciones/)
- Repositorio: [https://github.com/patente-ar/api-recall-argentina](https://github.com/patente-ar/api-recall-argentina)
