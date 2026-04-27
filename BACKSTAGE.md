# Backstage Integration

This guide explains how to integrate the Naftiko Capability template into an existing Backstage application.

## Prerequisites

The template uses a custom scaffolder action that relies on the **Naftiko CLI**. It must be installed on the machine running your Backstage backend.

Follow the installation instructions for your platform:
[Naftiko CLI Installation](https://github.com/naftiko/framework/wiki/Installation#cli-tool)

Verify the installation by running:

```bash
naftiko --help
```

## 1. Install the custom scaffolder module

The template depends on a custom scaffolder backend module published to GitHub Packages.

### Configure the GitHub Packages registry

Add the following to the `.yarnrc.yml` file at the root of your Backstage application:

```yaml
npmScopes:
  naftiko:
    npmRegistryServer: "https://npm.pkg.github.com"
    npmAuthToken: "${GITHUB_TOKEN}"
```

Set the `GITHUB_TOKEN` environment variable to a GitHub personal access token with `read:packages` scope. This is required because GitHub Packages does not support anonymous access, even for public packages.

### Install the package

Be sure to be at the root of your backstage application.

```bash
yarn add @naftiko/plugin-scaffolder-backend-module-naftiko@0.0.1-test3
```

### Register the module

In your Backstage backend entry point (typically `packages/backend/src/index.ts`), add:

```ts
backend.add(import('@naftiko/plugin-scaffolder-backend-module-naftiko'));
```

## 2. Register the template in the catalog

The template definition is hosted in the public repository [naftiko/fleet](https://github.com/naftiko/fleet).

Add the following to your `app-config.yaml` under `catalog.locations`:

```yaml
catalog:
  locations:
    - type: url
      target: https://github.com/naftiko/fleet/blob/main/backstage/templates/capability.yml
      rules:
        - allow: [Template]
```

After restarting your Backstage application, the **Naftiko Capability** template will appear in the template catalog. It allows you to create a new capability component by choosing what to expose (MCP, REST, or Agent Skills), then generates and pushes the corresponding configuration to a GitHub repository.
