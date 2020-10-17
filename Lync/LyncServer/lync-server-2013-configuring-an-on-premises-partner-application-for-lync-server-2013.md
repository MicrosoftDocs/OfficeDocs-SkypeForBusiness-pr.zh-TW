---
title: 設定 Lync Server 2013 的內部部署夥伴應用程式
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
ms.openlocfilehash: 34b6cd21d781f26ca734effd0c574c016aec3266
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517580"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="aa052-102">設定 Microsoft Lync Server 2013 的內部部署夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="aa052-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa052-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="aa052-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="aa052-104">在指派 OAuthTokenIssuer 憑證之後，您必須設定您的 Microsoft Lync Server 2013 夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa052-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="aa052-105"> (討論的程式會將 Microsoft Exchange Server 2013 和 Microsoft SharePoint 設定為作為夥伴應用程式。 ) 若要設定內部部署夥伴應用程式，您必須先複製下列 Windows PowerShell 腳本，然後將程式碼貼到 [記事本] 或任何其他的文字編輯器中 (：</span><span class="sxs-lookup"><span data-stu-id="aa052-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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

<span data-ttu-id="aa052-106">複製程式碼之後，使用來儲存腳本。PS1 副檔名 (例如 C： \\ Scripts \\ServerToServerAuth.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="aa052-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="aa052-107">請注意，在您執行此腳本之前，您必須將中繼資料 URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 和 http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx 您的 Exchange 2013 和 SharePoint 伺服器分別使用的中繼資料 URLs 取代。</span><span class="sxs-lookup"><span data-stu-id="aa052-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="aa052-108">如需如何識別各自產品的中繼資料 URL 的詳細資訊，請參閱 Exchange 2013 和 SharePoint 的產品檔。</span><span class="sxs-lookup"><span data-stu-id="aa052-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="aa052-109">如果您注意指令碼的最後一行，就會發現是使用此語法來呼叫 Set-CsOAuthConfiguration Cmdlet ：</span><span class="sxs-lookup"><span data-stu-id="aa052-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="aa052-p103">因為呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以領域會自動設為您組織的完整網域名稱 (FQDN) (例如 litwareinc.com)。如果您的領域名稱與組織名稱不同，就應包含領域名稱，方式如下：</span><span class="sxs-lookup"><span data-stu-id="aa052-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="aa052-112">進行這些變更之後，您可以執行腳本，並在 Lync Server 2013 管理命令介面中執行腳本檔案，以將 Exchange 2013 和 SharePoint 設定為合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa052-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="aa052-113">例如：</span><span class="sxs-lookup"><span data-stu-id="aa052-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="aa052-114">請注意，即使您沒有安裝 Exchange 2013 和 SharePoint 伺服器，也可以執行這個腳本：如果您沒有安裝 SharePoint 伺服器，請將 SharePoint 伺服器設定為夥伴應用程式，也不會發生問題。</span><span class="sxs-lookup"><span data-stu-id="aa052-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="aa052-115">當您執行此指令碼時，可能會收到如下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="aa052-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="aa052-p105">此錯誤訊息通常代表發生下列兩種情況其中之一：1) 指令碼中其中一個指定的 URL 無效 (亦即，其中一個中繼資料 URL 並非實際的中繼資料 URL)；或 2) 無法連絡其中一個中繼資料 URL。如果發生這種情況，請驗證 URL 為正確且可存取，然後重新執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="aa052-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="aa052-118">建立 Lync Server 2013 的夥伴應用程式之後，您必須將 Lync 伺服器設定為 Exchange 2013 的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa052-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="aa052-119">您可以執行腳本 Configure-EnterprisePartnerApplication.ps1，以設定 Exchange 2013 的夥伴應用程式。您只需要指定 Lync Server 的中繼資料 URL，並指出 Lync Server 是新的夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa052-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="aa052-120">若要將 Lync Server 設定為 Exchange 的夥伴應用程式，請開啟 Exchange 管理命令介面，並執行類似下列的命令</span><span class="sxs-lookup"><span data-stu-id="aa052-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

