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

- **Developer** > **Secrets** > **Create** > **Key/value secret**
  - Secret name: `eshop-secret`
  - Add the following values:
    - **Key**: `ConnectionStrings`
    - **Value**: `Server=sql-server,1433;Integrated Security=False;Initial Catalog=eShop;User Id=eShop;Password=R3dH4t1!;Trusted_Connection=false;Encrypt=false`
  - Click **Create**

- **Developer** > **ConfigMap** > **Create ConfigMap**
  - Secret name: `eshop-config`
  - Add the following values:
    - **Key**: `apiBase`
    - **Value**: `https://<API_HOSTNAME>/api/` (replace **API_HOSTNAME** with the hostname of the **eshop-api** Route)
    - **Key**: `webBase`
    - **Value**: `https://<WEB_HOSTNAME>/` (replace **WEB_HOSTNAME** with the hostname of the **eshop-web** Route)
  - Click **Create**

- **Developer** > **Topology**
  - Click on **eshop-web**
  - Next to the **eshop-web** title, click **Action**
  - Select **Edit Deployment**
  - TODO
