---
title: 針對 Lync Server 2013 設定內部部署合作夥伴應用程式
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
ms.openlocfilehash: 6fe3597f873e8f3bcf66eba922624e4c13ab3f3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a><span data-ttu-id="16d89-102">針對 Microsoft Lync Server 2013 設定內部部署合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="16d89-102">Configuring an on-premises partner application for Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16d89-103">_**主題上次修改日期：** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="16d89-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="16d89-104">指派 OAuthTokenIssuer 憑證之後，您必須設定您的 Microsoft Lync Server 2013 合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="16d89-104">After you have assigned the OAuthTokenIssuer certificate you must then configure your Microsoft Lync Server 2013 partner applications.</span></span> <span data-ttu-id="16d89-105">（討論的程式會將 Microsoft Exchange Server 2013 與 Microsoft SharePoint 設定為共同擔當合作夥伴應用程式。）若要設定內部部署合作夥伴應用程式，您必須先複製下列 Windows PowerShell 腳本，然後將程式碼貼到記事本（或任何其他的文字編輯器）中：</span><span class="sxs-lookup"><span data-stu-id="16d89-105">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and Microsoft SharePoint to act as partner applications.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>

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

<span data-ttu-id="16d89-106">複製程式碼之後，請使用來儲存腳本。PS1 檔案副檔名（例如，C：\\Scripts\\ServerToServerAuth. ps1）。</span><span class="sxs-lookup"><span data-stu-id="16d89-106">After copying the code, save the script using a .PS1 file extension (for example, C:\\Scripts\\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="16d89-107">請注意，在執行此腳本前，您必須將中繼資料 Url https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1與http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx Exchange 2013 和 SharePoint 伺服器分別使用的中繼資料 url 取代。</span><span class="sxs-lookup"><span data-stu-id="16d89-107">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="16d89-108">請參閱 Exchange 2013 和 SharePoint 的產品檔，以取得如何識別個別產品中繼資料 URL 的資訊。</span><span class="sxs-lookup"><span data-stu-id="16d89-108">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>

<span data-ttu-id="16d89-109">如果您看到腳本的最後一行，您會注意到 CsOAuthConfiguration Cmdlet 是使用下列語法來呼叫：</span><span class="sxs-lookup"><span data-stu-id="16d89-109">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="16d89-110">因為在呼叫 Set-CsOAuthConfiguration 時未使用 Realm 參數，所以 realm 會自動設定為貴組織的完整功能變數名稱（FQDN）（例如，litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="16d89-110">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com).</span></span> <span data-ttu-id="16d89-111">如果您的領域名稱與您的組織名稱不一樣，您應該包含領域名稱稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="16d89-111">If your realm name is different from your organization name then you should include the realm name, like this:</span></span>

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

<span data-ttu-id="16d89-112">進行這些變更之後，您就可以執行腳本，並將 Exchange 2013 和 SharePoint 設定為合作夥伴應用程式，方法是在 Lync Server 2013 管理命令介面中執行腳本檔案。</span><span class="sxs-lookup"><span data-stu-id="16d89-112">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="16d89-113">例如：</span><span class="sxs-lookup"><span data-stu-id="16d89-113">For example:</span></span>

    C:\Scripts\ServerToServerAuth.ps1

<span data-ttu-id="16d89-114">請注意，即使您沒有安裝 Exchange 2013 和 SharePoint Server，您也可以執行此腳本：如果您沒有安裝 SharePoint Server，就不會發生任何問題，只要將 SharePoint Server 設定為合作夥伴應用程式即可。</span><span class="sxs-lookup"><span data-stu-id="16d89-114">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>

<span data-ttu-id="16d89-115">當您執行此腳本時，您可能會收到類似以下的錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="16d89-115">When you run this script you might receive an error message similar to the following:</span></span>

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

<span data-ttu-id="16d89-116">此錯誤訊息通常是指以下兩種情況之一：1）在腳本中指定的其中一個 Url 無效（也就是，您的其中一個中繼資料 Url 不是實際中繼資料 URL）;或者，2）無法與其中一個中繼資料 Url 取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="16d89-116">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted.</span></span> <span data-ttu-id="16d89-117">如果發生這種情況，請確認 Url 正確且可存取，然後重新執行腳本。</span><span class="sxs-lookup"><span data-stu-id="16d89-117">If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>

<span data-ttu-id="16d89-118">在為 Lync Server 2013 建立合作夥伴應用程式之後，您必須將 Lync Server 設定為 Exchange 2013 的合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="16d89-118">After creating the partner application for Lync Server 2013 you must then configure Lync Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="16d89-119">您可以執行腳本 Configure-EnterprisePartnerApplication，以設定 Exchange 2013 的合作夥伴應用程式。您只需要指定 Lync Server 的中繼資料 URL，並指出 Lync Server 是新的合作夥伴應用程式。</span><span class="sxs-lookup"><span data-stu-id="16d89-119">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Lync Server and indicate that Lync Server is the new partner application.</span></span>

<span data-ttu-id="16d89-120">若要將 Lync Server 設定為 Exchange 的合作夥伴應用程式，請開啟 Exchange 管理命令介面，並執行如下所述的命令</span><span class="sxs-lookup"><span data-stu-id="16d89-120">To configure Lync Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

