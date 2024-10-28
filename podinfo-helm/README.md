# Sample

## Description

This folder contains a component that has a HelmChart based Resource in it.
It also contains a Localization object and a Resource.

The localization config object can be found in `localization-config.yaml` file.

This file describes how a configuration will happen. Where the configured object is and
what file to look for.

We fetch this config object and configure the `manifests-resource.yaml` object with it.

The ocm-controller objects are defined in `localized-resource.yaml`, `repository-object.yaml` and
`component-object.yaml`.

Once this is done, we create a `HelmRelease` in `helm_release.yaml`. This object will
point to the Localized resource object. Flux will fetch the linked Artifact and deploy
the localized resources within.

## Building the Component

Create a transfer archive:

```
ocm add componentversions --create components.yaml
```

Transport it to the targeted repository:

```
ocm transfer component ./transport-archive ghcr.io/open-component-model/ocm-demo-localized
```
