---
title: 設定商務用 Skype Server 的內部部署夥伴應用程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要：設定商務用 Skype Server 的內部部署夥伴應用程式。
ms.openlocfilehash: 794960a454d1028845820218d04b85e7faef17296417118217628d725e4dc815
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315689"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>設定商務用 Skype Server 的內部部署夥伴應用程式
 
**摘要：** 設定商務用 Skype Server 的內部部署夥伴應用程式。
  
在指派 OAuthTokenIssuer 憑證之後，您必須設定商務用 Skype Server 夥伴應用程式。  (所討論的程式會設定 Microsoft Exchange Server 2013 和 SharePoint 做為協力廠商應用程式，也就是選用的。 ) 若要設定內部部署夥伴應用程式，您必須先複製下列 Windows PowerShell 腳本，然後將程式碼貼到記事本 (或任何其他文字編輯器) 中：
  
```PowerShell
if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
   {
       Remove-CsPartnerApplication app
   }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
        
if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
           }
     }

$shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
        
if ($shp -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
    }
else
    {
       if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.sharepoint
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

在複製代碼後，請使用 .PS1 副檔名儲存指令碼 (例如 C:\Scripts\ServerToServerAuth.ps1)。 請注意，在您執行此腳本之前，您必須將中繼資料 URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 和 http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 中繼資料 URLs 分別取代 Exchange 2013 及 SharePoint 伺服器所使用的中繼資料。 如需如何識別各自產品的中繼資料 URL 的詳細資訊，請參閱 Exchange 2013 和 SharePoint 的產品檔。
  
如果您注意指令碼的最後一行，就會發現是使用此語法來呼叫 Set-CsOAuthConfiguration Cmdlet ：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

因為呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以領域會自動設為您組織的完整網域名稱 (FQDN) (例如 litwareinc.com)。如果您的領域名稱與組織名稱不同，就應包含領域名稱，方式如下：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

進行這些變更之後，您就可以執行腳本，並從商務用 Skype Server 管理命令介面中執行腳本檔案，以設定 Exchange 2013 和 SharePoint 做為協力廠商應用程式。 例如：
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

請注意，即使您沒有安裝 Exchange 2013 和 SharePoint 伺服器，也可以執行這個腳本：如果您沒有安裝 SharePoint 伺服器，請將 SharePoint 伺服器設定為夥伴應用程式，也不會發生問題。
  
當您執行此指令碼時，可能會收到如下的錯誤訊息：
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此錯誤訊息通常代表發生下列兩種情況其中之一：1) 指令碼中其中一個指定的 URL 無效 (亦即，其中一個中繼資料 URL 並非實際的中繼資料 URL)；或 2) 無法連絡其中一個中繼資料 URL。如果發生這種情況，請驗證 URL 為正確且可存取，然後重新執行指令碼。
  
為商務用 Skype Server 建立夥伴應用程式之後，您必須將商務用 Skype Server 設定為 Exchange 2013 的夥伴應用程式。 您可以執行腳本 Configure-EnterprisePartnerApplication.ps1，以設定 Exchange 2013 的夥伴應用程式。您只需要為商務用 Skype Server 指定中繼資料 URL，並指出商務用 Skype Server 是新的夥伴應用程式。 
  
若要將商務用 Skype Server 設定為 Exchange 的夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似下列的命令
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


