---
title: 將伺服器對伺服器驗證憑證指派給商務用 Skype Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：指派商務用 Skype Server 的伺服器對伺服器驗證憑證。
ms.openlocfilehash: 67e9b618e882a257047a4569e790d96c73bf386b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621079"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>將伺服器對伺服器驗證憑證指派給商務用 Skype Server
**摘要：** 指派商務用 Skype Server 的伺服器對伺服器驗證憑證。
  
若要判斷伺服器對伺服器驗證憑證是否已指派給商務用 Skype Server，請從商務用 Skype Server 管理命令介面執行下列命令：
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

若未傳回憑證資訊，您必須指派 token 簽發者憑證，才能使用伺服器對伺服器驗證。 一般來說，任何商務用 Skype Server 憑證均可用作 OAuthTokenIssuer 憑證;例如，您的商務用 Skype Server 預設憑證也可用作 OAuthTokenIssuer 憑證。  (OAUthTokenIssuer 憑證也可以是任何網頁伺服器憑證，包含 [主旨] 欄位中的 SIP 網功能變數名稱稱。 ) 伺服器對伺服器驗證所用之憑證的主要兩項需求如下： 1) 相同的憑證必須設定為所有前端伺服器上的 OAuthTokenIssuer 憑證;而且，2) 憑證必須至少是2048位。
  
如果您沒有可用於伺服器對伺服器驗證的憑證，您可以取得新的憑證，匯入新的憑證，然後使用該憑證進行伺服器對伺服器驗證。 在您要求並取得新憑證之後，您可以登入任何一部前端伺服器，並使用與下列類似的 Windows PowerShell 命令，匯入並指派該憑證：
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

在上述命令中，Path 參數會代表憑證檔案的完整路徑，而 Password 參數則代表指派給憑證的密碼。 此程式應只執行一次：然後商務用 Skype Server 複寫服務會自動建立一組排程的工作，將憑證解密並部署至您的所有前端伺服器。
  
或者，您可以使用現有憑證做為伺服器對伺服器驗證憑證。  (所述，可將預設憑證當做伺服器對伺服器驗證憑證使用。 ) 下列 Windows PowerShell 命令可取得預設憑證的 Thumbprint 屬性值，然後使用該值將預設憑證設為伺服器對伺服器驗證憑證：
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

在上述命令中，所檢索的憑證會設定為以全域伺服器對伺服器驗證憑證的形式運作;這表示憑證將會複製到並由所有前端伺服器使用。 同樣地，此命令只會執行一次，且只能在其中一部前端伺服器上執行。 雖然所有前端伺服器都必須使用相同的憑證，但您不應該在每個前端伺服器上設定 OAuthTokenIssuer 憑證。 請改為設定憑證一次，然後讓商務用 Skype Server 複寫伺服器負責將該憑證複製到每個伺服器。
  
Set-CsCertificate Cmdlet 會採取問題的憑證，並立即設定該憑證充當目前的 OAuthTokenIssuer 憑證。  (商務用 Skype Server 保留憑證類型的兩個複本：目前的憑證和舊的憑證。 ) 如果您需要新的憑證立即開始成為 OAuthTokenIssuer 憑證，則應該使用 Set-CsCertificate Cmdlet。
  
您也可以使用 Set-CsCertificate Cmdlet 來「推出」新的憑證。 「滾動」憑證只是表示您將新的憑證設定為在指定的時間點成為目前的 OAuthTokenIssuer 憑證。 例如，此命令會檢索預設憑證，然後設定該憑證作為目前的 OAuthTokenIssuer 憑證，在2015年7月1日為止。
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

在2015年7月1日，新的憑證會設定為目前的 OAuthTokenIssuer 憑證，而 "old" OAuthTokenIssuer 憑證將設定為舊版憑證。
  
如果您不想要使用 Windows PowerShell 您也可以使用憑證 MMC 主控台從一部前端伺服器匯出憑證，然後在其他所有的前端伺服器上匯入該相同的憑證。 如果您這麼做，請確定匯出私密金鑰和憑證本身。
  
> [!CAUTION]
> 在此情況下，必須在每一部前端伺服器上執行該程式。 以這種方式匯出及匯入憑證時商務用 Skype Server 不會將該憑證複製到每個前端伺服器。 
  
將憑證匯入至所有前端伺服器之後，即可使用商務用 Skype Server 部署嚮導（而不是 Windows PowerShell）來指派該憑證。 若要使用部署嚮導指派憑證，請在已安裝部署嚮導的電腦上完成下列步驟：
  
1. 依序按一下 [開始]、[所有程式]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 部署嚮導]**。
    
2. 在 [部署嚮導] 中，按一下 [**安裝或更新商務用 Skype Server 系統**]。
    
3. 在 [商務用 Skype Server] 頁面上，按一下 [標題 **步驟3：要求、安裝或指派憑證**] 底下的 [**執行**] 按鈕。  (注意：如果您已在此電腦上安裝憑證，則會將 [ **執行** ] 按鈕重新標示為 [ **執行** 中]。 ) 
    
4. 在 [憑證] 嚮導中，選取 **OAuthTokenIssuer** 憑證，然後按一下 [ **指派**]。
    
5. 在 [憑證指派] 嚮導的 [ **憑證指派** ] 頁面上，按 **[下一步]**。
    
6. 在 [ **憑證存放區** ] 頁面上，選取要用於伺服器對伺服器驗證的憑證，然後按 **[下一步]**。
    
7. 在 [憑證指派摘要] 頁面上，按 **[下一步]**。
    
8. 在 [執行命令] 頁面上，按一下 **[完成]**。
    
9. 關閉憑證嚮導和部署嚮導。
    

