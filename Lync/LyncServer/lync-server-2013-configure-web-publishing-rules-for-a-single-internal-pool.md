---
title: Lync Server 2013：設定單一內部集區的 Web 發佈規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="03922-102">在 Lync Server 2013 中設定單一內部集區的 Web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="03922-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03922-103">_**主題上次修改日期：** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="03922-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="03922-104">Microsoft Forefront 威脅管理閘道2010和 Internet Information Server 應用程式要求路由（IIS ARR）使用 web 發佈規則，將內部資源（例如會議 URL）發佈給網際網路上的使用者。</span><span class="sxs-lookup"><span data-stu-id="03922-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="03922-105">除了虛擬目錄的 Web 服務 Url 之外，您也必須為簡易 Url、LyncDiscover URL 和 Office Web Apps 伺服器建立發佈規則。</span><span class="sxs-lookup"><span data-stu-id="03922-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="03922-106">針對每個簡單的 URL，您必須在指向該簡單 URL 的反向 proxy 上建立個別規則。</span><span class="sxs-lookup"><span data-stu-id="03922-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="03922-107">如果您要部署行動性並使用自動探索，您必須為外部自動探索服務 URL 建立發佈規則。</span><span class="sxs-lookup"><span data-stu-id="03922-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="03922-108">自動探索也需要適用于您主管池和前端池之外部 Lync Server Web Services URL 的發佈規則。</span><span class="sxs-lookup"><span data-stu-id="03922-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="03922-109">如需有關建立自動探索的 web 發佈規則的詳細資料，請參閱[在 Lync Server 2013 中針對行動性配置反向 proxy](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="03922-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="03922-110">使用下列程式來建立 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="03922-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="03922-111">這些程式假設您已安裝標準版的 Forefront 威脅管理閘道（TMG）2010，或已使用應用程式要求路由（IIS ARR）延伸安裝並設定 Internet information Server。</span><span class="sxs-lookup"><span data-stu-id="03922-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="03922-112">您使用的是 TMG 或 IIS ARR。</span><span class="sxs-lookup"><span data-stu-id="03922-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="03922-113">在運行 TMG 2010 的電腦上建立 web 伺服器發佈規則</span><span class="sxs-lookup"><span data-stu-id="03922-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="03922-114">按一下 [**開始**]，選取 [**程式**]，選取 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。</span><span class="sxs-lookup"><span data-stu-id="03922-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="03922-115">在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，選取 [**新增**]，然後按一下 [**網站發佈規則**]。</span><span class="sxs-lookup"><span data-stu-id="03922-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="03922-116">在 [**歡迎使用新的 Web 發佈規則**] 頁面上，輸入發佈規則的顯示名稱（例如，LyncServerWebDownloadsRule）。</span><span class="sxs-lookup"><span data-stu-id="03922-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="03922-117">在 [**選取規則動作**] 頁面上，選取 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="03922-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="03922-118">在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]。</span><span class="sxs-lookup"><span data-stu-id="03922-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="03922-119">在 [**伺服器連線安全性**] 頁面上，選取 [**使用 SSL 連線至已發佈的 Web 服務器或伺服器**伺服器陣列]。</span><span class="sxs-lookup"><span data-stu-id="03922-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="03922-120">在 [**內部發佈詳細資料**] 頁面上，在 [內部**網站名稱**] 方塊中，輸入託管會議內容和通訊錄內容的內部網頁伺服器群的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="03922-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03922-121">如果您的內部伺服器是標準版伺服器，此 FQDN 就是標準版伺服器 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03922-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="03922-122">如果您的內部伺服器是前端池，此 FQDN 是一個硬體負載平衡器虛擬 IP （VIP），負載平衡內部的網路伺服器陣列伺服器。</span><span class="sxs-lookup"><span data-stu-id="03922-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="03922-123">TMG 伺服器必須能夠將 FQDN 解析為內部 web 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="03922-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="03922-124">如果 TMG 伺服器無法將 FQDN 解析為適當的 IP 位址，您可以選取<STRONG>[使用電腦名稱稱或 ip 位址連線到已發佈的伺服器]</STRONG>，然後在 [<STRONG>電腦名稱稱或</STRONG> <STRONG>ip 位址</STRONG>] 方塊中，輸入內部 web 伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="03922-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="03922-125">如果您這樣做，您必須確認在 TMG 伺服器上已開啟埠53，而且該伺服器可以到達位於周邊網路的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="03922-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="03922-126">您也可以使用本機 hosts 檔案中的專案來提供名稱解析。</span><span class="sxs-lookup"><span data-stu-id="03922-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="03922-127">在 [**內部發佈詳細資料**] 頁面上的 [**路徑（選用）** ] \*\* / \*\*方塊中，輸入為要發佈的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="03922-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03922-128">您只能在 [網站發佈嚮導] 中指定一個路徑。</span><span class="sxs-lookup"><span data-stu-id="03922-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="03922-129">您可以透過修改規則的屬性來新增其他路徑。</span><span class="sxs-lookup"><span data-stu-id="03922-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="03922-130">在 [**公用名稱詳細資料**] 頁面上，確認已選取 [**接受要求**] 底下的 [**此功能變數名稱**]，然後在 [**公用名**] 方塊中輸入外部 Web 服務 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03922-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="03922-131">在 [**選取 Web 攔截器]** 頁面上，按一下 [**新增**] 以開啟 [新增網頁監聽器定義] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="03922-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="03922-132">在 [**歡迎使用新的 Web 攔截器嚮導]** 頁面上，于 [**網頁監聽器名稱**] 方塊中輸入網頁監聽程式的名稱（例如，LyncServerWebServers）。</span><span class="sxs-lookup"><span data-stu-id="03922-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="03922-133">在 [**用戶端連線安全性**] 頁面上，選取 [**與用戶端要求 SSL 安全**連線]。</span><span class="sxs-lookup"><span data-stu-id="03922-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="03922-134">在 [ **Web 偵聽程式 IP 位址]** 頁面上，選取 [**外部**]，然後按一下 [**選取 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="03922-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="03922-135">在 [**外部監聽器 IP 選取]** 頁面上，選取**所選網路中 Forefront TMG 電腦上的 [指定 ip 位址**]，選取適當的 ip 位址，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="03922-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="03922-136">在 [**偵聽程式 SSL 憑證]** 頁面上，**針對每個 IP 位址選取 [指派憑證**]，選取與外部 web FQDN 相關聯的 IP 位址，然後按一下 [**選取憑證**]。</span><span class="sxs-lookup"><span data-stu-id="03922-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="03922-137">在 [**選取憑證**] 頁面上，選取符合步驟9所指定之公用名稱的憑證，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="03922-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="03922-138">在 [**驗證設定**] 頁面上，選取 [**無驗證**]。</span><span class="sxs-lookup"><span data-stu-id="03922-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="03922-139">在 [**單一登入設定**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="03922-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="03922-140">在 [**完成 Web 攔截器嚮導]** 頁面上，確認**網頁監聽**程式設定正確無誤，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="03922-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="03922-141">在 [**驗證委派**] 頁面上，選取 [**無委派]，但用戶端可以直接驗證**。</span><span class="sxs-lookup"><span data-stu-id="03922-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="03922-142">在 [**使用者組**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="03922-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="03922-143">在 [**完成新的 Web 發佈規則嚮導]** 頁面上，確認 Web 發佈規則設定正確無誤，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="03922-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="03922-144">按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。</span><span class="sxs-lookup"><span data-stu-id="03922-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="03922-145">在執行 IIS ARR 的電腦上建立 web 伺服器發佈規則</span><span class="sxs-lookup"><span data-stu-id="03922-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="03922-146">將您要用於反向 proxy 的憑證系結到 HTTPS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="03922-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="03922-147">按一下 [**開始**]，選取 [**程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="03922-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03922-148">在<A href="http://go.microsoft.com/fwlink/?linkid=293391">使用 iis arr 作為 Lync Server 2013 的反向 Proxy</A>，您可以在 NextHop 文章中找到有關部署和設定 IIS ARR 的其他說明、螢幕擷取畫面及指導方針。</span><span class="sxs-lookup"><span data-stu-id="03922-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="03922-149">如果您尚未這麼做，請匯入您將用於反向 proxy 的憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="03922-150">在 **[網際網路資訊服務（IIS）管理員**] 中，按一下主機左側大小的反向 proxy 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="03922-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="03922-151">在位於主控台中間的 [ **IIS** ] 中找到 [**伺服器憑證**]。</span><span class="sxs-lookup"><span data-stu-id="03922-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="03922-152">以滑鼠右鍵按一下 [**伺服器憑證**]，然後選取 [**開啟功能**]。</span><span class="sxs-lookup"><span data-stu-id="03922-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="03922-153">在主控台右側，按一下 [匯**入 ...**]。</span><span class="sxs-lookup"><span data-stu-id="03922-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="03922-154">輸入副檔名的路徑和檔案名，或按一下 [ **...** ]。</span><span class="sxs-lookup"><span data-stu-id="03922-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="03922-155">流覽證書。</span><span class="sxs-lookup"><span data-stu-id="03922-155">to browse for the certificate.</span></span> <span data-ttu-id="03922-156">選取憑證，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="03922-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="03922-157">提供密碼來保護私用金鑰（如果您是在匯出憑證和私密金鑰時指派密碼）。</span><span class="sxs-lookup"><span data-stu-id="03922-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="03922-158">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03922-158">Click **OK**.</span></span> <span data-ttu-id="03922-159">如果已成功匯入證書，則憑證會以 [**伺服器憑證**] 中的專案的形式顯示在主控台中間。</span><span class="sxs-lookup"><span data-stu-id="03922-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="03922-160">指派供 HTTPS 使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="03922-161">在主控台的左側，選取 IIS 伺服器的**預設網站**。</span><span class="sxs-lookup"><span data-stu-id="03922-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="03922-162">按一下右側的 [系結 **...**]。</span><span class="sxs-lookup"><span data-stu-id="03922-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="03922-163">在 [**網站綁定**] 對話方塊中，按一下 [**新增 ...**]。</span><span class="sxs-lookup"><span data-stu-id="03922-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="03922-164">在 [**類型：**] 下的 [**新增網站**系結] 對話方塊中，選取 [ **HTTPs**]。</span><span class="sxs-lookup"><span data-stu-id="03922-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="03922-165">選取 [HTTPs] 可讓您選取要用於 HTTPs 的憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="03922-166">在 [ **SSL 憑證：**] 下，選取您針對反向 proxy 所匯入的憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="03922-167">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03922-167">Click **OK**.</span></span> <span data-ttu-id="03922-168">然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="03922-168">Then, click **Close**.</span></span> <span data-ttu-id="03922-169">現在，證書已系結到安全通訊端層（SSL）和傳輸層安全性（TLS）的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="03922-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03922-170">如果您在關閉中間憑證遺失的 [綁定] 對話方塊時收到警告，您必須找出並匯入公用 CA 根頒發機構憑證及任何中間 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="03922-171">請參閱您要求憑證的公用 CA 中的指示，然後依照指示要求並匯入憑證連結。</span><span class="sxs-lookup"><span data-stu-id="03922-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="03922-172">如果您是從 Edge 伺服器匯出憑證，您可以匯出根 CA 憑證以及與 Edge 伺服器相關聯的任何中間 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="03922-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="03922-173">匯入根 CA 憑證至電腦的 [（不會與使用者儲存區混淆）] 信任的根憑證授權單位儲存及中間憑證到電腦的 [中級憑證授權單位] 存放區。</span><span class="sxs-lookup"><span data-stu-id="03922-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="03922-174">在位於主控台左側的 IIS 伺服器名稱下方，以滑鼠右鍵按一下 [**伺服器群**]，然後按一下 [**建立伺服器群 ...**]。</span><span class="sxs-lookup"><span data-stu-id="03922-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03922-175">如果您沒有看到 [<STRONG>伺服器群</STRONG>] 節點，您必須安裝應用程式要求路由。</span><span class="sxs-lookup"><span data-stu-id="03922-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="03922-176">如需詳細資訊，請參閱為<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync Server 2013 設定反向 proxy 伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="03922-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="03922-177">在 [**伺服器場名稱**] 的 [**建立伺服器群**] 對話方塊中，針對第一個 URL 輸入名稱（這可以是識別用途的易記名稱）。</span><span class="sxs-lookup"><span data-stu-id="03922-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="03922-178">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="03922-178">Click **Next**.</span></span>

6.  <span data-ttu-id="03922-179">在 [**伺服器位址**] 中的 [**新增伺服器**] 對話方塊中，輸入您前端伺服器上外部 web 服務的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="03922-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="03922-180">在這裡使用的名稱，例如，在 [反向 proxy] 的 [[認證摘要-Lync Server 2013 的反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)] 中使用的名稱是一樣的。</span><span class="sxs-lookup"><span data-stu-id="03922-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="03922-181">參照反向 proxy 的規劃，我們輸入 FQDN `webext.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="03922-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="03922-182">確認已選取 [**線上**] 旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="03922-183">按一下 [**新增**]，將伺服器新增至 web 伺服器的池中，以進行這項設定。</span><span class="sxs-lookup"><span data-stu-id="03922-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="03922-184">Lync Server 使用硬體負載平衡器來為 HTTP 和 HTTPS 流量進行池控制器和前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="03922-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="03922-185">您只會在新增伺服器到 IIS ARR 伺服器群時提供一個 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03922-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="03922-186">FQDN 將是非彙集伺服器設定中的前端伺服器或主管，或伺服器池的已設定硬體負載平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="03922-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="03922-187">若要將 HTTP 和 HTTPS 流量進行負載平衡，唯一支援的方法是使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="03922-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="03922-188">在 [**新增伺服器**] 對話方塊中，按一下 [**高級設定 ...**]。</span><span class="sxs-lookup"><span data-stu-id="03922-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="03922-189">這會開啟一個對話方塊，以針對已設定的 FQDN 定義要求的應用程式要求路由。</span><span class="sxs-lookup"><span data-stu-id="03922-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="03922-190">用途是重新定義由 IIS ARR 處理要求時所使用的埠。</span><span class="sxs-lookup"><span data-stu-id="03922-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="03922-191">根據預設，目的地 HTTP 埠必須定義為8080。</span><span class="sxs-lookup"><span data-stu-id="03922-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="03922-192">按一下目前**HTTPPort 80**旁邊的，然後將值設定為**8080**。</span><span class="sxs-lookup"><span data-stu-id="03922-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="03922-193">按一下目前**HTTPsPort 443**旁邊的，然後將值設定為**4443**。</span><span class="sxs-lookup"><span data-stu-id="03922-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="03922-194">將**體重**參數留在100。</span><span class="sxs-lookup"><span data-stu-id="03922-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="03922-195">如有需要，您可以在有比較基準統計資料後，重新定義指定規則的權重。</span><span class="sxs-lookup"><span data-stu-id="03922-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="03922-196">按一下 **[完成]** 以完成這部分規則設定。</span><span class="sxs-lookup"><span data-stu-id="03922-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="03922-197">您可能會看到對話方塊重寫規則，通知您 IIS 管理員可以建立 URL 重寫規則，以便自動將所有傳入的要求路由到伺服器伺服器群。</span><span class="sxs-lookup"><span data-stu-id="03922-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="03922-198">按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="03922-198">Click **Yes**.</span></span> <span data-ttu-id="03922-199">您將會手動調整規則，但選取 [是] 會設定初始配置。</span><span class="sxs-lookup"><span data-stu-id="03922-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="03922-200">按一下您剛剛建立的伺服器伺服器陣列名稱稱。</span><span class="sxs-lookup"><span data-stu-id="03922-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="03922-201">在 IIS 管理員功能視圖的 [**伺服器場上**] 下 **，按兩下 [** 快取]。</span><span class="sxs-lookup"><span data-stu-id="03922-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="03922-202">取消選取 [**啟用磁片**快取]。</span><span class="sxs-lookup"><span data-stu-id="03922-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="03922-203">按一下**右側的 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="03922-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="03922-204">按一下伺服器伺服器陣列的名稱。</span><span class="sxs-lookup"><span data-stu-id="03922-204">Click the name of the server farm.</span></span> <span data-ttu-id="03922-205">在 [IIS 管理員功能視圖] 中的 [**伺服器場上**] 底下，按兩下 [ **Proxy**]。</span><span class="sxs-lookup"><span data-stu-id="03922-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="03922-206">在 [Proxy 設定] 頁面上，將**超時（秒）** 的值變更為適合您部署的值。</span><span class="sxs-lookup"><span data-stu-id="03922-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="03922-207">按一下 **[** 套用] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="03922-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="03922-208">Proxy 超時值是一個數位，不會因部署而異。</span><span class="sxs-lookup"><span data-stu-id="03922-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="03922-209">您應該監視您的部署並修改用戶端最佳體驗的價值。</span><span class="sxs-lookup"><span data-stu-id="03922-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="03922-210">您可以將值設為 [低] 與200。</span><span class="sxs-lookup"><span data-stu-id="03922-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="03922-211">如果您是在您的環境中支援 Lync 行動用戶端，則應該將此值設定為960，以允許從具有超時值900的 Office 365 中推播通知的超時時間。</span><span class="sxs-lookup"><span data-stu-id="03922-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="03922-212">您很可能需要增加超時值，以避免用戶端連線時中斷連線，或在用戶端中斷連線後，如果透過 proxy 的連線沒有中斷就將數位減少。</span><span class="sxs-lookup"><span data-stu-id="03922-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="03922-213">監視與基礎，對於您的環境而言是正常的，是判斷此值的正確設定所在位置的唯一精確方式。</span><span class="sxs-lookup"><span data-stu-id="03922-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="03922-214">按一下伺服器伺服器陣列的名稱。</span><span class="sxs-lookup"><span data-stu-id="03922-214">Click the name of the server farm.</span></span> <span data-ttu-id="03922-215">在 IIS 管理員功能視圖的 [**伺服器**伺服器陣列] 底下，按兩下 [**路由規則**]。</span><span class="sxs-lookup"><span data-stu-id="03922-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="03922-216">在 [路由規則] 對話方塊中的 [路由] 下，清除 [啟用 SSL 卸載] 旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="03922-217">如果無法清除該核取方塊，請選取 [**使用 URL 重寫來檢查傳入要求**] 的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="03922-218">按一下 **[** 套用] 以儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="03922-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="03922-219">不支援反向 proxy 的 SSL 卸載。</span><span class="sxs-lookup"><span data-stu-id="03922-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="03922-220">針對必須透過反向 proxy 傳送的每個 URL，重複執行步驟5-11。</span><span class="sxs-lookup"><span data-stu-id="03922-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="03922-221">常見的清單如下所示：</span><span class="sxs-lookup"><span data-stu-id="03922-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="03922-222">前端伺服器 Web 服務外部： webext.contoso.com （已由初始逐步進行設定）</span><span class="sxs-lookup"><span data-stu-id="03922-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="03922-223">主管的外部 Web 服務主管： webdirext.contoso.com （如果已部署控制器，則為選用）</span><span class="sxs-lookup"><span data-stu-id="03922-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="03922-224">簡單的 URL 開會： meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03922-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="03922-225">簡單的 URL 撥入： dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03922-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="03922-226">Lync 自動探索 URL： lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03922-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="03922-227">Office Web Apps Server URL： officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="03922-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="03922-228">Office Web Apps 伺服器的 URL 會使用不同的 HTTPsPort 位址。</span><span class="sxs-lookup"><span data-stu-id="03922-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="03922-229">在步驟7中，您將<STRONG>HTTPsPort</STRONG>定義為<STRONG>443</STRONG> ，並將<STRONG>HTTPPort</STRONG>定義為 port <STRONG>80</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03922-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="03922-230">所有其他設定都是相同的。</span><span class="sxs-lookup"><span data-stu-id="03922-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="03922-231">在主控台的左側，按一下 [IIS 伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="03922-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="03922-232">在主控台中間，找到 [ **IIS**] 下的 [ **URL 重寫**]。</span><span class="sxs-lookup"><span data-stu-id="03922-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="03922-233">按兩下 [URL 重寫]，開啟 [URL 重寫規則] 設定。</span><span class="sxs-lookup"><span data-stu-id="03922-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="03922-234">您應該會看到您在先前步驟中建立的每個伺服器伺服器陣列的規則。</span><span class="sxs-lookup"><span data-stu-id="03922-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="03922-235">如果沒有，請確認您已在 [網際網路資訊伺服器管理員] 中，按一下 [**開始頁面**] 節點下方的 [ **IIS 伺服器**名稱]。</span><span class="sxs-lookup"><span data-stu-id="03922-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="03922-236">在 [ **URL 重新寫入**] 對話方塊中，使用 webext.contoso.com 做為範例，顯示的完整規則名稱為**ARR\_webext.contoso.com\_loadbalance\_SSL**。</span><span class="sxs-lookup"><span data-stu-id="03922-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="03922-237">按兩下規則以開啟 [**編輯入站規則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="03922-238">按一下 [**新增 ...** ]。</span><span class="sxs-lookup"><span data-stu-id="03922-238">Click **Add…**</span></span> <span data-ttu-id="03922-239">在 [**條件**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="03922-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="03922-240">在 [**條件輸入**] 中的 [**新增條件**]：輸入**\_{HTTP HOST}**。</span><span class="sxs-lookup"><span data-stu-id="03922-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="03922-241">（當您輸入時，會顯示對話方塊，讓您選取條件）。</span><span class="sxs-lookup"><span data-stu-id="03922-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="03922-242">在 [**檢查輸入字串：** ] 下 **，選取 [符合模式**]。</span><span class="sxs-lookup"><span data-stu-id="03922-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="03922-243">在**模式輸入**類型**\*** 中。</span><span class="sxs-lookup"><span data-stu-id="03922-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="03922-244">應選取 [**忽略大小寫**]。</span><span class="sxs-lookup"><span data-stu-id="03922-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="03922-245">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="03922-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="03922-246">在 [**編輯入站規則**] 對話方塊中向下滾動，找出 [**動作**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="03922-247">**動作類型：** 應該設定為**路由到伺服器伺服器**陣列，**配置：** 設定為**HTTPs://**，**伺服器集群：** 設定為適用于此規則的 URL。</span><span class="sxs-lookup"><span data-stu-id="03922-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="03922-248">在這個範例中，應該將它設為**webext.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="03922-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="03922-249">**路徑：** 設定為 **/{R： 0}**</span><span class="sxs-lookup"><span data-stu-id="03922-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="03922-250">按一下 **[** 套用] 以儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="03922-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="03922-251">按一下 [**返回規則**]，回到 URL 重寫規則。</span><span class="sxs-lookup"><span data-stu-id="03922-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="03922-252">針對您所定義的每個 SSL 重寫規則（每個伺服器伺服器陣列 URL），重複步驟14中定義的程式。</span><span class="sxs-lookup"><span data-stu-id="03922-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="03922-253">根據預設，會建立 HTTP 規則，並以與 SSL 規則相似的命名來表示。</span><span class="sxs-lookup"><span data-stu-id="03922-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="03922-254">針對我們目前的範例，HTTP 規則會命名為<STRONG>ARR_webext contoso. com_loadbalance</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="03922-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="03922-255">這些規則不需要任何修改，而且可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="03922-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="03922-256">在 TMG 2010 中修改網頁發佈規則的屬性</span><span class="sxs-lookup"><span data-stu-id="03922-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="03922-257">按一下 [**開始**]，指向 [**程式**]，選取 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。</span><span class="sxs-lookup"><span data-stu-id="03922-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="03922-258">在左窗格中，展開 [**伺服器名稱**]，然後按一下 [**防火牆原則**]。</span><span class="sxs-lookup"><span data-stu-id="03922-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="03922-259">在 [詳細資料] 窗格中，以滑鼠右鍵按一下您在上述程式中建立的 web 伺服器發佈規則（例如，LyncServerExternalRule），然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="03922-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="03922-260">在 [**屬性**] 頁面的 [**從**] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="03922-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="03922-261">在 [**此規則適用于來自下列來源的流量**] 清單中，按一下 [**隨處**]，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="03922-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="03922-262">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="03922-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="03922-263">在 [**新增網路實體**] 中展開 [**網路**]，按一下 [**外部**]，按一下 [**新增**]，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="03922-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="03922-264">在 [**至**] 索引標籤上，確定已選取 [**轉寄原始主機頭]，而不**是 [實際] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="03922-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="03922-265">在 [**橋接**] 索引標籤上，選取 [重新**導向 SSL 埠要求**] 核取方塊，然後指定埠**4443**。</span><span class="sxs-lookup"><span data-stu-id="03922-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="03922-266">在 [**公用名**] 索引標籤上，新增簡單的 url （例如，meet.contoso.com 和 dialin.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="03922-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="03922-267">按一下 [套用] 以儲存變更，**然後按一下** **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="03922-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="03922-268">按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。</span><span class="sxs-lookup"><span data-stu-id="03922-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="03922-269">在 IIS ARR 中修改網頁發佈規則的屬性</span><span class="sxs-lookup"><span data-stu-id="03922-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="03922-270">按一下 [**開始**]，選取 [**程式**]，選取 [**管理工具**]，然後按一下 **[網際網路資訊服務（IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="03922-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="03922-271">在主控台的左側，按一下 [IIS 伺服器名稱]。</span><span class="sxs-lookup"><span data-stu-id="03922-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="03922-272">在主控台中間，找到 [ **IIS**] 下的 [ **URL 重寫**]。</span><span class="sxs-lookup"><span data-stu-id="03922-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="03922-273">按兩下 [URL 重寫]，開啟 [URL 重寫規則] 設定。</span><span class="sxs-lookup"><span data-stu-id="03922-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="03922-274">按兩下您需要修改的規則。</span><span class="sxs-lookup"><span data-stu-id="03922-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="03922-275">視需要在**符合 URL**、**條件**、**伺服器變數**或**動作**時，進行您的修改。</span><span class="sxs-lookup"><span data-stu-id="03922-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="03922-276">按一下 **[** 套用] 以確認您的變更。</span><span class="sxs-lookup"><span data-stu-id="03922-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="03922-277">按一下 [**返回規則**] 來修改其他規則，或者，如果您已完成變更，請關閉 [ **IIS Manager** ] 主控台。</span><span class="sxs-lookup"><span data-stu-id="03922-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

