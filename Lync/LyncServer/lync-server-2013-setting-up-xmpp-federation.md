---
title: Lync Server 2013：設定 XMPP 同盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bad6bf4e2b09296e21aec75e206ba867415754a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="20847-102">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="20847-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20847-103">_**主題上次修改日期：** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="20847-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="20847-104">若要在 Edge 伺服器上部署 XMPP Proxy，您必須針對 XMPP 同盟設定 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="20847-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="20847-105">若要這樣做，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="20847-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="20847-106">設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="20847-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="20847-107">登入 Lync Server 部署嚮導以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員的身分安裝的電腦。</span><span class="sxs-lookup"><span data-stu-id="20847-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="20847-108">在前端伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="20847-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="20847-109">按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。</span><span class="sxs-lookup"><span data-stu-id="20847-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="20847-110">再次按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="20847-110">Click Run Again.</span></span>

3.  <span data-ttu-id="20847-111">在安裝程式 Lync Server 元件上，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="20847-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="20847-112">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="20847-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="20847-113">完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="20847-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="20847-114">按一下 [完成] 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="20847-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="20847-115">在邊緣伺服器上，開啟 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="20847-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="20847-116">按一下 [安裝或更新 Lync Server 系統]，然後按一下 [設定] 或 [移除 Lync Server 元件]。</span><span class="sxs-lookup"><span data-stu-id="20847-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="20847-117">再次按一下 [執行]。</span><span class="sxs-lookup"><span data-stu-id="20847-117">Click Run Again.</span></span>

