---
title: Lync Server 2013： 設定 Microsoft SharePoint Server 2013 搜尋已封存的 Lync Server 2013 資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SharePoint Server 2013 to search for archived Lync Server 2013 data
ms:assetid: 17f49365-8778-4962-a41b-f96faf6902f1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687978(v=OCS.15)
ms:contentKeyID: 49733566
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8debab39073bf31f509ec504f944c8e4c7a9dfc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="f708a-102">設定 Microsoft SharePoint Server 2013 搜尋已封存的 Microsoft Lync Server 2013 資料</span><span class="sxs-lookup"><span data-stu-id="f708a-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f708a-103">_**上次修改主題：** 2014年-02-04_</span><span class="sxs-lookup"><span data-stu-id="f708a-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f708a-104">若要將立即訊息和 Web 會議記錄儲存在 Microsoft Exchange Server 2013，而不是 Microsoft Lync Server 2013 的主要優點之一是將資料儲存在相同的位置可讓系統管理員可以使用單一工具來搜尋封存的 Exchange 資料及/或封存的 Lync Server 資料的事實。</span><span class="sxs-lookup"><span data-stu-id="f708a-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="f708a-105">因為所有的資料儲存在同一個放置 (Exchange) 封存 Exchange 資料可以搜尋任何工具也可以搜尋封存的 Lync Server 資料。</span><span class="sxs-lookup"><span data-stu-id="f708a-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="f708a-106">一種工具，可讓您輕鬆地搜尋封存的資料為 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f708a-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="f708a-107">如果您想要使用 SharePoint 搜尋 Lync Server 的資料，您必須先完成所有參與設定 Exchange 封存 Lync Server 中的步驟。</span><span class="sxs-lookup"><span data-stu-id="f708a-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="f708a-108">Exchange 2013 和 Lync Server 2013 有已成功地整合之後您必須在您的 SharePoint Server;，然後安裝 Exchange Web Services Managed API 2.0 版您可以從 Microsoft 下載中心下載該 API 的安裝程式 ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305))。</span><span class="sxs-lookup"><span data-stu-id="f708a-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="f708a-109">下載的檔案 (EWSManagedAPI.msi) 可以儲存至 SharePoint Server 上的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="f708a-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="f708a-110">下載檔案之後，在 SharePoint Server 上完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="f708a-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="f708a-111">依序按一下 [開始]\*\*\*\*、[所有程式]\*\*\*\* 及 [附屬應用程式]\*\*\*\*，再以滑鼠右鍵按一下 [命令提示字元]\*\*\*\*，然後按一下 [以系統管理員身分執行]\*\*\*\*，以開啟命令視窗。</span><span class="sxs-lookup"><span data-stu-id="f708a-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="f708a-112">在命令視窗中，使用 **cd** 命令將現行目錄切換至儲存 EWSManagedAPI.msi 檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="f708a-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="f708a-113">例如，如果您將檔案儲存至 c:\\下載命令視窗中輸入下列命令，然後按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="f708a-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="f708a-114">若要安裝 API，請輸入下列命令，然後按 ENTER 鍵：</span><span class="sxs-lookup"><span data-stu-id="f708a-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="f708a-115">安裝 API 之後，輸入下列命令並按 ENTER 鍵，以重設 IIS：</span><span class="sxs-lookup"><span data-stu-id="f708a-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="f708a-116">在安裝 Exchange Web 服務之後您必須再設定 SharePoint Server 2013 和 Exchange 2013 之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="f708a-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="f708a-117">若要這麼做，請先開啟 [SharePoint 2013 管理命令介面，並執行下列命令的：</span><span class="sxs-lookup"><span data-stu-id="f708a-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="f708a-118">請務必將該 URI 用於自動探索服務。</span><span class="sxs-lookup"><span data-stu-id="f708a-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="f708a-119">請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="f708a-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="f708a-120">建立 token 發行者以及設定 token 服務之後，請執行下列命令，請務必用來替代範例 URL 的 SharePoint 網站的 URLhttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="f708a-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="f708a-121">若要設定 Exchange 2013 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面並執行如下的命令 （假設已在 c： 磁碟機上安裝 Exchange，且其使用預設資料夾路徑）：</span><span class="sxs-lookup"><span data-stu-id="f708a-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="f708a-122">設定夥伴應用程式之後建議您停止並重新啟動所有 Exchange 信箱和用戶端存取伺服器上的網際網路資訊服務 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="f708a-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="f708a-123">您可以使用如下命令來重新啟動 IIS，其會在電腦 atl-exchange-001 上重新啟動該服務：</span><span class="sxs-lookup"><span data-stu-id="f708a-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="f708a-124">可以從執行此命令，或從任何其他命令視窗中 [Exchange 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="f708a-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="f708a-125">接著，執行下列命令，可讓指定的使用者 （在本例中為 kenmyer） 來執行探索 Exchange 上的權限如下的命令：</span><span class="sxs-lookup"><span data-stu-id="f708a-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="f708a-126">Exchange 與 SharePoint 之間建立伺服器對伺服器驗證之後下一個步驟是在 SharePoint 中建立電子文件探索站台。</span><span class="sxs-lookup"><span data-stu-id="f708a-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="f708a-127">可以藉由執行類似這些從 SharePoint 管理命令介面命令：</span><span class="sxs-lookup"><span data-stu-id="f708a-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="f708a-128">"eDiscovery" 是 "electronic discovery" (電子化探索) 的縮寫，此程序通常是指在電子化封存中尋找可以在法庭上「合理計算以導出可採納證據」的項目。</span><span class="sxs-lookup"><span data-stu-id="f708a-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="f708a-129">準備新的網站時下, 一步是設定 Exchange 2013 到 SharePoint 做為結果來源。</span><span class="sxs-lookup"><span data-stu-id="f708a-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="f708a-130">您可以這麼做，請完成下列程序，從 [SharePoint 2013 管理中心] 頁面上：</span><span class="sxs-lookup"><span data-stu-id="f708a-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="f708a-131">在「管理中心」頁面上，按一下 [管理服務應用程式]\*\*\*\*，然後按一下 [Search Service 應用程式]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="f708a-132">在「Search Service 應用程式：搜尋管理」頁面上，按一下 [結果來源]\*\*\*\* ，然後按一下 [新增結果來源]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="f708a-133">在 [新增結果來源]\*\*\*\* 窗格的 [名稱]\*\*\*\* 方塊中，輸入新結果來源的名稱 (例如，**Microsoft Exchange**)。</span><span class="sxs-lookup"><span data-stu-id="f708a-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="f708a-134">選取 [ **Exchange]** 作為**通訊協定**的結果來源，然後輸入您的 Exchange 伺服器中**Exchange 來源 URL** ] 方塊中的 [web 服務來源 URL。</span><span class="sxs-lookup"><span data-stu-id="f708a-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="f708a-135">來源 URL 看起來應該像下面這樣：</span><span class="sxs-lookup"><span data-stu-id="f708a-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="f708a-136">請確定未選取 [使用自動探索]\*\*\*\*，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="f708a-137">最後，建立新的 eDiscovery 案例及新的 eDiscovery 集 （例如，完成下列程序從 SharePoint 探索站台https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="f708a-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="f708a-138">在「網站內容」頁面上，按一下 [建立新案例]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="f708a-p110">在「網站內容：建立 SharePoint 網站」頁面上的 [標題]\*\*\*\* 方塊中，輸入使用者的電子郵件別名 (例如，**kenmyer**)，然後將那相同的 URL 新增至 [網站位址]\*\*\*\* 方塊中。如此將會產生像下面這樣的 URL：</span><span class="sxs-lookup"><span data-stu-id="f708a-p110">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box. That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="f708a-141">按一下 [建立]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-141">Click **Create**.</span></span>

4.  <span data-ttu-id="f708a-142">當「eDiscovery 集」頁面出現時，按一下 [識別與保留: Discovery 集]\*\*\*\* 底下的 [新項目]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="f708a-143">在「新增：Discovery 集」頁面上的 [Discovery 集名稱]\*\*\*\* 方塊中，輸入使用者電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="f708a-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="f708a-144">輸入**eDiscovery Lync\*** 在 [**篩選**] 方塊，然後按一下 [**新增 & 管理來源**。</span><span class="sxs-lookup"><span data-stu-id="f708a-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="f708a-p112">在「新增及管理來源」頁面上 [信箱]\*\*\*\* 底下的第一個文字方塊中，輸入使用者的電子郵件別名。按一下位在文字方塊旁邊的檢查信箱圖示，確認 SharePoint 可以連線至指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="f708a-p112">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**. Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="f708a-147">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f708a-147">Click **OK**.</span></span>

8.  <span data-ttu-id="f708a-148">在「eDiscovery 集」頁面上， 按一下 [儲存]\*\*\*\*，以儲存新的 eDiscovery 集。</span><span class="sxs-lookup"><span data-stu-id="f708a-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="f708a-149">此時，您可以搜尋指定的信箱 (kenmyer) 及/或啟用就地保留任何其他 SharePoint 內容或結果來源的相同的方式。</span><span class="sxs-lookup"><span data-stu-id="f708a-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

