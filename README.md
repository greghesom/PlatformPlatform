![PlatformPlatform Resource Groups](https://platformplatformgithub.blob.core.windows.net/$root/GitHubTopBanner.png)

<h4 align="center">

[![App Gateway](https://github.com/platformplatform/PlatformPlatform/actions/workflows/app-gateway.yml/badge.svg)](https://github.com/platformplatform/PlatformPlatform/actions/workflows/app-gateway.yml?query=branch%3Amain)
[![Account Management](https://github.com/platformplatform/PlatformPlatform/actions/workflows/account-management.yml/badge.svg)](https://github.com/platformplatform/PlatformPlatform/actions/workflows/account-management.yml?query=branch%3Amain)
[![Back Office](https://github.com/platformplatform/PlatformPlatform/actions/workflows/back-office.yml/badge.svg)](https://github.com/platformplatform/PlatformPlatform/actions/workflows/back-office.yml?query=branch%3Amain)
[![Cloud Infrastructure](https://github.com/platformplatform/PlatformPlatform/actions/workflows/cloud-infrastructure.yml/badge.svg)](https://github.com/platformplatform/PlatformPlatform/actions/workflows/cloud-infrastructure.yml?query=branch%3Amain)

[![GitHub issues with enhancement label](https://img.shields.io/github/issues-raw/platformplatform/PlatformPlatform/enhancement?label=enhancements&logo=github&color=%23A2EEEF)](https://github.com/orgs/PlatformPlatform/projects/1/views/3?filterQuery=-status%3A%22%E2%9C%85+Done%22+label%3Aenhancement)
[![GitHub issues with roadmap label](https://img.shields.io/github/issues-raw/platformplatform/PlatformPlatform/roadmap?label=roadmap&logo=github&color=%23006B75)](https://github.com/orgs/PlatformPlatform/projects/2/views/2?filterQuery=is%3Aopen+label%3Aroadmap)
[![GitHub issues with bug label](https://img.shields.io/github/issues-raw/platformplatform/PlatformPlatform/bug?label=bugs&logo=github&color=red)](https://github.com/platformplatform/PlatformPlatform/issues?q=is%3Aissue+is%3Aopen+label%3Abug)

[![Coverage](https://sonarcloud.io/api/project_badges/measure?project=PlatformPlatform_platformplatform&metric=coverage)](https://sonarcloud.io/component_measures?id=PlatformPlatform_platformplatform&metric=coverage)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=PlatformPlatform_platformplatform&metric=alert_status)](https://sonarcloud.io/summary/overall?id=PlatformPlatform_platformplatform)
[![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=PlatformPlatform_platformplatform&metric=security_rating)](https://sonarcloud.io/component_measures?id=PlatformPlatform_platformplatform&metric=Security)
[![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=PlatformPlatform_platformplatform&metric=reliability_rating)](https://sonarcloud.io/component_measures?id=PlatformPlatform_platformplatform&metric=Reliability)
[![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=PlatformPlatform_platformplatform&metric=sqale_rating)](https://sonarcloud.io/component_measures?id=PlatformPlatform_platformplatform&metric=Maintainability)

</h4>

# 👋 Welcome to PlatformPlatform

Kick-start building top-tier B2B & B2C cloud SaaS products with sleek design, fully localized and accessible, vertical slice architecture, automated and fast DevOps, and top-notch security.

Built to demonstrate seamless flow—backend contracts feed a fully-typed React UI, pipelines make fully automated deployments to Azure, and AI guardrails keep the codebase tidy—think of it as a ready-made blueprint, not a pile of parts to assemble.

## What's inside

* **Backend** - .NET 9 and C# adhering to the principles of vertical slice architecture, DDD, CQRS, and clean code
* **Frontend** – React 19, TypeScript, TanStack Router & Query, React Aria for accessible and UI
* **CI/CD** - GitHub actions for fast passwordless deployments of docker containers and infrastructure (Bicep)
* **Infrastructure** - Cost efficient and scalable Azure PaaS services like Azure Container Apps, Azure SQL, etc.
* **Developer CLI** - Extendable .NET CLI for DevEx - set up CI/CD is one command and a couple of questions
* **AI rules** – 30+ rules & workflows that guide AI tools to generate consistent, production-ready code

Still in alpha state, follow our [up-to-date roadmap](https://github.com/orgs/PlatformPlatform/projects/2/views/2) with core SaaS features like SSO, user management, telemetry, monitoring, alerts, multi-region, feature flags, back office for support, etc.

Show your support for our project – Give us a star on GitHub! It truly means a lot! ⭐

# Getting Started 1-2-3

TL;DR: Open the [PlatformPlatform](./application/PlatformPlatform.slnx) solution in Rider or Visual Studio and run the [Aspire AppHost](./application/AppHost/AppHost.csproj) project.

### Prerequisites

For development, you need .NET, Docker, and Node. And GitHub and Azure CLI for setting up CI/CD.

<details>

<summary>Install prerequisites for Windows</summary>
	
1.	Open a PowerShell terminal as Administrator and run the following command to install Windows Subsystem for Linux (required for Docker). Restart your computer if prompted.
  
    ```powershell
    wsl --install
    ```

2.	From an Administrator PowerShell terminal, use [winget](https://learn.microsoft.com/en-us/windows/package-manager/winget/) (preinstalled on Windows 11) to install any missing packages:

    ```powershell
    winget install Microsoft.DotNet.SDK.9
    winget install Git.Git
    winget install Docker.DockerDesktop
    winget install OpenJS.NodeJS
    winget install Microsoft.AzureCLI
    winget install GitHub.cli
    ```

</details>

<details>

<summary>Install prerequisites for Mac</summary>

Open a terminal and run the following commands (if not installed):

- Install [Homebrew](https://brew.sh/), a package manager for Mac
- `brew install --cask dotnet-sdk`
- `brew install --cask docker`
- `brew install git node azure-cli gh`

</details>

<details>

<summary>Install prerequisites for Linux/WSL2</summary>

Open a terminal and run the following commands (if not installed):

- Install Wget

  ```bash
  sudo apt update && sudo apt-get install wget -y
  ```

- Install Microsoft repository

  ```bash
  source /etc/os-release
  wget https://packages.microsoft.com/config/$ID/$VERSION_ID/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
  sudo dpkg -i packages-microsoft-prod.deb
  rm packages-microsoft-prod.deb
  ```

- Install Node repository

  ```bash
  curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
  ```

- Install GitHub Package repository

  ```bash
  (type -p wget >/dev/null || (sudo apt update && sudo apt-get install wget -y)) \
  && sudo mkdir -p -m 755 /etc/apt/keyrings \
  && wget -qO- https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo tee /etc/apt/keyrings/githubcli-archive-keyring.gpg > /dev/null \
  && sudo chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
  && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
  ```

- Update packages

  ```bash
  sudo apt-get update
  ```

- Install .NET SDK 9.0, Node, GitHub CLI

  ```bash
  sudo apt-get install -y dotnet-sdk-9.0 nodejs gh
  ```

- Install Azure CLI

  ```bash
  curl -sL https://aka.ms/InstallAzureCLIDeb | sudo bash
  ```

- Install Certificate
  ```bash
  dotnet tool update -g linux-dev-certs
  dotnet linux-dev-certs install
  ```

- Trust Certificates

  ```bash
  cd /usr/local/share/ca-certificates/aspnet-dev-{Environment.UserName}.crt && explorer.exe .
  # Install self signed root certificate

  # Open the windows certificate manager and import root certificate
  # "\\wsl.localhost\Ubuntu-20.04\home\maximus\.aspnet\dev-certs\https\platformplatform.pfx"
  ```

</details>

## 1. Clone the repository

We recommend you keep the commit history, which serves as a great learning and troubleshooting resource. 😃

## 2. Run the Aspire AppHost to spin up everything on localhost

Using .NET Aspire, docker images with SQL Server, Blob Storage emulator, and development mail server will be downloaded and started. No need install anything, or learn complicated commands. Simply run this command, and everything just works 🎉

```bash
cd application/AppHost
dotnet run # First time downloading Docker containers will take several minutes
```

Alternatively, open the [PlatformPlatform](./application/PlatformPlatform.slnx) solution in Rider or Visual Studio and run the [Aspire AppHost](./application/AppHost/AppHost.csproj) project.

Once the Aspire dashboard fully loads, click to the WebApp and sign up for a new account (https://localhost:9000/signup). A one-time password (OTP) will be sent to the development mail server, but for local development, you can always use the code `UNLOCK` instead of checking the mail server. As shown here:

<img src="https://platformplatformgithub.blob.core.windows.net/$root/local-development-exp.gif" alt="Getting Started" title="Developer Experience" width="800"/>

## 3. Set up CI/CD with passwordless deployments from GitHub to Azure

Run this command to automate Azure Subscription configuration and set up [GitHub Workflows](https://github.com/platformplatform/PlatformPlatform/actions) for deploying [Azure Infrastructure](./cloud-infrastructure) (using Bicep) and compiling [application code](./application) to Docker images deployed to Azure Container Apps:

```bash
cd developer-cli
dotnet run configure-continuous-deployments # Tip: Add --verbose-logging to show the used CLI commands
```

You need to be the owner of the GitHub repository and the Azure Subscription, plus have permissions to create Service Principals and Active Directory Groups.

The command will first prompt you to login to Azure and GitHub, and collect information. You will be presented with a complete list of changes before they are applied. It will look something like this:

![Configure Continuous Deployments](https://platformplatformgithub.blob.core.windows.net/$root/ConfigureContinuousDeployments.png)

Except for adding a DNS record, everything is fully automated. After successful setup, the command will provide simple instructions on how to configure branch policies, Sonar Cloud static code analysis, and more.

The infrastructure is configured with auto-scaling and hosting costs in focus. It will cost less than 2 USD per day for a cluster, and it will allow scaling to millions of users 🎉

![Azure Costs](https://platformplatformgithub.blob.core.windows.net/$root/azure-costs-center.png)

# Inside Our Monorepo

PlatformPlatform is a [monorepo](https://en.wikipedia.org/wiki/Monorepo) containing all application code, infrastructure, tools, libraries, documentation, etc. A monorepo is a powerful way to organize a codebase, used by Google, Facebook, Uber, Microsoft, etc.

```bash
.
├─ .cursor               # AI Rules for Cursor AI editor, and documentation for developers
├─ .github               # Separate GitHub workflows for deploying Infrastructure and app
├─ .windsurf             # Copy of .cursor for Windsurf AI editor (synchronized by CLI)
├─ application           # Contains the application source code
│  ├─ AppHost            # .NET Aspire project starting app and all dependencies in Docker
│  ├─ AppGateway         # Main entry point for the app using YARP as a reverse proxy 
│  ├─ account-management # Self-contained system with account sign-up, user management, etc.
│  │   ├─ WebApp         # React SPA frontend using TypeScript and React Aria Components
│  │   ├─ Api            # Presentation layer exposing the API to WebApp or other clients
│  │   ├─ Core           # Core business logic, application use cases, and infrastructure
│  │   ├─ Workers        # Background workers for long-running tasks and event processing
│  │   └─ Tests          # Tests for the Api, Core, and Workers
│  ├─ back-office        # A self-contained system for operations and support (empty for now)
│  │   ├─ WebApp         # React SPA frontend using TypeScript and React Aria Components
│  │   ├─ Api            # Presentation layer exposing the API to WebApp or other clients
│  │   ├─ Core           # Core business logic, application use cases, and infrastructure
│  │   ├─ Workers        # Background workers for long-running tasks and event processing
│  │   └─ Tests          # Tests for the Api, Core, and Workers
│  ├─ shared-kernel      # Reusable components and default configuration for all systems
│  ├─ shared-webapp      # Reusable and styled React Aria Components that affect all systems 
│  └─ [your-scs]         # [Your SCS] Create your SaaS product as a self-contained system
├─ cloud-infrastructure  # Contains Bash and Bicep scripts (IaC) for Azure resources
│  ├─ cluster            # Scale units like production-west-eu, production-east-us, etc.
│  ├─ environment        # Shared resources like App Insights, Container Registry, etc.
│  └─ modules            # Reusable Bicep modules like Container App, SQL Server, etc.
└─ development-cli       # A .NET CLI tool for automating common developer tasks
```

** A [Self-Contained System](https://scs-architecture.org/) is a large microservice (or a small monolith) that contains the full stack, including frontend, background jobs, etc. These can be developed, tested, deployed, and scaled in isolation.

# Technologies

### .NET 9 Backend With Vertical Sliced Architecture, DDD, CQRS, Minimal API, and Aspire

The backend is built using the most popular, mature, and commonly used technologies in the .NET ecosystem:

- [.NET 9](https://dotnet.microsoft.com) and [C# 13](https://learn.microsoft.com/en-us/dotnet/csharp/tour-of-csharp)
- [.NET Aspire](https://aka.ms/dotnet-aspire)
- [YARP](https://microsoft.github.io/reverse-proxy)
- [ASP.NET Minimal API](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/minimal-apis)
- [Entity Framework](https://learn.microsoft.com/en-us/ef)
- [MediatR](https://github.com/jbogard/MediatR)
- [FluentValidation](https://fluentvalidation.net)
- [Mapster](https://github.com/MapsterMapper/Mapster)
- [XUnit](https://xunit.net), [FluentAssertions](https://fluentassertions.com), [NSubstitute](https://nsubstitute.github.io), and [Bogus](https://github.com/bchavez/Bogus)
- [SonarCloud](https://sonarcloud.io) and [JetBrains Code style and Cleanup](https://www.jetbrains.com/help/rider/Code_Style_Assistance.html)

<details>

<summary>Read more about the backend architecture</summary>

- **Vertical Slice Architecture**: The codebase is organized around vertical slices, each representing a feature or module, promoting separation of concerns and maintainability.
- **Domain-Driven Design (DDD)**: DDD principles are applied to ensure a clear and expressive domain model.
- **Command Query Responsibility Segregation (CQRS)**: This clearly separates read (query) and write (command) operations, adhering to the single responsibility principle (each action is in a separate command).
- **Screaming architecture**: The architecture is designed with namespaces (folders) per feature, making the concepts easily visible and expressive, rather than organizing the code by types like models and repositories.
- **MediatR pipelines**: MediatR pipeline behaviors are used to ensure consistent handling of cross-cutting concerns like validation, unit of work, and handling of domain events.
- **Strongly Typed IDs**: The codebase uses strongly typed IDs, which are a combination of the entity type and the entity ID. This is even at the outer API layer, and Swagger translates this to the underlying contract. This ensures type safety and consistency across the codebase.
- **JetBrains Code style and Cleanup**: JetBrains Rider/ReSharper is used for code style and automatic cleanup (configured in `.DotSettings`), ensuring consistent code formatting. No need to discuss tabs vs. spaces anymore; Invalid formatting breaks the build.
- **Monolith prepared for self-contained systems**: The codebase is organized into a monolith, but the architecture is prepared for splitting in to self-contained systems. A self-contained system is a large microservice (or a small monolith) that contains the full stack including frontend, background jobs, etc. These can be developed, tested, deployed, and scaled in isolation, making it a good compromise between a large monolith and many small microservices. Unlike the popular backend-for-frontend (BFF) style with one shared frontend, this allows teams to work fully independently.
- **Shared Kernel**: The codebase uses a shared kernel for all the boilerplate code required to build a clean codebase. The shared kernel ensures consistency between self-contained systems, e.g., enforcing tenant isolation, auditing, tracking, implementation of tactical DDD patterns like aggregate, entities, repository base, ID generation, etc.

Although some features like multi-tenancy are not yet implemented, the current implementation serves as a solid foundation for building business logic without unnecessary boilerplate.

</details>

### React 19 Frontend With TypeScript, React Aria Components, and Node

The frontend is built with these technologies:

- [React 19](https://react.dev)
- [TypeScript](https://www.typescriptlang.org)
- [React Aria Components](https://react-spectrum.adobe.com/react-aria/react-aria-components.html)
- [Tanstack Router](https://tanstack.com/router)
- [Tanstack Query](https://tanstack.com/query)
- [Node](https://nodejs.org/en)

### Azure Cloud Infrastructure With Enterprise-Grade Security and Zero Secrets

PlatformPlatform's cloud infrastructure is built using the latest Azure Platform as a Service (PaaS) technologies:

- [Azure Container Apps](https://learn.microsoft.com/en-us/azure/container-apps/overview)
- [Azure SQL](https://azure.microsoft.com/en-us/products/azure-sql)
- [Azure Blob Storage](https://azure.microsoft.com/en-us/services/storage/blobs)
- [Azure Service Bus](https://azure.microsoft.com/en-us/services/service-bus)
- [Azure Key Vault](https://azure.microsoft.com/en-us/services/key-vault)
- [Azure Application Insights](https://azure.microsoft.com/en-us/services/monitor)
- [Azure Log Analytics](https://azure.microsoft.com/en-us/services/monitor)
- [Azure Virtual Network](https://azure.microsoft.com/en-us/services/virtual-network)
- [Azure Managed Identities](https://docs.microsoft.com/en-us/azure/active-directory/lifecyclesmanaged-identities-azure-resources/overview)
- [Azure Container Registry](https://azure.microsoft.com/en-us/products/communication-services/)
- [Azure Communication Services](https://azure.microsoft.com/en-us/products/communication-services/)
- [Microsoft Defender for Cloud](https://azure.microsoft.com/en-us/products/defender-for-cloud)

<details>

<summary>Read more about this enterprise-grade architecture</summary>

- **Platform as a Service (PaaS) technologies**: Azure is the leading Cloud Service Provider (CSP) when it comes to PaaS technologies. PlatformPlatform uses PaaS technologies which are fully managed by Microsoft, as opposed to Infrastructure as a Service (IaaS) technologies where the customer is responsible for the underlying infrastructure. This means that Microsoft is responsible for the availability of the infrastructure, and you are only responsible for the application and data. This makes it possible for even a small team to run a highly scalable, stable, and secure solution.
- **Enterprise-grade security with zero secrets**:
  - **Managed Identities**: No secrets are used when Container Apps connect to e.g. Databases, Blob Storage, and Service Bus. The infrastructure uses Managed Identities for all communication with Azure resources, eliminating the need for secrets.
  - **Federated credentials**: Deployment from GitHub to Azure is done using federated credentials, establishing a trust between the GitHub repository and Azure subscription based on the repository's URL, without the need for secrets.
  - **No secrets expires**: Since no secrets are used, there is no need to rotate secrets, and no risk of secrets expiring.
  - **100% Security Score**: The current infrastructure configuration follows best practices, and the current setup code achieves a 100% Security Score in Microsoft Defender for Cloud. This minimizes the attack surface and protects against even sophisticated attacks.
- **Automatic certificate management**: The infrastructure is configured to automatically request and renew SSL certificates, eliminating the need for manual certificate management.
- **Multiple environments**: The setup includes different environments like Development, Staging, and Production, deployed into clearly named resource groups within a single Azure Subscription.
- **Multi-region**: Spinning up a cluster in a new region is a matter of adding one extra deployment job to the GitHub workflow. This allows customers to select a region where their data is close to the user and local data protection laws like GDPR, CCPA, etc. are followed.
- **Azure Container Apps**: The application is hosted using Azure Container Apps, which is a new service from Azure that provides a fully managed Kubernetes environment for running containerized applications. You don't need to be a Kubernetes expert to run your application in a scalable and secure environment.
- **Scaling from zero to millions of users**: The Azure Container App Environment is configured to scale from zero to millions of users, and the infrastructure is configured to scale automatically based on load. This means the starting costs are very low, and the solution can scale to millions of users without any manual intervention. This enables having Development and Staging environments running with very low costs.
- **Azure SQL**: The database is hosted using Azure SQL Database, which is a fully managed SQL Server instance. SQL Server is known for its high performance, stability, scalability, and security. The server will easily handle millions of users with single-digit millisecond response times.

</details>

# Screenshots

This is how it looks when GitHub workflows has deployed Azure Infrastructure:

![GitHub Environments](https://platformplatformgithub.blob.core.windows.net/GitHubInfrastructureDeployments.png)

These are the resource groups created when deploying one staging cluster, and two production clusters:

![PlatformPlatform Resource Groups](https://platformplatformgithub.blob.core.windows.net/PlatformPlatformResourceGroups.png)

This is the security score after deploying PlatformPlatform resources to Azure. Achieving a 100% security score in Azure Defender for Cloud without exemptions is not trivial.

![Azure Security Recommendations](https://platformplatformgithub.blob.core.windows.net/AzureSecurityRecommendations.png)
