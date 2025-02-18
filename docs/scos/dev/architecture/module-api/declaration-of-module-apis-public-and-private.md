---
title: "Declaration of module APIs: Public and private"
description: This document declares what public and private APIs are
last_updated: Sep 27, 2021
originalLink: https://documentation.spryker.com/2021080/docs/definition-api
originalArticleId: d86471b1-719e-4ab5-b5eb-b5e915f0a837
template: concept-topic-template
redirect_from:
  - /2021080/docs/definition-api
  - /2021080/docs/en/definition-api
  - /docs/definition-api
  - /docs/en/definition-api
  - /v6/docs/definition-api
  - /v6/docs/en/definition-api
  - /v5/docs/definition-api
  - /v5/docs/en/definition-api
  - /v4/docs/definition-api
  - /v4/docs/en/definition-api
  - /v3/docs/definition-api
  - /v3/docs/en/definition-api
  - /v2/docs/definition-api
  - /v2/docs/en/definition-api
  - /v1/docs/definition-api
  - /v1/docs/en/definition-api
  - /docs/scos/dev/architecture/module-api/definition-of-module-api.html
---

According to [Semantic Versioning](http://semver.org/), we release a major version of a module when there are backward compatibility(BC) breaking changes in the Public API. This document declares what public and private APIs are.

## Public API

In the Spryker Commerce OS’s core, the following is the public API:

* Public methods in these locatable classes:
    * [Facades](/docs/scos/dev/back-end-development/zed/business-layer/facade/facade.html)
    * [Clients](/docs/scos/dev/back-end-development/client/client.html)
    * [Query Containers](/docs/scos/dev/back-end-development/zed/persistence-layer/query-container/query-container.html)
    * [Services](/docs/scos/dev/back-end-development/messages-and-errors/registering-a-new-service.html)

* Interfaces:
    * Plugin interfaces
    * Plugins

* Other classes:
    * module Config [`Client/Yves/Zed/Shared/Service`](/docs/scos/dev/back-end-development/data-manipulation/configuration-management.html)
    * Controllers
    * Twig functions
    * [CLI commands](/docs/scos/dev/back-end-development/console-commands/implementing-a-new-console-command.html)
    * Public constants that define environment configuration in [Constant Interfaces](/docs/scos/dev/back-end-development/data-manipulation/configuration-management.html)
* [Database](/docs/scos/dev/back-end-development/zed/persistence-layer/database-schema-definition.html)
* Search
* [Storage](/docs/scos/dev/back-end-development/client/using-and-configuring-redis-as-a-key-value-storage.html)
* [Transfer objects](/docs/scos/dev/back-end-development/data-manipulation/data-ingestion/structural-preparations/creating-using-and-extending-the-transfer-objects.html)
* Dependencies to open source components
* Glossary keys
* Software design



### BC breaking changes

There are several classes and files which are part of the public API, but not every change in the file  causes a BC break. In general, there is a BC break whenever an existing contract is changed. A contract is what the user of the API expects. This includes the signature of methods as well as the expected behavior. For this reason, we have added an ApiDoc to the most used APIs like facades and plugin interfaces.

We always try to avoid BC breaking changes and reduce the effort needed to upgrade a module to a new version. There are several ways to add functionality to APIs without a BC break. So it is possible to add new methods and even parameters to the existing methods as long as they are optional.


## Private API

The *public API* term is introduced by Semantic Versioning. To refer to everything that is not part of the public API in Spryker Commerce OS, we introduced a *private API*.