5.  <span data-ttu-id="20847-118">在安裝程式 Lync Server 元件上，按一下 [下一步]。</span><span class="sxs-lookup"><span data-stu-id="20847-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="20847-119">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="20847-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="20847-120">完成部署之後，按一下 [查看記錄] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="20847-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="20847-121">按一下 [完成] 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="20847-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="20847-122">在 Edge 伺服器的 [部署嚮導] 中，在 [步驟3：要求、安裝或指派憑證] 旁，按一下 [再次執行]。</span><span class="sxs-lookup"><span data-stu-id="20847-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="20847-123">如果您是第一次部署邊緣伺服器，您會看到 [執行]，而不是再次執行。</span><span class="sxs-lookup"><span data-stu-id="20847-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="20847-124">在 [可用的憑證工作] 頁面上，按一下 [建立新的憑證要求]。</span><span class="sxs-lookup"><span data-stu-id="20847-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="20847-125">在 [憑證要求] 頁面上，按一下 [外部邊緣憑證]。</span><span class="sxs-lookup"><span data-stu-id="20847-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="20847-126">在 [延遲] 或 [立即要求] 頁面上，選取 [立即準備要求，但稍後傳送] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="20847-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="20847-127">在 [憑證要求檔案] 頁面上，輸入要儲存申請之檔案的完整路徑和檔案名（例如，c：\\cert\_外部\_edge）。</span><span class="sxs-lookup"><span data-stu-id="20847-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="20847-128">若要使用預設 Web 文件範本以外的範本，請在 [指定備用憑證範本] 頁面上，選取 [針對所選的憑證授權單位使用替代憑證範本] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="20847-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="20847-129">在 [名稱及安全性設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="20847-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="20847-130">在 [易記名稱] 中，輸入憑證的顯示名稱</span><span class="sxs-lookup"><span data-stu-id="20847-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="20847-131">在 [位長] 中，指定位長（通常是預設值2048）</span><span class="sxs-lookup"><span data-stu-id="20847-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="20847-132">確認已選取 [將憑證私人金鑰標示為可匯出] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="20847-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="20847-133">在 [組織資訊] 頁面上，輸入組織和組織單位的名稱（例如，部門或部門）</span><span class="sxs-lookup"><span data-stu-id="20847-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="20847-134">在 [地理資訊] 頁面上，指定位置資訊</span><span class="sxs-lookup"><span data-stu-id="20847-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="20847-135">在 [Subject 名稱/主旨替換名稱] 頁面上，會顯示要由嚮導自動填入的資訊。</span><span class="sxs-lookup"><span data-stu-id="20847-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="20847-136">如果需要額外的消費者替換名稱，請在接下來的兩個步驟中加以指定。</span><span class="sxs-lookup"><span data-stu-id="20847-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="20847-137">在 [受領人替代名稱（San）] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\> [主題替換名稱] 清單中的專案。</span><span class="sxs-lookup"><span data-stu-id="20847-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="20847-138">在 [設定其他消費者替換名稱] 頁面上，指定任何所需的其他消費者替換名稱</span><span class="sxs-lookup"><span data-stu-id="20847-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="20847-139">如果已安裝 XMPP proxy，預設會在 SAN 專案中填入功能變數名稱（例如 [contoso.com]）。</span><span class="sxs-lookup"><span data-stu-id="20847-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="20847-140">如果您需要更多專案，請在此步驟中加以新增。</span><span class="sxs-lookup"><span data-stu-id="20847-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="20847-141">在 [要求摘要] 頁面上，查看要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="20847-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="20847-142">在命令完成執行之後，您可以查看記錄，或按一下 [下一步] 繼續。</span><span class="sxs-lookup"><span data-stu-id="20847-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="20847-143">在 [憑證要求檔案] 頁面上，您可以按一下 [查看] 或 [結束證書] 嚮導來查看產生的憑證簽署要求（CSR）檔案，方法是按一下 [完成]。</span><span class="sxs-lookup"><span data-stu-id="20847-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="20847-144">複製要求檔案並提交至您的公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="20847-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="20847-145">接收、匯入及指派公用憑證之後，您必須停止並重新啟動 Edge 伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="20847-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="20847-146">您可以在 Lync Server 管理主控台中輸入以下專案來執行此動作：</span><span class="sxs-lookup"><span data-stu-id="20847-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="20847-147">若要為 XMPP 同盟設定 DNS，您可以將下列 SRV 記錄新增至外部\_DNS： XMPP-伺服器。\_tcp。\<[功能變數名稱] SRV 記錄會解析為邊緣伺服器的存取邊緣 FQDN，埠值為\> 5269。</span><span class="sxs-lookup"><span data-stu-id="20847-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="20847-148">此外，您還可以設定指向存取邊緣伺服器 IP 位址的 "A" 主機記錄（例如，xmpp.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="20847-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="20847-149">如果您在多個網站中有 Edge 池，我們建議您新增多個 XMPP 同盟的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="20847-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="20847-150">為組織中的每個 Edge 池新增 SRV 記錄，並為每一個 SRV 記錄指定不同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="20847-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="20847-151">當所有邊緣池都在執行時，會使用第一個優先順序的邊緣池來處理 XMPP 要求，但如果該 Edge 池向下，您就不需要新增 SRV 記錄，就能重新取得 XMPP 聯盟功能。</span><span class="sxs-lookup"><span data-stu-id="20847-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="20847-152">在前端開啟 Lync Server 管理命令介面並輸入以下內容，以設定新的外部存取原則來啟用所有使用者：</span><span class="sxs-lookup"><span data-stu-id="20847-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="20847-153">輸入以下內容來啟用外部使用者的 XMPP 存取：</span><span class="sxs-lookup"><span data-stu-id="20847-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="20847-154">在部署 XMPP Proxy 的邊緣伺服器上，開啟命令提示字元或 Windows PowerShell™命令列介面，並輸入以下內容：</span><span class="sxs-lookup"><span data-stu-id="20847-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="20847-155">Command **netstat – ano**是 [網路統計] 命令、[參數] **– ano**要求 netstat 顯示所有連線和偵聽埠、位址和埠都以數位形式顯示，且擁有的處理常式識別碼與每個連線相關聯。</span><span class="sxs-lookup"><span data-stu-id="20847-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="20847-156">字元**|** 會定義管道至下一個命令、[ **findstr**] 或 [尋找字串]。</span><span class="sxs-lookup"><span data-stu-id="20847-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="20847-157">傳遞給 findstr 的數位5269和23456（作為參數）會指示 findstr 搜尋字串5269和23456的 netstat 輸出。</span><span class="sxs-lookup"><span data-stu-id="20847-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="20847-158">如果 XMPP 設定正確，命令的結果應該是在外部（埠5269）與 Edge 伺服器的內部（埠23456）介面上，偵聽與建立的連線。</span><span class="sxs-lookup"><span data-stu-id="20847-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="20847-159">如果命令沒有傳回已建立或在5269和23456上的偵聽埠，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="20847-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="20847-160">疑難排解 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="20847-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="20847-161">若要判斷 XMPP Proxy 是否正在執行，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="20847-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="20847-162">登入執行 XMPP Proxy 服務的邊緣伺服器作為本機管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="20847-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="20847-163">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**管理工具**]，按一下 [**服務**]</span><span class="sxs-lookup"><span data-stu-id="20847-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="20847-164">在 [服務] 中，找出 [Lync Server XMPP 翻譯閘道 Proxy]。</span><span class="sxs-lookup"><span data-stu-id="20847-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="20847-165">服務應該處於 [**已啟動**] 狀態。</span><span class="sxs-lookup"><span data-stu-id="20847-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="20847-166">如果沒有啟動，請按一下工具列中的 [**開始**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="20847-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="20847-167">圖示會顯示為綠色、向右箭號。</span><span class="sxs-lookup"><span data-stu-id="20847-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="20847-168">確認服務已變更為 [**已啟動**]。</span><span class="sxs-lookup"><span data-stu-id="20847-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="20847-169">如果它已順利啟動，請關閉 [**服務**] 並繼續。</span><span class="sxs-lookup"><span data-stu-id="20847-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="20847-170">如果 ther 服務未成功啟動，請從 [管理工具] 開啟事件檢視器，然後參閱 [**應用程式和服務記錄**] 底下的**Lync Server**部分中的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="20847-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="20847-171">在**Lync SERVER XMPP 翻譯閘道**服務執行之後，請重新檢查先前使用的 netstat 命令。</span><span class="sxs-lookup"><span data-stu-id="20847-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="20847-172">如果您沒有看到已建立或偵聽的會話，請核取並確保在拓撲建立器中正確設定**XMPP 同盟路由**</span><span class="sxs-lookup"><span data-stu-id="20847-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="20847-173">登入以 [網域管理員] 群組和 [RTCUniversalServerAdmins] 群組成員身分安裝拓撲建立器的電腦。</span><span class="sxs-lookup"><span data-stu-id="20847-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="20847-174">啟動拓撲產生器：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="20847-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="20847-175">在 [拓撲建立器] 中，選取 XMPP 同盟路由的網站，並檢查以確認**XMPP 同盟**的**網站同盟路由指派**會將您的 Edge 伺服器或 edge 池顯示為所選的 XMPP 同盟路由指派。</span><span class="sxs-lookup"><span data-stu-id="20847-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="20847-176">如果路線分派不正確或未設定，請以滑鼠右鍵按一下該網站，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="20847-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="20847-177">選取 [XMPP 聯盟] 核取方塊，然後選取正確的 [邊緣伺服器] 或 [Edge] 池。</span><span class="sxs-lookup"><span data-stu-id="20847-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="20847-178">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="20847-178">Publish the topology.</span></span> <span data-ttu-id="20847-179">如需詳細資訊，請參閱[在 Lync Server 2013 中發佈您的拓撲](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="20847-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="20847-180">雖然不需要且通常不必要，您可能會發現您需要重新開機 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="20847-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="20847-181">使用先前使用的 netstat 程式，確認 Edge 伺服器現在正在接聽，或已在埠5269和埠23456上建立會話。</span><span class="sxs-lookup"><span data-stu-id="20847-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="20847-182">如果您仍未看到預期的會話，請檢查事件檢視器，找出可能造成通訊問題的原因。</span><span class="sxs-lookup"><span data-stu-id="20847-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="20847-183">請參閱</span><span class="sxs-lookup"><span data-stu-id="20847-183">See Also</span></span>


[<span data-ttu-id="20847-184">Lync Server 2013 中的範例 XMPP 設定 – XMPP 與 Google Talk 的同盟</span><span class="sxs-lookup"><span data-stu-id="20847-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="20847-185">在 Lync Server 2013 中管理 XMPP 同盟夥伴</span><span class="sxs-lookup"><span data-stu-id="20847-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

