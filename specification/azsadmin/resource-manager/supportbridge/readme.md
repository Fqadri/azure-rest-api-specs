# Support Bridge Service

> see https://aka.ms/autorest

This is the AutoRest configuration file for Support Bridge Service

---
## Getting Started
To build the SDK for Support Bridge Service, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration

### Basic Information
These are the global settings for the Support Bridge Service API.

``` yaml
title: SupportBridgeAdminClient
description: Support Bridge Admin Client
openapi-type: arm
tag: package-2018-12-01
```

## Suppression
``` yaml

directive:
  - suppress: TrackedResourceListByResourceGroup
    reason: This tracked resource is exposed as a nested resource under Region. Region is an internal AzS Admin RP requirement that is created and managed during deployment. Without exposing region resource list for RG path will not appear valid. Hence, this operation will not be needed in SDK.

  - suppress: TrackedResourceListBySubscription
    reason: AzS Admin RP (Admin namespace) works with single subscription only. 

```


### Tag: package-2018-12-01

These settings apply only when `--tag=package-2018-12-01` is specified on the command line.

``` yaml $(tag) == 'package-2018-12-01'
input-file:
    - "Microsoft.SupportBridge.Admin/preview/2018-12-01/LogCollection.json"
```

---
# Code Generation

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.AzureStack.Management.SupportBridge.Admin
  payload-flattening-threshold: 1
  output-folder: $(csharp-sdks-folder)/Generated
  clear-output-folder: true
```
