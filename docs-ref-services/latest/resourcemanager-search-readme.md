---
title: Azure Resource Manager Azure AI Search client library for Java
keywords: Azure, java, SDK, API, azure-resourcemanager-search, cognitive-search
ms.date: 12/22/2023
ms.topic: reference
ms.devlang: java
ms.service: cognitive-search
---
# Azure Resource Manager Azure AI Search client library for Java - version 2.34.0 

Azure AI Search (formerly known as "Azure Cognitive Search") is an AI-powered information retrieval platform that helps developers build rich search experiences and generative AI apps that combine large language models with enterprise data.

This library supports managing Microsoft Azure AI Search resources using the Azure SDK for Java.

Although Azure AI Search is renamed, many API descriptions continue to use the former name, "Azure Cognitive Search". API string descriptions will get updated over time.

For documentation on how to use this package, please see [Azure Management Libraries for Java](https://aka.ms/azsdk/java/mgmt).

## Getting started

### Prerequisites

- [Java Development Kit (JDK)][jdk] with version 8 or above
- [Azure Subscription][azure_subscription]

### Adding the package to your product

[//]: # ({x-version-update-start;com.azure.resourcemanager:azure-resourcemanager-search;current})
```xml
<dependency>
    <groupId>com.azure.resourcemanager</groupId>
    <artifactId>azure-resourcemanager-search</artifactId>
    <version>2.34.0</version>
</dependency>
```
[//]: # ({x-version-update-end})

### Include the recommended packages

Azure Management Libraries require a `TokenCredential` implementation for authentication and an `HttpClient` implementation for HTTP client.

[Azure Identity][azure_identity] package and [Azure Core Netty HTTP][azure_core_http_netty] package provide the default implementation.

### Authentication

By default, Microsoft Entra ID token authentication depends on correct configure of following environment variables.

- `AZURE_CLIENT_ID` for Azure client ID.
- `AZURE_TENANT_ID` for Azure tenant ID.
- `AZURE_CLIENT_SECRET` or `AZURE_CLIENT_CERTIFICATE_PATH` for client secret or client certificate.

In addition, Azure subscription ID can be configured via environment variable `AZURE_SUBSCRIPTION_ID`.

With above configuration, `azure` client can be authenticated by following code:

```java readme-sample-authenticate
AzureProfile profile = new AzureProfile(AzureEnvironment.AZURE);
TokenCredential credential = new DefaultAzureCredentialBuilder()
    .authorityHost(profile.getEnvironment().getActiveDirectoryEndpoint())
    .build();
SearchServiceManager manager = SearchServiceManager
    .authenticate(credential, profile);
```

The sample code assumes global Azure. Please change `AzureEnvironment.AZURE` variable if otherwise.

See [Authentication][authenticate] for more options.

## Key concepts

See [API design][design] for general introduction on design and key concepts on Azure Management Libraries.

## Examples

See [Samples][sample] for code snippets and samples.

## Troubleshooting

## Next steps

## Contributing

For details on contributing to this repository, see the [contributing guide](https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/CONTRIBUTING.md).

1. Fork it
1. Create your feature branch (`git checkout -b my-new-feature`)
1. Commit your changes (`git commit -am 'Add some feature'`)
1. Push to the branch (`git push origin my-new-feature`)
1. Create new Pull Request

<!-- LINKS -->
[jdk]: https://learn.microsoft.com/azure/developer/java/fundamentals/
[azure_subscription]: https://azure.microsoft.com/free/
[azure_identity]: https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/sdk/identity/azure-identity
[azure_core_http_netty]: https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/sdk/core/azure-core-http-netty
[authenticate]: https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/sdk/resourcemanager/docs/AUTH.md
[sample]: https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/sdk/resourcemanager/docs/SAMPLE.md
[design]: https://github.com/Azure/azure-sdk-for-java/blob/azure-resourcemanager-search_2.34.0/sdk/resourcemanager/docs/DESIGN.md

