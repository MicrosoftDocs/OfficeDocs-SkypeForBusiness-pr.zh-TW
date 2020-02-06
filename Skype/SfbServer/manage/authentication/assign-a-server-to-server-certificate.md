---
title: 指派伺服器對伺服器驗證憑證至商務用 Skype 伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：指派商務用 Skype Server 的伺服器對伺服器驗證憑證。
ms.openlocfilehash: 4689306e0fb8cd7b7c8ce67f74c6ddb65db44f13
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818855"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>指派伺服器對伺服器驗證憑證至商務用 Skype 伺服器
**摘要：** 指派商務用 Skype Server 的伺服器對伺服器驗證憑證。
  
若要判斷伺服器對伺服器驗證憑證是否已指派給商務用 Skype Server，請從商務用 Skype Server Management Shell 執行下列命令：
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

如果沒有傳回憑證資訊，您必須先指派權杖頒發者憑證，才能使用伺服器對伺服器驗證。 一般來說，任何商務用 Skype 伺服器憑證都可以用來做為您的 OAuthTokenIssuer 憑證;例如，您的商務用 Skype Server 預設憑證也可以用來做為 OAuthTokenIssuer 憑證。 （OAUthTokenIssuer 憑證也可以是任何包含您的 [主旨] 欄位中您 SIP 網功能變數名稱稱的 Web 服務器憑證）。伺服器與伺服器驗證所用之憑證的主要兩個需求如下：1）必須在所有前端伺服器上將相同的憑證設定為 OAuthTokenIssuer 憑證;而且，2）證書必須至少為2048位。
  
如果您沒有可用於伺服器對伺服器驗證的憑證，您可以取得新憑證、匯入新憑證，然後將該憑證用於伺服器對伺服器驗證。 在您要求並取得新憑證之後，您就可以登入任何一個前端伺服器，並使用類似這個的 Windows PowerShell 命令來匯入並指派該證書：
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 參數代表憑證檔案的完整路徑，而 Password 參數則代表指派給憑證的密碼。 這個程式應該只執行一次： [商務用 Skype Server] 複製服務接著會自動建立一組排程的任務，將憑證解密並部署到所有的前端伺服器。
  
或者，您可以使用現有的憑證作為伺服器對伺服器驗證憑證。 （如前所述，預設憑證可以用來做為伺服器對伺服器驗證憑證）。下列 Windows PowerShell 命令對會檢索預設憑證的 Thumbprint 屬性值，然後使用該值將預設憑證設為伺服器對伺服器驗證憑證：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在上述命令中，已將檢索的憑證設定為充當全域伺服器與伺服器驗證憑證的功能;這表示該憑證將會複製到您的所有前端伺服器並加以使用。 同樣地，這個命令只能在一次執行，而且只能在其中一個前端伺服器上執行。 雖然所有前端伺服器都必須使用相同的憑證，否則您不應該在每個前端伺服器上設定 OAuthTokenIssuer 憑證。 相反地，請改為將憑證設定一次，然後讓商務用 Skype Server 複製伺服器小心地將該憑證複製到每個伺服器。
  
CsCertificate Cmdlet 會取得相關的證書，並立即將該憑證設定為目前的 OAuthTokenIssuer 憑證。 （商務用 Skype Server 會保留兩份憑證類型的複本：目前憑證與前一個憑證）。如果您需要新憑證立即開始充當 OAuthTokenIssuer 憑證，您應該使用 CsCertificate Cmdlet。
  
您也可以使用 CsCertificate Cmdlet 來 [滾出] 新的憑證。 「滾動」憑證只是表示您要將新憑證設定為在指定的時間點成為目前的 OAuthTokenIssuer 憑證。 例如，這個命令會檢索預設憑證，然後將該憑證設定為在2015年7月1日之後作為目前的 OAuthTokenIssuer 憑證來接管：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

在2015年7月1日，新憑證會設定為目前的 OAuthTokenIssuer 憑證，而 "old" OAuthTokenIssuer 憑證將會設定為舊版的憑證。
  
如果您不想使用 Windows PowerShell，您也可以使用 [憑證] MMC 主控台來匯出來自一個前端伺服器的憑證，然後再匯入其他所有其他前端伺服器上的同一份證書。 如果您這樣做，請務必將私密金鑰與憑證本身一起匯出。
  
> [!CAUTION]
> 在這種情況下，程式必須在每個前端伺服器上執行。 以這種方式匯出及匯入憑證時，商務用 Skype Server 不會將該憑證複製到每個前端伺服器。 
  
在證書已匯入到您的所有前端伺服器之後，就可以使用商務用 Skype Server 部署嚮導（而不是 Windows PowerShell）來指派該憑證。 若要使用 [部署嚮導] 指派憑證，請在已安裝 [部署嚮導] 的電腦上完成下列步驟：
  
1. 按一下 [開始]，按一下 [所有程式]，按一下 [**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 部署嚮導]**。
    
2. 在 [部署嚮導] 中，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
3. 在 [商務用 Skype Server] 頁面上，按一下 [標題]**步驟3： [要求]、[安裝或指派憑證**] 底下的 [**執行**] 按鈕。 （注意：如果您已在這台電腦上安裝了證書，[**執行**] 按鈕就會再次標示為 [**執行**]。）
    
4. 在 [憑證] 嚮導中，選取 [ **OAuthTokenIssuer**憑證]，然後按一下 [**指派**]。
    
5. 在 [證書指派] 嚮導中，按一下 [**憑證指派**] 頁面上的 **[下一步]**。
    
6. 在 [**憑證存放區**] 頁面上，選取要用於伺服器對伺服器驗證的憑證，然後按一下 **[下一步]**。
    
7. 在 [憑證指派摘要] 頁面上，按一下 **[下一步]**。
    
8. 在 [執行命令] 頁面上，按一下 **[完成]**。
    
9. 關閉 [憑證] 嚮導和 [部署嚮導]。
    

