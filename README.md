# 📦 Gitlab include for Sonarqube Scan and Quality Gate — `sonarqube-template-include`

This Gitlab include Scan and rate a Quality Gate from project.

## ✨ Supported Project Types

This template officially supports the following project ecosystems:

- **`dotnet`**: For .NET and .NET Core projects (`.csproj` or `.sln`).
- **`node`**: For any JavaScript/TypeScript project that uses npm (`package.json`), including frontend (React, Vue, Angular) and backend (Node.js) applications.


## Requirements

This include needs tags on your runners named "amd64" because de architecture is amd64(x86) on Sonarqube CLI and Docker Image base used

## 🔧 Inputs

| Input | Description | Default | Required |
|---|---|---|---|
| `stage` | The GitLab CI/CD stage where the SonarQube job will run. | `sonarqube` | No |
| `language` | The project type to be scanned. Accepted values: `dotnet`, `node`. | - | **Yes** |
| `dotnet_version` | The .NET SDK version to use for the analysis. | `8.0` | Only for `dotnet` |
| `dotnet_path_sln_or_csproj` | The relative path to your `.sln` or `.csproj` file. | - | **Yes**, for `dotnet` |

### If your project is .NET, really necessary inputs:

- **`dotnet_version`**: .NET version utilized in csproj or sln file.
- **`dotnet_path_sln_or_csproj`**: Path to .csproj or .sln file in your project.

## 🚀 How to Use

Add the following to your `.gitlab-ci.yml` file.

### For .NET Projects

```yaml
include:
- remote: 'https://raw.githubusercontent.com/Tooark/sonarqube-template-include/main/.gitlab-ci.yml'
  inputs:
    language: "dotnet"
    dotnet_version: "9.0"
    dotnet_path_sln_or_csproj: "./src/my-project.sln" # or my-project.csproj
```

### For JavaScript/TypeScript (Node.js) Projects

```yaml
include:
- remote: 'https://raw.githubusercontent.com/Tooark/sonarqube-template-include/main/.gitlab-ci.yml'
  inputs:
    language: "node"
```

## Contribution

Contributions are welcome! Feel free to open issues and pull requests in the [Notification Trigger Url](https://Gitlab.com/Tooark/sonarqube-template-include/issues) repository.

---

## Contributors

The following users are contributing to the project:

| <img src="https://avatars.Gitlabusercontent.com/u/97809060?v=4" width=120> | 
| :-------------------------------------------------------------------------: |
| [**Stenio Ignacio**](https://Gitlab.com/stenioignacio) |