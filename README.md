<!--
SPDX-License-Identifier: CC0-1.0
SPDX-FileCopyrightText: 2025 OpenRail Association AISBL
-->

# Renovate Config Presets

![OpenRail Administrative Project](https://openrailassociation.org/badges/openrail-project-admin.svg)

This repository contains re-usable configuration options for [Renovate Bot](https://renovatebot.com) which we use in some repository to update package dependencies.

## Usage

To make a repo use Renovate Bot with this config, the following steps are recommended:

### 1. Add renovate configuration

Add a file `renovate.json5` to your repo which at least contains the following:

```json5
// SPDX-License-Identifier: CC0-1.0
// SPDX-FileCopyrightText: 2025 OpenRail Association AISBL
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>OpenRailAssociation/renovate-config"],
}
```

This will use the configuration from [`default.json`](default.json) which we consider to be a sane baseline.

We also have other presets which you may use, e.g. [`rangestrategy-pin.json`](rangestrategy-pin.json), which in turn in based on the default. To use this, make your `renovate.json5` look like this:

```json5
// SPDX-License-Identifier: CC0-1.0
// SPDX-FileCopyrightText: 2025 OpenRail Association AISBL
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>OpenRailAssociation/renovate-config:rangestrategy-pin"],
}
```

Of course, you can also add your [own configuration](https://docs.renovatebot.com/configuration-options/) to your file.


### 2. Enable the Renovate GitHub App for this repo

This can be done from the [GitHub organization admin view](https://github.com/organizations/OpenRailAssociation/settings/installations), as we have installed the app inside the whole organization but only for select repositories.

There, find the "Renovate" app, press "Configure" and add your repository under the headline "Repository access".

## License and Copyright

The renovate configuration files are licensed under [CC0-1.0](https://creativecommons.org/public-domain/cc0/).

There are files in this repository under different licenses. As this repository is [REUSE](https://reuse.software) compliant, all required information is transparent.
