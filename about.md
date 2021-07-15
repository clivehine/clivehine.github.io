---
layout: page
title: About
permalink: /about/
---

This is the base Jekyll theme. You can find out more info about customizing your Jekyll theme, as well as basic Jekyll usage documentation at [jekyllrb.com](https://jekyllrb.com/)


----
You can find the source code for Minima at GitHub:
[jekyll](jekyll-organization) /
[minima](https://github.com/jekyll/minima)

You can find the source code for Jekyll at GitHub:
[jekyll](jekyll-organization) /
[jekyll](https://github.com/jekyll/jekyll)

----
[~~jekyll-organization~~ Double tagged to strikethru ;)](https://github.com/jekyll)

| Effect        | Format          |   |   |   |
|---------------|-----------------|---|---|---|
| strikethrough | ~strikethrough~ |   |   |   |
| bold          | __bold__        |   |   |   |
| italics       | _italics_       |   |   |   |
|               |                 |   |   |   |

### PowerShell example below:

<details>
  <summary><em><strong>Expand code block</strong></em></summary>

```powershell
# Clone repo that contains the Graph API and ToolKit functions
git clone --branch main --single-branch https://github.com/wesley-trust/GraphAPI.git
git clone --branch main --single-branch https://github.com/wesley-trust/ToolKit.git

# Dot source function into memory
. .\GraphAPI\Public\AzureAD\Groups\Pipeline\Invoke-WTApplyAzureADGroup.ps1

# Define Variables
$ClientID = "sdg23497-sd82-983s-sdf23-dsf234kafs24"
$ClientSecret = "khsdfhbdfg723498345_sdfkjbdf~-SDFFG1"
$TenantDomain = "wesleytrustsandbox.onmicrosoft.com"
$AccessToken = "HWYLAqz6PipzzdtPwRnSN0Socozs2lZ7nsFky90UlDGTmaZY1foVojTUqFgm1vw0iBslogoP"

# Example groups (mailNickName if missing, is auto-generated upon creation)
$RemoveGroup = [PSCustomObject]@{
    id              = "41fd3497-52hq-983s-sdf23-dsf234kafs24"
    displayName     = "This group will be removed"
    mailEnabled     = $false
    securityEnabled = $true
}
$UpdateGroup = [PSCustomObject]@{
    id              = "52bf4497-f2g7-983s-sdf23-dsf234kafs24"
    displayName     = "This group will be updated"
    mailEnabled     = $false
    securityEnabled = $true
}
$CreateGroup = [PSCustomObject]@{
    displayName     = "This group will be created"
    mailEnabled     = $false
    securityEnabled = $true
}

# Build plan object
$PlanAzureADGroup = [PSCustomObject]@{
    RemoveGroups = $RemoveGroup
    UpdateGroups = $UpdateGroup
    CreateGroups = $CreateGroup
}

# Create hashtable
$Parameters = @{
  ClientID             = $ClientID
  ClientSecret         = $ClientSecret
  TenantDomain         = $TenantDomain
  UpdateExistingGroups = $true
  AzureADGroup         = $PlanAzureADGroup
}

# Apply a plan, splatting the hashtable of parameters
Invoke-WTApplyAzureADGroup @Parameters

# Or pipe specific object definitions to the apply function, with an access token previously obtained
$PlanAzureADGroup | Invoke-WTApplyAzureADGroup -AccessToken $AccessToken

# Or specify each parameter individually, with an access token previously obtained
Invoke-WTApplyAzureADGroup -AzureADGroup $PlanAzureADGroup -AccessToken $AccessToken -UpdateExistingGroups
```

</details>