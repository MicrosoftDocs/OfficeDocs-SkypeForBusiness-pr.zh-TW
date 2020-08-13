---
title: Lync Server 2013：設定單一內部集區的 web 發佈規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6a1d777e16827f41d9a795fde54fca49750e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="822a0-102">在 Lync Server 2013 中設定單一內部集區的 web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="822a0-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="822a0-103">_**主題上次修改日期：** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="822a0-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="822a0-104">Microsoft Forefront 威脅管理閘道2010和 Internet Information Server 應用程式要求路由 (IIS ARR) 使用網頁發行規則，將內部資源（如會議 URL）發佈至網際網路上的使用者。</span><span class="sxs-lookup"><span data-stu-id="822a0-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="822a0-105">除了虛擬目錄的 Web 服務 URLs 之外，您還必須針對簡易 URLs、LyncDiscover URL 和 Office Web Apps Server 建立發佈規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="822a0-106">針對每個簡單 URL，您必須在反向 proxy 上建立一個指向該簡易 URL 的個別規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="822a0-107">若要部署行動性並使用自動探索，您需要為外部自動探索服務 URL 建立發佈規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="822a0-108">自動探索也需要適用于 Director 集區和前端集區之外部 Lync Server Web 服務 URL 的發行規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="822a0-109">如需建立自動探索之網頁發行規則的詳細資訊，請參閱[在 Lync Server 2013 中設定行動的反向 proxy](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="822a0-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="822a0-110">請使用下列程式建立 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="822a0-111">這些程式假設您已安裝 Standard Edition 的 Forefront 威脅管理閘道 (TMG) 2010 或已安裝及設定具有應用程式要求路由 (IIS ARR) 擴充的 Internet Information Server。</span><span class="sxs-lookup"><span data-stu-id="822a0-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="822a0-112">您使用的是 TMG 或 IIS ARR。</span><span class="sxs-lookup"><span data-stu-id="822a0-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="822a0-113">在執行 TMG 2010 的電腦上建立網頁伺服器發行規則</span><span class="sxs-lookup"><span data-stu-id="822a0-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="822a0-114">依序按一下 [**開始**]、[**程式**] 和 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="822a0-115">在左窗格中，展開 [ **ServerName**]，以滑鼠右鍵按一下 [**防火牆原則**]，然後選取 [**新增**]，然後按一下 [網站**發行規則**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="822a0-116">在 [**歡迎使用新增網頁發行規則**] 頁面上，輸入發行規則 (的顯示名稱，例如，LyncServerWebDownloadsRule) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="822a0-117">在 [選取規則動作]\*\*\*\* 頁面上，按一下 [允許]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="822a0-118">在 [發行類型]\*\*\*\* 頁面上，選取 [發行單一網站或負載平衡器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="822a0-119">在 [伺服器連線安全性]\*\*\*\* 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="822a0-120">在 [**內部發行詳細資料**] 頁面的 [內部**網站名稱**] 方塊中，輸入主控會議內容和通訊錄內容之內部網頁伺服器陣列的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="822a0-121">如果您的內部伺服器為 Standard Edition server，則此 FQDN 為 Standard Edition server FQDN。</span><span class="sxs-lookup"><span data-stu-id="822a0-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="822a0-122">如果您的內部伺服器是前端集區，則此 FQDN 是硬體負載平衡器虛擬 IP (VIP) 負載平衡內部網頁伺服器陣列伺服器。</span><span class="sxs-lookup"><span data-stu-id="822a0-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="822a0-123">TMG 伺服器必須能夠將 FQDN 解析為內部網頁伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="822a0-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="822a0-124">如果 TMG 伺服器無法將 FQDN 解析為正確的 IP 位址，您可以選取<STRONG>[使用電腦名稱稱或 ip 位址連線到已發佈的伺服器]</STRONG>，然後在 [<STRONG>電腦名稱稱或</STRONG> <STRONG>ip 位址</STRONG>] 方塊中，輸入內部網頁伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="822a0-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="822a0-125">如果您這麼做，您必須確定 TMG 伺服器上的埠53已開啟，而且可以到達位於周邊網路中的 DNS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="822a0-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="822a0-126">您也可以使用本機主機檔案中的專案，以提供名稱解析。</span><span class="sxs-lookup"><span data-stu-id="822a0-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="822a0-127">在 [**內部發行詳細資料**] 頁面的 [\*\*路徑 (選用) \*\* ] 方塊中，輸入 **/\*** 要發佈之資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="822a0-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="822a0-128">在 [網站發佈嚮導] 中，您只能指定一個路徑。</span><span class="sxs-lookup"><span data-stu-id="822a0-128">In the website publishing wizard you can only specify one path.</span></span> <span data-ttu-id="822a0-129">您可以修改規則的屬性，以新增其他路徑。</span><span class="sxs-lookup"><span data-stu-id="822a0-129">Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="822a0-130">在 [**公用名稱詳細資料**] 頁面上，確認已選取 [**接受要求**] 下的 [**功能變數名稱**]，在 [**公用名稱**] 方塊中輸入 [外部 Web 服務 FQDN]。</span><span class="sxs-lookup"><span data-stu-id="822a0-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="822a0-131">在 [**選取 Web**接聽程式] 頁面上，按一下 [**新增**] 以開啟 [新增網頁接聽程式定義] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="822a0-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="822a0-132">在 [**歡迎使用新增網頁接聽程式] 嚮導**頁面上，于 [網頁接聽程式**名稱**] 方塊中輸入 [網頁接聽程式] 的名稱 (例如，LyncServerWebServers) ]。</span><span class="sxs-lookup"><span data-stu-id="822a0-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="822a0-133">在 [**用戶端連線安全性**] 頁面上，選取 [**需要與用戶端建立 SSL 安全**連線]。</span><span class="sxs-lookup"><span data-stu-id="822a0-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="822a0-134">在 [**網頁接聽程式 IP 位址]** 頁面上，選取 [**外部**]，然後按一下 [**選取 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="822a0-135">在 [**外部攔截器 IP 選擇]** 頁面上，選取**所選網路中 Forefront TMG 電腦上的 [指定的 ip 位址**]，然後選取適當的 ip 位址，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="822a0-136">在 [接聽程式**SSL 憑證]** 頁面上，選取 [**指派每個 IP 位址的憑證**]，然後選取與外部 web FQDN 相關聯的 IP 位址，然後按一下 [**選取憑證**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="822a0-137">在 [**選取憑證**] 頁面上，選取符合步驟9中指定之公用名稱的憑證，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="822a0-138">在 [**驗證設定**] 頁面上，選取 [**無驗證**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="822a0-139">在 [**單一登入設定**] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822a0-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="822a0-140">在 [**完成網頁監聽器] 嚮導**頁面上，確認 [**網頁**接聽程式] 設定正確，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="822a0-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="822a0-141">在 [驗證委派]\*\*\*\* 頁面上選取 [沒有委派，但用戶端可以直接驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="822a0-142">在 [**使用者組**] 頁面上，按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="822a0-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="822a0-143">在 [正在完成新網頁發行規則精靈]\*\*\*\* 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="822a0-144">按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。</span><span class="sxs-lookup"><span data-stu-id="822a0-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="822a0-145">在執行 IIS ARR 的電腦上建立網頁伺服器發行規則</span><span class="sxs-lookup"><span data-stu-id="822a0-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="822a0-146">將您要用於反向 proxy 的憑證系結到 HTTPS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="822a0-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="822a0-147">依序按一下 [**開始**]、[**程式**]、[系統**管理工具**]，然後按一下 [**網際網路資訊服務 (IIS) 管理員**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="822a0-148">在<A href="https://go.microsoft.com/fwlink/?linkid=293391">使用 IIS arr 做為 Lync Server 2013 的反向 Proxy</A>的 NextHop 文章中，可以找到有關部署及設定 IIS arr 的其他協助資訊、螢幕擷取畫面和指導方針。</span><span class="sxs-lookup"><span data-stu-id="822a0-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="https://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="822a0-149">若尚未匯入您要用於反向 proxy 的憑證，請將其匯入。</span><span class="sxs-lookup"><span data-stu-id="822a0-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="822a0-150">在 [ **Internet Information Services (IIS) 管理員**] 中，按一下主控台左側大小的反向 proxy 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="822a0-151">在 [ **IIS** ] 底下的 [主控台] 中，尋找 [**伺服器憑證**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="822a0-152">以滑鼠右鍵按一下 [**伺服器憑證**]，然後選取 [**開啟功能**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="822a0-153">在主控台的右側，按一下 [匯**入 ...**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="822a0-154">輸入副檔名的路徑和檔案名，或按一下 [ **...** ]。</span><span class="sxs-lookup"><span data-stu-id="822a0-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="822a0-155">以流覽憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-155">to browse for the certificate.</span></span> <span data-ttu-id="822a0-156">選取憑證，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="822a0-157">在匯出憑證和私密金鑰) 時，提供用來保護私密金鑰 (的密碼。</span><span class="sxs-lookup"><span data-stu-id="822a0-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="822a0-158">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-158">Click **OK**.</span></span> <span data-ttu-id="822a0-159">如果已成功匯入憑證，則憑證會顯示為主控台中間的專案，成為**伺服器憑證**中的專案。</span><span class="sxs-lookup"><span data-stu-id="822a0-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="822a0-160">指派供 HTTPS 使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="822a0-161">在主控台的左側，選取 IIS 伺服器的**預設**網站。</span><span class="sxs-lookup"><span data-stu-id="822a0-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="822a0-162">在右側，按一下 [系結 **...**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="822a0-163">在 [**網站**系結] 對話方塊中，按一下 [**新增 ...**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="822a0-164">在 [**類型：**] 底下的 [**新增網站**系結] 對話方塊中，選取 [ **HTTPs**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="822a0-165">選取 [HTTPs] 可讓您選取要用於 HTTPs 的憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="822a0-166">在 [ **SSL 憑證：**] 底下，選取您為反向 proxy 匯入的憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="822a0-167">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-167">Click **OK**.</span></span> <span data-ttu-id="822a0-168">然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-168">Then, click **Close**.</span></span> <span data-ttu-id="822a0-169">現在，該憑證會系結至安全通訊端層的反向 proxy (SSL) 和傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="822a0-170">[！注意] 如果您在關閉「系結憑證遺失的系結」對話方塊時收到警告，您必須尋找並匯入公用 CA 根授權憑證和任何中間 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="822a0-171">請參閱您要求憑證的公用 CA 上的指示，並遵循指示要求和匯入憑證鏈。</span><span class="sxs-lookup"><span data-stu-id="822a0-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="822a0-172">如果您從 Edge Server 匯出憑證，您可以匯出根 CA 憑證，以及與 Edge Server 關聯的任何中間 CA 憑證。</span><span class="sxs-lookup"><span data-stu-id="822a0-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="822a0-173">將根 CA 憑證匯入電腦的 (，不會與使用者存放區) 受信任的根憑證授權單位儲存區和中級憑證，加入電腦的「中級憑證授權單位」存放區。</span><span class="sxs-lookup"><span data-stu-id="822a0-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="822a0-174">在 [IIS 伺服器名稱] 底下的主控台左側，以滑鼠右鍵按一下 [**伺服器**陣列]，然後按一下 [**建立伺服器陣列 ...**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="822a0-175">如果您沒有看到 [<STRONG>伺服器</STRONG>陣列] 節點，您必須安裝應用程式要求路由。</span><span class="sxs-lookup"><span data-stu-id="822a0-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="822a0-176">如需詳細資訊，請參閱<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</A>。</span><span class="sxs-lookup"><span data-stu-id="822a0-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="822a0-177">在 [伺服器陣列中的**建立伺服器**陣列] 對話方塊的 [**伺服器陣列名稱稱**] 中，輸入名稱 (此名稱可以是識別目的的易記名稱) 第一個 URL。</span><span class="sxs-lookup"><span data-stu-id="822a0-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="822a0-178">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-178">Click **Next**.</span></span>

6.  <span data-ttu-id="822a0-179">在 [**伺服器位址**] 中的 [**新增伺服器**] 對話方塊中，輸入前端伺服器上的外部 web 服務的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="822a0-180">在這裡用來做為範例用途的名稱，與在[Lync Server 2013 中的反向 proxy、憑證摘要-反向 proxy](lync-server-2013-certificate-summary-reverse-proxy.md)的規劃區段中使用的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="822a0-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="822a0-181">參照反向 proxy 的規劃，我們輸入 FQDN `webext.contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="822a0-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="822a0-182">確認已選取 [**線上**] 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="822a0-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="822a0-183">按一下 [**新增**]，將伺服器新增至此設定之網頁伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="822a0-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="822a0-184">Lync Server 使用硬體負載平衡器來集區 Director 和前端伺服器以進行 HTTP 及 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="822a0-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="822a0-185">將伺服器新增至 IIS ARR 伺服器陣列時，您只會提供一個 FQDN。</span><span class="sxs-lookup"><span data-stu-id="822a0-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="822a0-186">FQDN 會是非集區伺服器設定中的前端伺服器或 Director，或為伺服器集區設定的硬體負載平衡器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="822a0-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="822a0-187">使用硬體負載平衡器時，唯一支援的負載平衡 HTTP 和 HTTPS 流量的方法是使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="822a0-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="822a0-188">在 [**新增伺服器**] 對話方塊中，按一下 [**高級設定 ...**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="822a0-189">這會開啟對話方塊，為設定的 FQDN 定義要求的應用程式要求路由。</span><span class="sxs-lookup"><span data-stu-id="822a0-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="822a0-190">目的是在 IIS ARR 處理要求時，重新定義所使用的埠。</span><span class="sxs-lookup"><span data-stu-id="822a0-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="822a0-191">根據預設，目的地 HTTP 埠必須定義為8080。</span><span class="sxs-lookup"><span data-stu-id="822a0-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="822a0-192">按一下目前**HTTPPort 80**的 [下一步]，然後將值設為**8080**。</span><span class="sxs-lookup"><span data-stu-id="822a0-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="822a0-193">按一下目前**HTTPsPort 443**的 [下一步]，然後將值設為**4443**。</span><span class="sxs-lookup"><span data-stu-id="822a0-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="822a0-194">在100保留**加權**參數。</span><span class="sxs-lookup"><span data-stu-id="822a0-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="822a0-195">如有需要，您可以在有基線統計資料之後重新定義指定規則的權重。</span><span class="sxs-lookup"><span data-stu-id="822a0-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="822a0-196">按一下 **[完成]** 以完成規則設定的此部分。</span><span class="sxs-lookup"><span data-stu-id="822a0-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="822a0-197">您可能會看到對話方塊重寫規則，通知您 IIS 管理員可以建立 URL 重新寫入規則，以自動將所有傳入要求路由傳送至伺服器陣列。</span><span class="sxs-lookup"><span data-stu-id="822a0-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="822a0-198">按一下 [是]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-198">Click **Yes**.</span></span> <span data-ttu-id="822a0-199">您將會手動調整規則，但是選取 [是] 會設定初始設定。</span><span class="sxs-lookup"><span data-stu-id="822a0-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="822a0-200">按一下剛才建立的伺服器陣列名稱稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="822a0-201">在 [IIS 管理員功能] 視圖中的 [**伺服器**陣列] 底下 **，按兩下 [** 快取]。</span><span class="sxs-lookup"><span data-stu-id="822a0-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="822a0-202">取消選取 [**啟用磁碟快取**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="822a0-203">按一下**右側的 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="822a0-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="822a0-204">按一下伺服器陣列的名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-204">Click the name of the server farm.</span></span> <span data-ttu-id="822a0-205">在 [IIS 管理員功能] 視圖中的 [**伺服器**陣列] 底下，按兩下 [ **Proxy**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="822a0-206">在 [Proxy 設定] 頁面上，將\*\*超時 (秒) \*\*的值變更為適合您部署的值。</span><span class="sxs-lookup"><span data-stu-id="822a0-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="822a0-207">按一下 **[** 套用] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="822a0-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="822a0-208">Proxy 超時值是一個數位，會因部署而異。</span><span class="sxs-lookup"><span data-stu-id="822a0-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="822a0-209">您應該監視您的部署，並修改用戶端的最佳體驗值。</span><span class="sxs-lookup"><span data-stu-id="822a0-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="822a0-210">您可以將值設為低200。</span><span class="sxs-lookup"><span data-stu-id="822a0-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="822a0-211">如果您在環境中支援 Lync 行動用戶端，則應該將值設為960，以允許來自 Office 365 的推播通知超時，其超時值為900。</span><span class="sxs-lookup"><span data-stu-id="822a0-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="822a0-212">您很可能會需要增加超時值，以避免用戶端在用戶端中斷連線後，如果透過 proxy 的連線不會中斷連線，則中斷用戶端的連線。</span><span class="sxs-lookup"><span data-stu-id="822a0-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="822a0-213">監視和基本對齊您環境的情況是唯一可以判斷此值的正確設定位置的唯一準確方式。</span><span class="sxs-lookup"><span data-stu-id="822a0-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="822a0-214">按一下伺服器陣列的名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-214">Click the name of the server farm.</span></span> <span data-ttu-id="822a0-215">在 [IIS 管理員功能] 視圖中的 [**伺服器**陣列] 底下，按兩下 [**路由規則**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="822a0-216">在 [路由規則] 下的 [路由規則] 對話方塊中，清除 [啟用 SSL 卸載] 旁邊的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="822a0-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="822a0-217">如果無法使用清除核取方塊的功能，請選取 [使用 URL 重新寫入] 核取方塊以**檢查傳入的要求**。</span><span class="sxs-lookup"><span data-stu-id="822a0-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="822a0-218">按一下 **[** 套用] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="822a0-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="822a0-219">反向 proxy 不支援進行 SSL 卸載。</span><span class="sxs-lookup"><span data-stu-id="822a0-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="822a0-220">針對必須透過反向 proxy 傳遞的每個 URL，重複步驟5-11。</span><span class="sxs-lookup"><span data-stu-id="822a0-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="822a0-221">常見的清單如下：</span><span class="sxs-lookup"><span data-stu-id="822a0-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="822a0-222">前端伺服器 Web 服務外部： webext.contoso.com (已透過初始逐步進行設定) </span><span class="sxs-lookup"><span data-stu-id="822a0-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="822a0-223">Director： webdirext.contoso.com 的外部 Web 服務 director： (選用若要部署 Director) </span><span class="sxs-lookup"><span data-stu-id="822a0-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="822a0-224">簡易 URL 符合： meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="822a0-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="822a0-225">簡單 URL 撥入： dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="822a0-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="822a0-226">Lync 自動探索 URL: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="822a0-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="822a0-227">Office Web Apps Server URL: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="822a0-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="822a0-228">Office Web Apps Server 的 URL 會使用不同的 HTTPsPort 位址。</span><span class="sxs-lookup"><span data-stu-id="822a0-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="822a0-229">在步驟7中，您將<STRONG>HTTPsPort</STRONG>定義為<STRONG>443</STRONG> ，將<STRONG>HTTPPort</STRONG>定義為埠<STRONG>80</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="822a0-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="822a0-230">所有其他設定設定都相同。</span><span class="sxs-lookup"><span data-stu-id="822a0-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="822a0-231">在主控台左側，按一下 IIS 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="822a0-232">在主控台中央，找到 [ **IIS**] 底下的 [ **URL 重新寫入**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="822a0-233">按兩下 [URL 重新寫入]，以開啟 URL 重新寫入規則設定。</span><span class="sxs-lookup"><span data-stu-id="822a0-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="822a0-234">您應該會看到您在先前步驟中建立的每個伺服器陣列的規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="822a0-235">否則，請確認您已在 [網際網路資訊伺服器管理員] 主控台中，在 [**起始頁面**] 節點底下緊接著按一下**IIS 伺服器**名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="822a0-236">在 [ **URL 重新寫入**] 對話方塊中，使用 webext.contoso.com 做為範例，顯示的完整的規則名稱是**ARR \_ webext.contoso.com \_ loadbalance \_ SSL**。</span><span class="sxs-lookup"><span data-stu-id="822a0-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="822a0-237">按兩下規則以開啟 [**編輯輸入規則**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="822a0-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="822a0-238">按一下 [**新增 ...** ]</span><span class="sxs-lookup"><span data-stu-id="822a0-238">Click **Add…**</span></span> <span data-ttu-id="822a0-239">在 [**條件**] 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="822a0-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="822a0-240">在 [**條件輸入：** 輸入 **{HTTP \_ 主機}**] 中的**Add 條件**。</span><span class="sxs-lookup"><span data-stu-id="822a0-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="822a0-241"> (當您輸入時，會出現一個對話方塊，讓您選取條件) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="822a0-242">在 [**檢查輸入字串：** ] 下 **，選取 [符合模式**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="822a0-243">在**模式輸入**類型中 **\*** 。</span><span class="sxs-lookup"><span data-stu-id="822a0-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="822a0-244">應該選取 [**忽略案例**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="822a0-245">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="822a0-246">在 [**編輯輸入規則**] 對話方塊中向內移動，以找出 [**動作**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="822a0-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="822a0-247">**動作類型：** 應該設定為**路由傳送到伺服器**陣列，**配置：** 設定為**HTTPs://**，**伺服器陣列：** 設定為套用此規則的 URL。</span><span class="sxs-lookup"><span data-stu-id="822a0-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="822a0-248">在此範例中，此範例應設定為**webext.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="822a0-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="822a0-249">**路徑：** 設定為 **/{R： 0}**</span><span class="sxs-lookup"><span data-stu-id="822a0-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="822a0-250">按一下 **[** 套用] 以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="822a0-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="822a0-251">按一下 [**回到規則**] 以回到 URL 重新寫入規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="822a0-252">針對您所定義的每個 SSL 修正規則（每一個伺服器陣列 URL），重複步驟14中所定義的程式。</span><span class="sxs-lookup"><span data-stu-id="822a0-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="822a0-253">根據預設，會同時建立 HTTP 規則，並以類似于 SSL 規則的命名來表示。</span><span class="sxs-lookup"><span data-stu-id="822a0-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="822a0-254">在目前的範例中，會將 HTTP 規則命名為<STRONG>ARR_webext contoso com_loadbalance</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="822a0-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="822a0-255">不需要修改這些規則，而且可以放心地忽略。</span><span class="sxs-lookup"><span data-stu-id="822a0-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="822a0-256">在 TMG 2010 中修改 web 發行規則的屬性</span><span class="sxs-lookup"><span data-stu-id="822a0-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="822a0-257">按一下 [**開始**]，指向 [**程式**]，選取 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="822a0-258">在左窗格中，展開 [ **ServerName**]，然後按一下 [**防火牆原則**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="822a0-259">在 [詳細資料] 窗格中，以滑鼠右鍵按一下您在先前程式中建立的網頁伺服器發行規則 (例如，LyncServerExternalRule) ]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="822a0-260">在 [**屬性**] 頁面上的 [**從**] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="822a0-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="822a0-261">在 [**此規則套用至這些來源的流量**] 清單中，按一下 [**隨處**]，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="822a0-262">按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="822a0-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="822a0-263">在 [**新增網路實體**] 中，展開 [**網路**]，按一下 [**外部**]，按一下 [**新增**]，然後按一下 [**關閉**]</span><span class="sxs-lookup"><span data-stu-id="822a0-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="822a0-264">在 [**到**] 索引標籤上，確定已選取 [**轉寄原始主機標頭，而非實際的主機標頭**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="822a0-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="822a0-265">在 [**橋接**] 索引標籤上，選取 [將**要求重新導向至 SSL 埠**] 核取方塊，然後指定埠**4443**。</span><span class="sxs-lookup"><span data-stu-id="822a0-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="822a0-266">在 [**公用名稱**] 索引標籤上，新增簡易 URLs (例如，meet.contoso.com 和 dialin.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="822a0-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="822a0-267">按一下 [套用] 以儲存變更，**然後按一下** **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="822a0-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="822a0-268">按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。</span><span class="sxs-lookup"><span data-stu-id="822a0-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="822a0-269">在 IIS ARR 中修改 web 發行規則的屬性</span><span class="sxs-lookup"><span data-stu-id="822a0-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="822a0-270">依序按一下 [**開始**]、[**程式**]、[系統**管理工具**]，然後按一下 [**網際網路資訊服務 (IIS) 管理員**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="822a0-271">在主控台左側，按一下 IIS 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="822a0-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="822a0-272">在主控台中央，找到 [ **IIS**] 底下的 [ **URL 重新寫入**]。</span><span class="sxs-lookup"><span data-stu-id="822a0-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="822a0-273">按兩下 [URL 重新寫入]，以開啟 URL 重新寫入規則設定。</span><span class="sxs-lookup"><span data-stu-id="822a0-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="822a0-274">按兩下您需要修改的規則。</span><span class="sxs-lookup"><span data-stu-id="822a0-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="822a0-275">視需要在**符合 URL**、**條件**、**伺服器變數**或**動作**時進行修改。</span><span class="sxs-lookup"><span data-stu-id="822a0-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="822a0-276">按一下 **[** 套用] 以認可您的變更。</span><span class="sxs-lookup"><span data-stu-id="822a0-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="822a0-277">按一下 [**回到規則**] 修改其他規則，如果您已完成變更，請關閉 [ **IIS 管理員**] 主控台。</span><span class="sxs-lookup"><span data-stu-id="822a0-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

