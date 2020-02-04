---
title: Lync Server 2013：設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Lync Server 2013 資料
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
ms.openlocfilehash: 1e000f6116b112b3de9840c22c29510745303035
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-sharepoint-server-2013-to-search-for-archived-microsoft-lync-server-2013-data"></a><span data-ttu-id="d7c91-102">設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Microsoft Lync Server 2013 資料</span><span class="sxs-lookup"><span data-stu-id="d7c91-102">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7c91-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="d7c91-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="d7c91-104">在 Microsoft Exchange Server 2013 （而非 Microsoft Lync Server 2013）中儲存立即訊息和網路會議記錄的主要優點之一，是將資料儲存在同一個位置，讓系統管理員可以使用單一工具搜尋已歸檔的 Exchange 資料和/或已歸檔的 Lync Server 資料。</span><span class="sxs-lookup"><span data-stu-id="d7c91-104">One of the major advantages to storing instant messaging and Web conferencing transcripts in Microsoft Exchange Server 2013 instead of Microsoft Lync Server 2013 is the fact that storing data in the same location enables administrators to use a single tool to search for archived Exchange data and/or archived Lync Server data.</span></span> <span data-ttu-id="d7c91-105">由於所有資料都儲存在同一個位置（Exchange）中，任何可以搜尋已歸檔 Exchange 資料的工具也都可以搜尋已歸檔的 Lync Server 資料。</span><span class="sxs-lookup"><span data-stu-id="d7c91-105">Because all the data is stored in the same place (Exchange) any tool that can search for archived Exchange data can also search for archived Lync Server data.</span></span>

