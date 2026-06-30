# Backstage files

The generated repository contains specific files for integration into Backstage. All these files are located in the /`backstage` folder.

## Service

The `service/catalog-info.yaml` file is useful for the backstage application. It allows you to add a new service component corresponding to this capability in the catalog.

## Provided APIs

The `provided-apis/catalog-info.yaml` and the `provided-apis/openapi.yaml` files are used to add a new API in the backstage catalog. This is the API provided by the new service.

The `provided-apis/openapi.yaml` file is **generated** from `${{ values.name }}.ikanos.yml` — do not edit it by hand. It is kept in sync automatically (see _Automatic OpenAPI synchronization_ below).

## Automatic OpenAPI synchronization

The repository ships a GitHub Actions workflow at `.github/workflows/sync-openapi.yaml`.

Whenever `${{ values.name }}.ikanos.yml` is modified on the `main` branch, the workflow:

1. downloads the Ikanos CLI,
2. runs `ikanos export openapi ${{ values.name }}.ikanos.yml --output backstage/provided-apis/openapi.yaml`,
3. commits the regenerated `backstage/provided-apis/openapi.yaml` back to `main` (only if it changed).

Backstage then re-reads the updated spec on its next catalog refresh, so the **API** component stays in sync with the capability — no manual action required.

!!! note
    The commit is made by `github-actions[bot]`; the workflow skips its own commits to avoid an infinite loop. Pushing to `main` requires the default `GITHUB_TOKEN` write permission, which the workflow declares explicitly. If `main` is protected and rejects bot pushes, change the commit strategy to open a pull request instead.