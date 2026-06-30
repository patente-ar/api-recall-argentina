# Repo profile: api-recall-argentina

## GitHub creation settings

- Owner: patente-ar
- Repository name: api-recall-argentina
- Visibility: Public
- Add README: yes
- .gitignore: Node
- License: MIT License
- Homepage: https://patente.ar/api-recall
- Description: Ejemplos de integracion para consultar campanas de recall por VIN con la API de patente.ar.

## Topics

api, argentina, recall, vin, automotor, seguridad-vial, webhooks, openapi

## SEO positioning

- Primary keyword: API recall vehicular
- Secondary keywords: API de recall vehicular en Argentina, recall, API vehicular Argentina, API patente argentina
- Canonical commercial page: https://patente.ar/api-recall
- Public informational page: https://patente.ar/campanas-recall
- Brand/entity link: https://patente.ar

## Repository features

- Enable Issues for integration questions.
- Enable Discussions only if there is time to moderate.
- Enable GitHub Pages from the `docs/` folder on `main`.
- Pin this repo on the GitHub profile after the README is published.
- Keep default branch as `main`.

## GitHub API metadata command

```bash
GH_TOKEN="$(security find-generic-password -a patente-ar -s codex-github:doc-apis-github -w)"
gh repo edit patente-ar/api-recall-argentina \
  --description "Ejemplos de integracion para consultar campanas de recall por VIN con la API de patente.ar." \
  --homepage "https://patente.ar/api-recall" \
  --enable-issues=true
gh repo edit patente-ar/api-recall-argentina --add-topic "api,argentina,recall,vin,automotor,seguridad-vial,webhooks,openapi"
```
