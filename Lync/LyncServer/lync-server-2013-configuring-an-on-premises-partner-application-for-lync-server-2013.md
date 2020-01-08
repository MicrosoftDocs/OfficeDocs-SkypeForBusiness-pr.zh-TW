---
title: 針對 Lync Server 2013 設定內部部署合作夥伴應用程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c396415dd6bd3bda99254f30b0223f1ff672a01f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>針對 Microsoft Lync Server 2013 設定內部部署合作夥伴應用程式

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-04_

指派 OAuthTokenIssuer 憑證之後，您必須設定您的 Microsoft Lync Server 2013 合作夥伴應用程式。 （討論的程式會將 Microsoft Exchange Server 2013 與 Microsoft SharePoint 設定為共同擔當合作夥伴應用程式。）若要設定內部部署合作夥伴應用程式，您必須先複製下列 Windows PowerShell 腳本，然後將程式碼貼到記事本（或任何其他的文字編輯器）中：

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

複製程式碼之後，請使用來儲存腳本。PS1 檔案副檔名（例如，C：\\Scripts\\ServerToServerAuth. ps1）。 請注意，在執行此腳本前，您必須將中繼資料 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1與http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx Exchange 2013 和 SharePoint 伺服器分別使用的中繼資料 url 取代。 請參閱 Exchange 2013 和 SharePoint 的產品檔，以取得如何識別個別產品中繼資料 URL 的資訊。

如果您看到腳本的最後一行，您會注意到 CsOAuthConfiguration Cmdlet 是使用下列語法來呼叫：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

因為在呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以 realm 會自動設定為貴組織的完整功能變數名稱（FQDN）（例如，litwareinc.com）。 如果您的領域名稱與您的組織名稱不一樣，您應該包含領域名稱稱，如下所示：

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

進行這些變更之後，您就可以執行腳本，並將 Exchange 2013 和 SharePoint 設定為合作夥伴應用程式，方法是在 Lync Server 2013 管理命令介面中執行腳本檔案。 例如：

    C:\Scripts\ServerToServerAuth.ps1

請注意，即使您沒有安裝 Exchange 2013 和 SharePoint Server，您也可以執行此腳本：如果您沒有安裝 SharePoint Server，就不會發生任何問題，只要將 SharePoint Server 設定為合作夥伴應用程式即可。

當您執行此腳本時，您可能會收到類似以下的錯誤訊息：

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

此錯誤訊息通常是指以下兩種情況之一：1）在腳本中指定的其中一個 Url 無效（也就是，您的其中一個中繼資料 Url 不是實際中繼資料 URL）;或者，2）無法與其中一個中繼資料 Url 取得聯繫。 如果發生這種情況，請確認 Url 正確且可存取，然後重新執行腳本。

在為 Lync Server 2013 建立合作夥伴應用程式之後，您必須將 Lync Server 設定為 Exchange 2013 的合作夥伴應用程式。 您可以執行腳本 Configure-EnterprisePartnerApplication，以設定 Exchange 2013 的合作夥伴應用程式。您只需要指定 Lync Server 的中繼資料 URL，並指出 Lync Server 是新的合作夥伴應用程式。

若要將 Lync Server 設定為 Exchange 的合作夥伴應用程式，請開啟 Exchange 管理命令介面，並執行如下所述的命令

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

