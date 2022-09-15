---
title: Teams PowerShell 模組中的應用程式型驗證
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 瞭解用於管理 Microsoft Teams 的 Teams PowerShell 模組中的應用程式型驗證。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ea836225658292c312490704305261210ba0991c
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732778"
---
# <a name="application-based-authentication-in-teams-powershell-module"></a>Teams PowerShell 模組中的應用程式型驗證

Teams PowerShell 模組現在支援在預覽版本 4.7.1 或更新版本中使用一組限定 Cmdlet 的應用程式型驗證。 此驗證模式目前僅在商業環境中受到支援。 對於已經或先前已在 商務用 Skype Online 中啟用地區託管會議的客戶，不支援此功能。


## <a name="cmdlets-supported"></a>支援 Cmdlet

所有非 \* Cs Cmdlet (例如 Get-Team) 、Get-CsTenant、Get-CsOnlineUser & Get-CsOnlineVoiceUser 都已受到支援。 其他 Cmdlet 將會逐漸推出。 


## <a name="examples"></a>範例

下列範例說明如何搭配 Azure AD 應用程式型驗證使用 Teams PowerShell 模組： 

- 使用憑證縮圖連線：

  ```powershell
  Connect-MicrosoftTeams -CertificateThumbprint "XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX" -ApplicationId "00000000-0000-0000-0000-000000000000" -TenantId "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"
  ```
  當您使用 CertificateThumbprint 參數時，憑證必須安裝在您執行命令的電腦上。 憑證應該會安裝在使用者憑證存放區中。
  
- 使用 Access Token 連線：
  
  存取權杖可透過 login.microsoftonline.com 端點擷取。 它需要兩個 Access Token – 「MS Graph」 和 「Skype 和 Teams 租使用者管理員 API」 資源。

  ```powershell
  $ClientSecret   = "…"
  $ApplicationID = "00000000-0000-0000-0000-000000000000"
  $TenantID = "YYYYYYYY-YYYY-YYYY-YYYY-YYYYYYYYYYYY"

  $graphtokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "https://graph.microsoft.com/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret   
  }  

  $graphToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $graphtokenBody | Select-Object -ExpandProperty Access_Token 

  $teamstokenBody = @{   
     Grant_Type    = "client_credentials"   
     Scope         = "48ac35b8-9aa8-4d74-927d-1f4a14a0b239/.default"   
     Client_Id     = $ApplicationID   
     Client_Secret = $ClientSecret 
  } 

  $teamsToken = Invoke-RestMethod -Uri "https://login.microsoftonline.com/$TenantID/oauth2/v2.0/token" -Method POST -Body $teamstokenBody | Select-Object -ExpandProperty Access_Token 

  Connect-MicrosoftTeams -AccessTokens @("$graphToken", "$teamsToken")
  ```
  
## <a name="how-does-it-work"></a>它的運作方式為何？

Teams PowerShell 模組會使用應用程式識別碼、租使用者識別碼和憑證縮圖來擷取應用程式型權杖。 在 Azure AD 內布建的應用程式物件已指派目錄角色給該物件，該角色會在存取權杖中傳回。 會話的角色型存取控制 (RBAC) 是使用 token 中提供的目錄角色資訊來設定。


## <a name="setup-application-based-authentication"></a>設定應用程式型驗證

使用應用程式物件進行驗證時需要初始上線。 應用程式與服務主體會交替使用，但應用程式就像是類別物件，而服務主體就像是類別的實例。 您可以在 [Azure Active Directory 中的應用程式與服務主體物件](/azure/active-directory/develop/app-objects-and-service-principals)深入瞭解這些物件。

下方提及在 Azure Ad 中建立應用程式的高層級步驟，以取得詳細步驟，請參閱 [本文](/azure/active-directory/develop/howto-create-service-principal-portal)。
  1. 在 Azure AD 中註冊應用程式
  2. 產生自我簽署憑證
  3. 將憑證附加至 Azure AD 應用程式
  4. 指派 Azure AD 角色給應用程式

應用程式需要指派適當的 RBAC 角色。 由於應用程式是在 Azure AD 中布建，因此您可以使用任何支援的內建角色。
 
