---
title: 針對商務用 Skype Server 設定內部部署合作夥伴應用程式
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
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 摘要：針對商務用 Skype Server 設定內部部署合作夥伴應用程式。
ms.openlocfilehash: 3f8aa3bfc7407ccf6409d00c540cfeab724913ab
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818825"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>針對商務用 Skype Server 設定內部部署合作夥伴應用程式
 
**摘要：** 針對商務用 Skype Server 設定內部部署合作夥伴應用程式。
  
指派 OAuthTokenIssuer 憑證之後，您必須設定您的商務用 Skype Server 合作夥伴應用程式。 （討論的程式會將 Microsoft Exchange Server 2013 和 SharePoint 設定為可作為合作夥伴應用程式（選用）。若要設定內部部署合作夥伴應用程式，您必須先複製下列 Windows PowerShell 腳本，然後將程式碼貼到記事本（或任何其他的文字編輯器）中：
  
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

複製程式碼之後，請使用來儲存腳本。PS1 檔案副檔名（例如，C:\Scripts\ServerToServerAuth.ps1）。 請注意，在執行此腳本前，您必須將中繼資料 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1與http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 Exchange 2013 和 SharePoint 伺服器分別使用的中繼資料 url 取代。 請參閱 Exchange 2013 和 SharePoint 的產品檔，以取得如何識別個別產品中繼資料 URL 的資訊。
  
如果您看到腳本的最後一行，您會注意到 CsOAuthConfiguration Cmdlet 是使用下列語法來呼叫：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

因為在呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以 realm 會自動設定為貴組織的完整功能變數名稱（FQDN）（例如，litwareinc.com）。 如果您的領域名稱與您的組織名稱不一樣，您應該包含領域名稱稱，如下所示：
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

進行這些變更之後，您就可以執行此腳本，並將 Exchange 2013 和 SharePoint 設定為合作夥伴應用程式，方法是從商務用 Skype Server Management Shell 中執行腳本檔案。 例如：
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

請注意，即使您沒有安裝 Exchange 2013 和 SharePoint Server，您也可以執行此腳本：如果您沒有安裝 SharePoint Server，就不會發生任何問題，只要將 SharePoint Server 設定為合作夥伴應用程式即可。
  
當您執行此腳本時，您可能會收到類似以下的錯誤訊息：
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

此錯誤訊息通常是指以下兩種情況之一：1）在腳本中指定的其中一個 Url 無效（也就是，您的其中一個中繼資料 Url 不是實際中繼資料 URL）;或者，2）無法與其中一個中繼資料 Url 取得聯繫。 如果發生這種情況，請確認 Url 正確且可存取，然後重新執行腳本。
  
為商務用 Skype Server 建立合作夥伴應用程式之後，您必須接著將商務用 Skype 伺服器設定為 Exchange 2013 的合作夥伴應用程式。 您可以執行腳本 Configure-EnterprisePartnerApplication，以設定 Exchange 2013 的合作夥伴應用程式。您只需要指定商務用 Skype Server 的中繼資料 URL，並指出商務用 Skype 伺服器是新的合作夥伴應用程式。 
  
若要將商務用 Skype Server 設定為 Exchange 的合作夥伴應用程式，請開啟 Exchange 管理命令介面並執行類似此的命令
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


