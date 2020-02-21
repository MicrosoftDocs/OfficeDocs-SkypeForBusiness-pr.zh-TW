---
title: 設定 Lync Server 2013 內部部署夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58cfee7b89d2e7e66bd39b28a6d3361b4521cdc2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207569"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>設定 Microsoft Lync Server 2013 內部部署夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-04_

之後您指派然後，您必須設定您的 Microsoft Lync Server 2013 協力廠商應用程式的 OAuthTokenIssuer 憑證。 （討論的程序設定 Microsoft Exchange Server 2013 和 Microsoft SharePoint 做為協力廠商應用程式）。若要設定內部部署夥伴應用程式，您必須啟動複製下列 Windows PowerShell 指令碼，並將程式碼貼入 [記事本] （或任何其他文字編輯器）：

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
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

複製程式碼之後, 將儲存指令碼使用。PS1 副檔名 (例如 c:\\指令碼\\ServerToServerAuth.ps1)。 請注意，在執行此指令碼之前，您必須取代的中繼資料 Urlhttps://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1和http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx與分別對 Exchange 2013 和 SharePoint 伺服器，所使用的中繼資料 Url。 在如何找出各自產品的中繼資料 URL，請參閱資訊的 Exchange 2013 和 SharePoint 產品文件。

如果您注意指令碼的最後一行，就會發現是使用此語法來呼叫 Set-CsOAuthConfiguration Cmdlet ：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

因為呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以領域會自動設為您組織的完整網域名稱 (FQDN) (例如 litwareinc.com)。如果您的領域名稱與組織名稱不同，就應包含領域名稱，方式如下：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

進行這些變更之後您可以接著執行指令碼，並設定兩個 Exchange 2013 和 SharePoint 做為合作夥伴應用程式，來執行指令碼檔案從在 Lync Server 2013 管理命令介面。 例如：

    C:\Scripts\ServerToServerAuth.ps1

請注意，即使您不需要兩個 Exchange 2013 和 SharePoint Server 安裝，您可以執行此指令碼:，不會發生問題，說，將 SharePoint Server 設定為夥伴應用程式，即使您不需要 SharePoint Server 安裝。

當您執行此指令碼時，可能會收到如下的錯誤訊息：

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

此錯誤訊息通常代表發生下列兩種情況其中之一：1) 指令碼中其中一個指定的 URL 無效 (亦即，其中一個中繼資料 URL 並非實際的中繼資料 URL)；或 2) 無法連絡其中一個中繼資料 URL。如果發生這種情況，請驗證 URL 為正確且可存取，然後重新執行指令碼。

建立 Lync Server 2013 的夥伴應用程式之後，您必須接著設定 Lync Server 以 Exchange 2013 為合作夥伴應用程式。 您可以設定 Exchange 2013 的協力廠商應用程式執行的指令碼 Configure-enterprisepartnerapplication.ps1;您只需要為 Lync Server 的指定的中繼資料 URL，並指出 Lync Server 是新的協力廠商應用程式。

若要設定 Lync Server 的協力廠商應用程式為 Exchange，開啟 Exchange 管理命令介面並執行如下的命令

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