<span data-ttu-id="d7c91-106">可讓您輕鬆搜尋已歸檔資料的一個工具是 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="d7c91-106">One tool that makes it easy to search for archived data is Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="d7c91-107">如果您想要使用 SharePoint 來搜尋 Lync Server 資料，您必須先完成在 Lync Server 中設定 Exchange 封存所需的所有步驟。</span><span class="sxs-lookup"><span data-stu-id="d7c91-107">If you would like to use SharePoint to search for Lync Server data, you must first complete all the steps involved in configuring Exchange archiving in Lync Server.</span></span> <span data-ttu-id="d7c91-108">成功整合 Exchange 2013 和 Lync Server 2013 之後，您必須接著在 SharePoint Server 上安裝 Exchange Web Services Managed API 版本 2.0;該 API 的安裝程式可以從 Microsoft 下載中心下載（[http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)）。</span><span class="sxs-lookup"><span data-stu-id="d7c91-108">After Exchange 2013 and Lync Server 2013 have been successfully integrated you must then install the Exchange Web Services Managed API Version 2.0 on your SharePoint Server; the setup program for that API can be downloaded from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/p/?LinkId=258305](http://go.microsoft.com/fwlink/p/?linkid=258305)).</span></span> <span data-ttu-id="d7c91-109">下載的檔案（EWSManagedAPI）可儲存至 SharePoint 伺服器上的任何資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7c91-109">The downloaded file (EWSManagedAPI.msi) can be saved to any folder on your SharePoint server.</span></span>

<span data-ttu-id="d7c91-110">檔案下載之後，請在 SharePoint 伺服器上完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="d7c91-110">After the file has been downloaded complete the following procedure on the SharePoint server:</span></span>

1.  <span data-ttu-id="d7c91-111">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，以滑鼠右鍵按一下 [**命令提示**字元]，然後按一下 [**以系統管理員身分執行**] 來開啟命令視窗。</span><span class="sxs-lookup"><span data-stu-id="d7c91-111">Open a command window by clicking **Start**, clicking **All Programs**, clicking **Accessories**, right-clicking **Command Prompt**, and then clicking **Run as administrator**.</span></span>

2.  <span data-ttu-id="d7c91-112">在命令視窗中，使用 [ **cd** ] 命令，將目前的目錄變更為已儲存檔案 EWSManagedAPI 的資料夾。</span><span class="sxs-lookup"><span data-stu-id="d7c91-112">In the command window, use the **cd** command to change the current directory to the folder where the file EWSManagedAPI.msi has been saved.</span></span> <span data-ttu-id="d7c91-113">例如，如果您已將檔案儲存到 C：\\下載，請在命令視窗中輸入下列命令，然後按 enter：</span><span class="sxs-lookup"><span data-stu-id="d7c91-113">For example, if you have saved the file to C:\\Downloads type the following command in the command window and then press ENTER:</span></span>
    
        cd C:\Downloads

3.  <span data-ttu-id="d7c91-114">若要安裝 API，請輸入下列命令，然後按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="d7c91-114">To install the API, type the following command then press ENTER:</span></span>
    
        msiexec /I EwsManagedApi.msi addlocal="ExchangeWebServicesApi_Feature,ExchangeWebServicesApi_Gac"

4.  <span data-ttu-id="d7c91-115">安裝 API 之後，請輸入下列命令，然後按 ENTER 來重設 IIS：</span><span class="sxs-lookup"><span data-stu-id="d7c91-115">After the API has been installed, reset IIS by typing the following command and pressing ENTER:</span></span>
    
        iisreset

<span data-ttu-id="d7c91-116">在已安裝 Exchange Web 服務之後，您必須在 SharePoint Server 2013 與 Exchange 2013 之間設定伺服器對伺服器的驗證。</span><span class="sxs-lookup"><span data-stu-id="d7c91-116">After Exchange Web Services has been installed you must then configure server-to-server authentication between SharePoint Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="d7c91-117">若要這樣做，請先開啟 SharePoint 2013 管理命令介面，然後執行下列命令組：</span><span class="sxs-lookup"><span data-stu-id="d7c91-117">To do this, first open the SharePoint 2013 Management Shell and run the following set of command:</span></span>

    New-SPTrustedSecurityTokenIssuer -Name "Exchange" -MetadataEndPoint "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"
    $service = Get-SPSecurityTokenServiceConfig
    $service.HybridStsSelectionEnabled = $True
    $service.AllowMetadataOverHttp = $False
    $service.AllowOAuthOverHttp = $False
    $service.Update()

<div>


> [!NOTE]  
> <span data-ttu-id="d7c91-118">請務必在您的自動探索服務中使用 URI。</span><span class="sxs-lookup"><span data-stu-id="d7c91-118">Be sure and use the URI for your autodiscover service.</span></span> <span data-ttu-id="d7c91-119">請勿使用範例 URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1。</span><span class="sxs-lookup"><span data-stu-id="d7c91-119">Do not use the sample URI https://autodiscover.litwareinc.com/autodiscover/metadata/json/1.</span></span>



</div>

<span data-ttu-id="d7c91-120">在您建立權杖頒發者並設定權杖服務之後，請執行這些命令，以確保將 SharePoint 網站的 URL 替換為範例 URLhttp://atl-sharepoint-001:</span><span class="sxs-lookup"><span data-stu-id="d7c91-120">After you have created the token issuer and configured the token service, run these commands, making sure to substitute the URL of your SharePoint site for the sample URL http://atl-sharepoint-001:</span></span>

    $exchange = Get-SPTrustedSecurityTokenIssuer "Exchange"
    $app = Get-SPAppPrincipal -Site "https://atl-sharepoint-001" -NameIdentifier $exchange.NameID
    $site = Get-SPSite  "https://atl-sharepoint-001"
    Set-SPAppPrincipalPermission -AppPrincipal $app -Site $site.RootWeb -Scope "SiteSubscription" -Right "FullControl" -EnableAppOnlyPolicy

<span data-ttu-id="d7c91-121">若要設定 Exchange 2013 的伺服器對伺服器驗證，請開啟 Exchange 管理命令介面，並執行類似此的命令（假設 Exchange 已安裝在磁碟機 C：，且它使用預設的資料夾路徑）：</span><span class="sxs-lookup"><span data-stu-id="d7c91-121">To configure server-to-server authentication for Exchange 2013, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-sharepoint-001/_layouts/15/metadata/json/1' -ApplicationType SharePoint"

<span data-ttu-id="d7c91-122">在設定合作夥伴應用程式之後，建議您在所有 Exchange 信箱和用戶端存取伺服器上停止並重新啟動 Internet 資訊服務（IIS）。</span><span class="sxs-lookup"><span data-stu-id="d7c91-122">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on all your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="d7c91-123">您可以使用類似這個的命令重新開機 IIS，這會重新開機電腦 atl-exchange-001 的服務：</span><span class="sxs-lookup"><span data-stu-id="d7c91-123">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="d7c91-124">這個命令可以從 Exchange 管理命令介面或任何其他命令視窗中執行。</span><span class="sxs-lookup"><span data-stu-id="d7c91-124">This command can be run from within the Exchange Management Shell or from any other command window.</span></span>

<span data-ttu-id="d7c91-125">接著，執行如下所示的命令，這會讓指定的使用者（在此範例中為 kenmyer）在 Exchange 上執行探索的許可權：</span><span class="sxs-lookup"><span data-stu-id="d7c91-125">Next, run a command similar to the following, which gives the specified user (in this example, kenmyer) the right to do discovery on Exchange:</span></span>

    Add-RoleGroupMember "Discovery Management" -Member "kenmyer"

<span data-ttu-id="d7c91-126">在 Exchange 與 SharePoint 之間建立伺服器對伺服器驗證之後，下一步是在 SharePoint 中建立 eDiscovery 網站。</span><span class="sxs-lookup"><span data-stu-id="d7c91-126">After server-to-server authentication has been established between Exchange and SharePoint your next step is to create an eDiscovery site in SharePoint.</span></span> <span data-ttu-id="d7c91-127">若要這樣做，可以從 SharePoint 管理命令介面執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="d7c91-127">That can be done by running commands similar to these from the SharePoint Management Shell:</span></span>

    $template = Get-SPWebTemplate | Where-Object {$_.Title -eq "eDiscovery Center"}
    New-SPSite -Url "https://atl-sharepoint-001/sites/discovery" -OwnerAlias "kenmyer" -Template $Template -Name "Discovery Center"

<div>


> [!NOTE]  
> <span data-ttu-id="d7c91-128">「eDiscovery」是「電子 discovery」的簡稱，通常是指在法庭中，查看電子歸檔，以取得可供 admissible 證據的專案的處理方式。</span><span class="sxs-lookup"><span data-stu-id="d7c91-128">"eDiscovery" is short for "electronic discovery," and typically refers to the process of looking through electronic archives for items that can be "reasonably calculated to lead to admissible evidence" in a court of law.</span></span>



</div>

<span data-ttu-id="d7c91-129">新網站準備就緒後，下一步就是將 Exchange 2013 設定為充當 SharePoint 的結果來源。</span><span class="sxs-lookup"><span data-stu-id="d7c91-129">When the new site is ready, the next step is to configure Exchange 2013 to act as a result source for SharePoint.</span></span> <span data-ttu-id="d7c91-130">您可以從 [SharePoint 2013 管理中心] 頁面完成下列程式來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="d7c91-130">You can do that by completing the following procedure from the SharePoint 2013 Central Administration page:</span></span>

1.  <span data-ttu-id="d7c91-131">在 [管理中心] 頁面上，按一下 [**管理服務應用程式**]，然後按一下 [ **Search Service 應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="d7c91-131">On the Central Administration page click **Manage Service Applications** and then click **Search Service Application**.</span></span>

2.  <span data-ttu-id="d7c91-132">在 Search Service 應用程式上： [搜尋管理] 頁面上，按一下 [**結果來源**]，然後按一下 [**新增結果來源**]。</span><span class="sxs-lookup"><span data-stu-id="d7c91-132">On the Search Service Application: Search Administration page click **Result Sources** and then click **New Result Source**.</span></span>

3.  <span data-ttu-id="d7c91-133">在**新的結果來源**窗格中，在 [**名稱**] 方塊中輸入新結果來源（例如， **Microsoft Exchange**）的名稱。</span><span class="sxs-lookup"><span data-stu-id="d7c91-133">In the **New Result Source** pane enter a name for the new result source (for example, **Microsoft Exchange**) in the **Name** box.</span></span> <span data-ttu-id="d7c91-134">選取 [ **Exchange** ] 做為結果來源**通訊協定**，然後在 [ **exchange 來源 URL** ] 方塊中輸入 EXCHANGE 伺服器的 web services 來源 url。</span><span class="sxs-lookup"><span data-stu-id="d7c91-134">Select **Exchange** as the result source **Protocol**, and then enter the web services source URL for your Exchange server in the **Exchange Source URL** box.</span></span> <span data-ttu-id="d7c91-135">來源 URL 應該看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="d7c91-135">The source URL should look similar to this:</span></span>
    
    https://atl-exchange-001.litwareinc.com/ews/exchange.asmx

4.  <span data-ttu-id="d7c91-136">確認沒有選取 [**使用自動**探索]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d7c91-136">Make sure that **Use Autodiscover** is not selected, and then click **OK**.</span></span>

<span data-ttu-id="d7c91-137">最後，透過從 SharePoint Discovery 網站完成下列程式，建立新的 eDiscovery 案例和新的 eDiscovery 集（例如，https://atl-sharepoint-001/sites/discovery):</span><span class="sxs-lookup"><span data-stu-id="d7c91-137">Finally, create a new eDiscovery case and a new eDiscovery set by completing the following procedure from the SharePoint Discovery site (for example, https://atl-sharepoint-001/sites/discovery):</span></span>

1.  <span data-ttu-id="d7c91-138">在 [網站內容] 頁面上，按一下 [**建立新案例**]。</span><span class="sxs-lookup"><span data-stu-id="d7c91-138">On the Site Contents page click **Create a new case**.</span></span>

2.  <span data-ttu-id="d7c91-139">在 [網站內容]： [新增 SharePoint 網站] 頁面上，于 [**標題**] 方塊中輸入使用者的電子郵件別名（例如， **kenmyer**），然後將該 URL 新增至 [**網站位址**] 方塊。</span><span class="sxs-lookup"><span data-stu-id="d7c91-139">On the Site Contents: New SharePoint Site page, enter the user's email alias (for example, **kenmyer**) in the **Title** box, then add that same URL to the **Web Site Address** box.</span></span> <span data-ttu-id="d7c91-140">如此一來，就會產生如下所示的 URL：</span><span class="sxs-lookup"><span data-stu-id="d7c91-140">That will result in a URL similar to this:</span></span>
    
    https://atl-sharepoint-001/sites/eDiscovery/kenmyer

3.  <span data-ttu-id="d7c91-141">按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="d7c91-141">Click **Create**.</span></span>

4.  <span data-ttu-id="d7c91-142">出現 [eDiscovery 集] 頁面時，請按一下 [身分識別] 下的 [**新增專案**]，然後按 [**保留：探索**</span><span class="sxs-lookup"><span data-stu-id="d7c91-142">When the eDiscovery set page appears, click **new item** under **Identity and Preserve: Discovery Sets**.</span></span>

5.  <span data-ttu-id="d7c91-143">在 [新的：探索設定] 頁面上，于 [**探索集名稱**] 方塊中輸入使用者的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="d7c91-143">On the New: Discovery Set page, enter the user's email alias in the **Discovery Set Name** box.</span></span> <span data-ttu-id="d7c91-144">在 [**篩選**] 方塊中輸入**eDiscovery Lync\* \*\* ，然後按一下 [**新增 & 管理來源\*\*]。</span><span class="sxs-lookup"><span data-stu-id="d7c91-144">Enter **eDiscovery Lync\*** in the **Filter** box and then click **Add & Manage Sources**.</span></span>

6.  <span data-ttu-id="d7c91-145">在 [新增 & 管理來源] 頁面上，于 [**信箱**] 下的第一個文字方塊中輸入使用者的電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="d7c91-145">On the Add & Manage Sources page, enter the user's email alias in the first textbox under **Mailboxes**.</span></span> <span data-ttu-id="d7c91-146">按一下教科書旁邊的 [檢查信箱] 圖示，確認 SharePoint 可以連線至指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="d7c91-146">Click the check mailbox icon located next to the textbook to verify that SharePoint can connect to the specified mailbox.</span></span>

7.  <span data-ttu-id="d7c91-147">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d7c91-147">Click **OK**.</span></span>

8.  <span data-ttu-id="d7c91-148">在 [eDiscovery 集] 頁面上，按一下 [**儲存**] 以儲存新的 eDiscovery 集。</span><span class="sxs-lookup"><span data-stu-id="d7c91-148">On the eDiscovery set page, click **Save** to save the new eDiscovery set.</span></span>

<span data-ttu-id="d7c91-149">此時，您可以搜尋指定的信箱（kenmyer），並/或啟用就地保留，就與任何其他 SharePoint 內容或結果來源一樣。</span><span class="sxs-lookup"><span data-stu-id="d7c91-149">At this point you can search the specified mailbox (kenmyer) and/or enable In-Place holds the same way you would for any other SharePoint content or result source.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

