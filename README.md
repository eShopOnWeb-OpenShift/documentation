# Demo Scenario

## Source to Image .NET

- Create a new project named `eshoponweb`
- **Developer** > **+ Add** >  **Import from Git**

  - Git Repo URL: `https://github.com/eShopOnWeb-OpenShift/eShopOnWeb`
  - Click **Edit Import Strategy** and choose **Builder Image**
  - Pick **.NET**
  - Application Name: `eshoponweb`
  - Name: `eshop-web`
  - Click **Build Configuration**
  - Add an **Environment Variable**:
    - Name: `DOTNET_STARTUP_PROJECT`
    - Value: `src/Web/Web.csproj`
  - Click **Create**

- **Developer** > **+ Add** >  **Import from Git**

  - Git Repo URL: `https://github.com/eShopOnWeb-OpenShift/eShopOnWeb`
  - Click **Edit Import Strategy** and choose **Builder Image**
  - Pick **.NET**
  - Application Name: `eshoponweb`
  - Name: `eshop-api`
  - Click **Build Configuration**
  - Add an **Environment Variable**:
    - Name: `DOTNET_STARTUP_PROJECT`
    - Value: `src/PublicApi/PublicApi.csproj`
  - Click **Create**
