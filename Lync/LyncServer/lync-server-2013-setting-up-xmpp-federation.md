---
title: Lync Server 2013：設定 XMPP 同盟
description: Lync Server 2013：設定 XMPP 同盟。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8a1fa15e399b0e0596a697420042b7504f8b791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555699"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="7d639-103">在 Lync Server 2013 中設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="7d639-103">Setting up XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d639-104">_**主題上次修改日期：** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="7d639-104">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="7d639-p101">如要在 Edge Server 上部署 XMPP Proxy，必須設定 Edge Server 用於 XMPP 同盟。若要這樣做，請執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="7d639-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="7d639-107">設定 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="7d639-107">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="7d639-108">以 Domain Admins 群組和 RTCUniversalServerAdmins 群組成員的身分，登入安裝 Lync Server 部署嚮導的電腦。</span><span class="sxs-lookup"><span data-stu-id="7d639-108">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="7d639-p102">在前端伺服器上開啟 [Lync Server 部署精靈]。依序按一下 [安裝或更新 Lync Server 系統]、[安裝或移除 Lync Server 元件]、[再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="7d639-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="7d639-p103">在 [安裝 Lync Server 元件] 中，按 [下一步]。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 [檢視記錄檔]，檢視可用的記錄檔。按一下 [完成] 完成部署。</span><span class="sxs-lookup"><span data-stu-id="7d639-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="7d639-p104">在 Edge Server 上開啟 [Lync Server 部署精靈]。依序按一下 [安裝或更新 Lync Server 系統]、[安裝或移除 Lync Server 元件]、[再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="7d639-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="7d639-p105">在 [安裝 Lync Server 元件] 中，按 [下一步]。摘要畫面會隨著動作的執行顯示各個動作。部署完成後，按一下 [檢視記錄檔]，檢視可用的記錄檔。按一下 [完成] 完成部署。</span><span class="sxs-lookup"><span data-stu-id="7d639-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="7d639-123">在 Edge Server 的 [部署精靈] 中，按一下 [步驟 3: 要求、安裝或指派憑證] 旁邊的 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="7d639-123">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d639-124">如果是第一次部署 Edge Server，則會看到 [執行] 而不是 [再執行一次]。</span><span class="sxs-lookup"><span data-stu-id="7d639-124">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="7d639-125">在 [可用憑證工作] 頁面上，按一下 [建立新憑證要求]。</span><span class="sxs-lookup"><span data-stu-id="7d639-125">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="7d639-126">在 [憑證要求] 頁面上，按一下 [外部邊緣憑證]。</span><span class="sxs-lookup"><span data-stu-id="7d639-126">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="7d639-127">在 [延遲或立即要求] 頁面上，選取 [立即準備此要求，但稍後再傳送] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7d639-127">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="7d639-128">在 [憑證要求檔案] 頁面上，輸入要儲存要求的檔案完整路徑和檔案名 (例如，c： \\ cert \_ 外部 \_ edge) 。</span><span class="sxs-lookup"><span data-stu-id="7d639-128">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="7d639-129">若要使用預設 WebServer 範本之外的其他範本，在 [指定其他憑證範本] 頁面上，選取 [針對選取的憑證授權單位使用其他憑證範本] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7d639-129">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="7d639-130">在 [名稱和安全性設定] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7d639-130">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="7d639-131">在 [易記名稱] 中，輸入憑證的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="7d639-131">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="7d639-132">在 [位元長度] 中，指定位元長度 (預設值通常是 2048)。</span><span class="sxs-lookup"><span data-stu-id="7d639-132">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="7d639-133">確認已選取 [將憑證私密金鑰標示為可匯出] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="7d639-133">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="7d639-134">在 [組織資訊] 頁面上，輸入組織的名稱和組織單位 (例如部門)。</span><span class="sxs-lookup"><span data-stu-id="7d639-134">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="7d639-135">在 [地理資訊] 頁面上，指定位置資訊。</span><span class="sxs-lookup"><span data-stu-id="7d639-135">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="7d639-p106">在 [主體名稱/主體替代名稱] 頁面上，會顯示精靈將自動填入的資訊。如果您還需要其他主體替代名稱，請在後續兩個步驟中指定。</span><span class="sxs-lookup"><span data-stu-id="7d639-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="7d639-138">在 [主體別名 (SANs) ] 頁面上的 [SIP 網域設定] 上，選取 [網域] 核取方塊以新增 SIP。\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="7d639-138">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="7d639-139">專案的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="7d639-139">entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="7d639-140">在 [設定其他主體替代名稱] 頁面上，指定其他任何需要的主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="7d639-140">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d639-p108">如果已安裝 XMPP Proxy，依照預設會在 SAN 項目中填入網域名稱 (例如 contoso.com)。如需其他項目，請在此步驟中新增。</span><span class="sxs-lookup"><span data-stu-id="7d639-p108">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="7d639-143">在 [要求摘要] 頁面上，檢閱要用來產生要求的憑證資訊。</span><span class="sxs-lookup"><span data-stu-id="7d639-143">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="7d639-144">命令執行完成後，可按一下 [檢視記錄檔] 或按 [下一步] 繼續。</span><span class="sxs-lookup"><span data-stu-id="7d639-144">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="7d639-145">在 [憑證要求檔案] 頁面上，可按一下 [檢視] 以檢視產生的憑證簽署要求 (CSR) 檔案，或按一下 [完成] 結束 [憑證精靈]。</span><span class="sxs-lookup"><span data-stu-id="7d639-145">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="7d639-146">複製要求檔案並提交公用憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="7d639-146">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="7d639-p109">在接收、匯入並指派公用憑證後，必須停止並重新啟動 Edge Server 服務。請在 Lync Server 管理主控台中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d639-p109">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="7d639-149">若要設定 DNS 以進行 XMPP 同盟，您可以將下列 SRV 記錄新增至外部 DNS： \_ XMPP-server。 \_Tcp。\<domain name\></span><span class="sxs-lookup"><span data-stu-id="7d639-149">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="7d639-150">SRV 記錄會解析為 Edge server 的 access edge FQDN，埠值為5269。</span><span class="sxs-lookup"><span data-stu-id="7d639-150">The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="7d639-151">此外，您還可以設定「A ' 主機記錄 (例如，xmpp.contoso.com) ，指向 Access Edge Server 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7d639-151">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7d639-p111">如多個網站中都有 Edge 集區，建議您新增多個 SRV 記錄用於 XMPP 同盟。為組織中每個 Edge 集區新增一個 SRV 記錄，並給予每個 SRV 記錄不同的優先順序。當所有的 Edge 集區都在執行時，XMPP 要求都會由第一優先順序的 Edge 集區來處理，但如果該 Edge 集區發生問題，就不用新增 SRV 記錄來重新取得 XMPP 同盟功能。</span><span class="sxs-lookup"><span data-stu-id="7d639-p111">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="7d639-155">如要設定新的外部存取原則來啟用所有的使用者，請在前端開啟 Lync Server 管理命令介面命令並輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d639-155">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="7d639-156">如要啟用外部使用者的 XMPP 存取，請輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d639-156">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="7d639-157">在部署 XMPP Proxy 的 Edge Server 上，開啟命令提示字元或 Windows PowerShell™命令列介面，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="7d639-157">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="7d639-158">**netstat –ano** 命令是網路統計資料命令，參數 **–ano** 會要求 netstat 顯示所有連線及聆聽連接埠 (位址和連接埠以數字格式顯示)，並顯示與每個連線相關的擁有處理程序識別碼。</span><span class="sxs-lookup"><span data-stu-id="7d639-158">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="7d639-159">字元會 **|** 定義管道至下一個命令、 **findstr**或尋找字串。</span><span class="sxs-lookup"><span data-stu-id="7d639-159">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="7d639-160">傳遞給 findstr 做為參數的數位5269和23456，會指示 findstr 搜尋 netstat 的字串5269及23456的輸出。</span><span class="sxs-lookup"><span data-stu-id="7d639-160">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="7d639-161">如果已正確設定 XMPP，則命令的結果應該會產生接聽和建立的連線，這兩種都是在外部 (埠 5269) 和 Edge Server 的內部 (埠 23456) 介面上。</span><span class="sxs-lookup"><span data-stu-id="7d639-161">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="7d639-162">如果命令沒有傳回在 5269 和 23456 建立或聆聽連接埠，請檢查下列事項：</span><span class="sxs-lookup"><span data-stu-id="7d639-162">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="7d639-163">疑難排解 XMPP 同盟</span><span class="sxs-lookup"><span data-stu-id="7d639-163">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="7d639-164">如要判斷 XMPP Proxy 是否在執行，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7d639-164">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="7d639-165">以本機系統管理員群組成員的身分，登入執行 XMPP Proxy 服務的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="7d639-165">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="7d639-166">依序按一下 **[開始]**、**[所有程式]**、**[系統管理工具]** 和 **[服務]**。</span><span class="sxs-lookup"><span data-stu-id="7d639-166">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="7d639-p113">在 [服務] 中找到 [Lync Server XMPP 轉譯閘道 Proxy]。該服務應在 **[已啟動]** 狀態。如果不是已啟動，請按一下工具列中的 **[啟動]** 圖示。該圖示顯示為指向右方的綠色箭頭。</span><span class="sxs-lookup"><span data-stu-id="7d639-p113">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="7d639-p114">確認服務已經變更為 **[已啟動]**。如果服務成功啟動，請關閉 **[服務]** 並繼續。</span><span class="sxs-lookup"><span data-stu-id="7d639-p114">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="7d639-173">如果服務未成功啟動，請從 [系統管理工具] 開啟 [事件檢視器]， 然後參考在 **[應用程式及服務記錄檔]** 下 **[Lync Server]** 部分中的錯誤和警告。</span><span class="sxs-lookup"><span data-stu-id="7d639-173">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="7d639-174">一旦 **[Lync Server XMPP 轉譯閘道]** 服務在執行，請重新檢查先前使用的 netstat 命令。</span><span class="sxs-lookup"><span data-stu-id="7d639-174">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="7d639-175">如果您未看到已建立或接聽的會話，請檢查並確定拓撲產生器中已正確設定**XMPP 同盟路由**</span><span class="sxs-lookup"><span data-stu-id="7d639-175">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="7d639-176">以 Domain Admins 群組與 RTCUniversalServerAdmins 群組成員的身分，登入安裝了拓撲產生器的電腦。</span><span class="sxs-lookup"><span data-stu-id="7d639-176">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="7d639-177">啟動拓撲產生器：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 拓撲**產生器]。</span><span class="sxs-lookup"><span data-stu-id="7d639-177">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="7d639-178">在 [拓撲產生器] 中，選取 XMPP 同盟路由的網站，並查看以確認**XMPP 同盟**的「**網站同盟路由指派**」會顯示您的 Edge Server 或 edge 集區作為選取的 XMPP 同盟路由指派。</span><span class="sxs-lookup"><span data-stu-id="7d639-178">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="7d639-179">如果路由指派不正確或未設定，請以滑鼠右鍵按一下網站，然後按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="7d639-179">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="7d639-180">選取 [XMPP 同盟] 核取方塊，然後選取正確的 Edge Server 或 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="7d639-180">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="7d639-181">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="7d639-181">Publish the topology.</span></span> <span data-ttu-id="7d639-182">如需詳細資訊，請參閱 [在 Lync Server 2013 中發行您的拓撲](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="7d639-182">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="7d639-183">雖然這不是必要的，通常不需要，但您可能會需要重新開機 Edge Server</span><span class="sxs-lookup"><span data-stu-id="7d639-183">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="7d639-184">使用先前所用的 netstat 程式，確認 Edge Server 現在正在接聽或已在埠5269和埠23456上建立會話。</span><span class="sxs-lookup"><span data-stu-id="7d639-184">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="7d639-185">如果還是沒看到預期的工作階段，請檢查 [事件檢視器] 中是否有任何可能造成通訊問題的原因。</span><span class="sxs-lookup"><span data-stu-id="7d639-185">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d639-186">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d639-186">See Also</span></span>


[<span data-ttu-id="7d639-187">Lync Server 2013 的範例 XMPP 設定– XMPP 與 Google 交談的同盟</span><span class="sxs-lookup"><span data-stu-id="7d639-187">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="7d639-188">在 Lync Server 2013 中管理 XMPP 同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="7d639-188">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

