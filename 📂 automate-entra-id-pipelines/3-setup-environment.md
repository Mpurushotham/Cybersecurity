# Environment Setup

## 1. Register Application in Entra ID
```powershell
Connect-AzureAD
New-AzureADApplication -DisplayName "Pipeline-App" | New-AzureADServicePrincipal
