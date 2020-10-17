---
title: Lync Server 2013：設定自動探索的反向 proxy
description: Lync Server 2013：設定自動探索的反向 proxy。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a reverse proxy for Autodiscover
ms:assetid: 1e3c3cc2-fe55-408b-99c4-c6e0a9252689
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945619(v=OCS.15)
ms:contentKeyID: 51541456
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f7873df063c526b4e51678ded02ca11d27c5e01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553949"
---
# <a name="configuring-a-reverse-proxy-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="841fe-103">在 Lync Server 2013 中設定自動探索的反向 proxy</span><span class="sxs-lookup"><span data-stu-id="841fe-103">Configuring a reverse proxy for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="841fe-104">_**主題上次修改日期：** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="841fe-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="841fe-105">自動探索及支援使用自動探索的用戶端，必須修改現有的 web 發行規則，或為反向 proxy 建立新的 web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="841fe-105">Autodiscover and the support of clients using autodiscover requires modification of an existing web publishing rule or creating a new web publishing rule for the reverse proxy.</span></span> <span data-ttu-id="841fe-106">修改或建立新的發佈規則，並不取決於決定是否要更新或不更新反向 proxy 憑證上的主體替代名稱清單。</span><span class="sxs-lookup"><span data-stu-id="841fe-106">The modification or creation of a new publishing rule is not dependent on the decision to update or not update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="841fe-107">如果您決定針對初始 Lync Server 2013 自動探索服務要求使用 HTTPS，並更新反向 proxy 憑證上的主體替代名稱清單，您必須將更新的公用憑證指派給反向 proxy 上的安全通訊端層 (SSL) 偵聽程式。</span><span class="sxs-lookup"><span data-stu-id="841fe-107">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="841fe-108">對外部 (公開) 憑證所需的更新將包括 lyncdiscover 的主體替代名稱 (SAN) \<domain name\> 專案。</span><span class="sxs-lookup"><span data-stu-id="841fe-108">The required update to the external (public) certificate will include the subject alternate name (SAN) entry for lyncdiscover.\<domain name\>.</span></span> <span data-ttu-id="841fe-109">接著，您必須修改外部 web 服務的現有監聽器，或為外部自動探索服務 URL 建立新的 web 發行規則，例如 **lyncdiscover.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="841fe-109">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL, for example **lyncdiscover.contoso.com**.</span></span> <span data-ttu-id="841fe-110">如果您的前端集區和 Director)  (集區的外部 Lync Server 2013 Web 服務 URL 尚無發行規則，則您也需要為該伺服器發行規則。</span><span class="sxs-lookup"><span data-stu-id="841fe-110">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool and Director pool (if you have deployed Directors), you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="841fe-111">反向 Proxy 發行規則與接聽程式可服務外部 Web 服務及自動探索服務，只要指派給接聽程式的憑證包含兩服務之必要的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="841fe-111">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="841fe-112">如需網頁接聽程式和發行規則之預設設定的詳細資料，請參閱 <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</A> 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="841fe-112">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="841fe-113">如果您決定使用 HTTP 來進行初始自動探索服務要求，這樣就不需要為反向 Proxy 更新主體替代名稱，則您需要為連接埠 80 建立或修改 Web 發行規則。</span><span class="sxs-lookup"><span data-stu-id="841fe-113">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="841fe-114">本節中的程序說明如何在 Microsoft Forefront Threat Management Gateway 2010 中建立或修改 Web 發行規則，以進行自動探索。</span><span class="sxs-lookup"><span data-stu-id="841fe-114">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="841fe-p104">這些程序假設您已安裝 Forefront Threat Management Gateway (TMG) 2010 Standard Edition。如果您使用其他的反向 Proxy，程序還是類似，但需要對應協力廠商產品的文件。</span><span class="sxs-lookup"><span data-stu-id="841fe-p104">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010. If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="841fe-117">為外部自動探索 URL 建立 Web 發行規則</span><span class="sxs-lookup"><span data-stu-id="841fe-117">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="841fe-118">按一下 [開始]\*\*\*\*，依序指向 [程式集]\*\*\*\* 和 [Microsoft Forefront TMG]\*\*\*\*，然後按一下 [Forefront TMG 管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-118">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="841fe-119">在左邊的窗格，展開 [伺服器名稱]\*\*\*\*，用滑鼠右鍵按一下 [防火牆原則]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [網站發行規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-119">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="841fe-120">在 [歡迎使用新增網頁發行規則]\*\*\*\* 頁面上，輸入新發行規則的顯示名稱 (例如 LyncDiscoveryURL)。</span><span class="sxs-lookup"><span data-stu-id="841fe-120">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="841fe-121">在 [選取規則動作]\*\*\*\* 頁面上，按一下 [允許]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-121">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="841fe-122">在 [發行類型]\*\*\*\* 頁面上，選取 [發行單一網站或負載平衡器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-122">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="841fe-123">在 [伺服器連線安全性]\*\*\*\* 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-123">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="841fe-124">在 [ **內部發行詳細資料** ] 頁面的 [ **內部網站名稱**] 中，輸入 Director 集區的完整功能變數名稱 (FQDN)  (例如，lyncdir01) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-124">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="841fe-125">若要為前端集區上的外部 Web 服務 URL 建立規則，請輸入前端集區的 FQDN (例如，lyncpool01 local) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-125">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN of the Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="841fe-126">在 [ **內部發行詳細資料** ] 頁面的 [ \*\*路徑 (選用) \*\*中，輸入 **/\*** 要發佈的資料夾路徑，然後選取 **[轉寄原始主機標頭**]。</span><span class="sxs-lookup"><span data-stu-id="841fe-126">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="841fe-127">在 [公用名稱詳細資料]\*\*\*\* 頁面上，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="841fe-127">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="841fe-128">在 [為右列接受要求]\*\*\*\* 底下，選取 [這個網域名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-128">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="841fe-129">在 [ **公用名稱**] 中，輸入 **lyncdiscover。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="841fe-129">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="841fe-130"> (外部自動探索服務 URL) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-130">(the external Autodiscover Service URL).</span></span> <span data-ttu-id="841fe-131">若要為前端集區上的外部 Web 服務 URL 建立規則，請在前端集區上輸入外部 Web 服務的 FQDN (例如，lyncwebextpool01.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-131">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="841fe-132">在 [ **路徑**] 中輸入 **/\*** 。</span><span class="sxs-lookup"><span data-stu-id="841fe-132">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="841fe-133">在 [選取網頁接聽程式]\*\*\*\* 頁面上的 [網頁接聽程式]\*\*\*\* 中，選取具有更新公用憑證的現存 SSL 接聽程式。</span><span class="sxs-lookup"><span data-stu-id="841fe-133">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="841fe-134">在 [驗證委派]\*\*\*\* 頁面上選取 [沒有委派，但用戶端可以直接驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="841fe-135">在 [使用者組]\*\*\*\* 頁面上，選取 [所有使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-135">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="841fe-136">在 [正在完成新網頁發行規則精靈]\*\*\*\* 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-136">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="841fe-137">在網頁發行規則的 Forefront TMG 清單中，按兩下您剛才加入的新規則，以開啟 [內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-137">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="841fe-138">在 [到]\*\*\*\* 索引標籤中，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="841fe-138">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="841fe-139">選取 [轉寄原始主機標頭而非實際標頭]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-139">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="841fe-140">選取 **[要求似乎來自 Forefront TMG 電腦]**。</span><span class="sxs-lookup"><span data-stu-id="841fe-140">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="841fe-141">在 [橋接]\*\*\*\* 索引標籤中，設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="841fe-141">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="841fe-142">選取 [Web 伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-142">Select **Web server**.</span></span>
    
      - <span data-ttu-id="841fe-143">選取 [將要求重新導向至 HTTP 連接埠]\*\*\*\*，並輸入 **8080** 作為連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="841fe-143">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="841fe-144">選取 [將要求重新導向至 SSL 連接埠]\*\*\*\*，並輸入 **4443** 作為連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="841fe-144">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="841fe-145">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-145">Click **OK**.</span></span>

18. <span data-ttu-id="841fe-146">按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。</span><span class="sxs-lookup"><span data-stu-id="841fe-146">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="841fe-147">按一下 [測試規則]\*\*\*\*，以確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="841fe-147">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="841fe-148">修改現有的 Web 發行規則以新增至外部自動探索 SAN 及 URL</span><span class="sxs-lookup"><span data-stu-id="841fe-148">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="841fe-149">按一下 [開始]\*\*\*\*，依序指向 [程式集]\*\*\*\* 和 [Microsoft Forefront TMG]\*\*\*\*，然後按一下 [Forefront TMG 管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-149">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="841fe-150">將為每個現有的發行規則及接聽程式重複此修改程序。</span><span class="sxs-lookup"><span data-stu-id="841fe-150">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="841fe-151">一般來說，這會是前端集區的一個規則和監聽器，另一個是選用的 Director 或 Director 集區（如果您已部署）。</span><span class="sxs-lookup"><span data-stu-id="841fe-151">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="841fe-p108">在左窗格中，展開 **[伺服器名稱]**，在 **[防火牆原則]** 上按右鍵，按一下適用的規則。在 **[工作]** 索引標籤上，按一下 **[編輯選取的規則]**。</span><span class="sxs-lookup"><span data-stu-id="841fe-p108">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule. On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="841fe-154">在 **[公用名稱]** 索引標籤上的 **[此規則套用對象]** 中，選取 **[對下列網站的要求]**。</span><span class="sxs-lookup"><span data-stu-id="841fe-154">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="841fe-155">按一下 **[新增]**，輸入新自動探索網站的名稱 (例如 "lyncdiscover.contoso.com")，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="841fe-155">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="841fe-p109">在 **[接聽程式]** 索引標籤上，按一下 **[選取憑證]** 並指派包含新增自動探索 SAN 項目的新憑證。關閉接聽程式與 Web 發行內容。</span><span class="sxs-lookup"><span data-stu-id="841fe-p109">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries. Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="841fe-158">按一下詳細資料窗格中的 [套用]\*\*\*\*，以儲存變更並更新設定。</span><span class="sxs-lookup"><span data-stu-id="841fe-158">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="841fe-159">按一下 [測試規則]\*\*\*\*，以確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="841fe-159">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="841fe-160">建立連接埠 80 的網頁發行規則</span><span class="sxs-lookup"><span data-stu-id="841fe-160">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="841fe-161">按一下 **[開始]**，依序指向 **[程式集]** 和 **[Microsoft Forefront TMG]**，然後按一下 **[Forefront TMG 管理]**。</span><span class="sxs-lookup"><span data-stu-id="841fe-161">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="841fe-162">在左邊的窗格，展開 [伺服器名稱]\*\*\*\*，用滑鼠右鍵按一下 [防火牆原則]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [網站發行規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-162">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="841fe-163">在 [歡迎使用新增網頁發行規則]\*\*\*\* 頁面上，輸入新發行規則的顯示名稱 (例如 Lync Autodiscover (HTTP))。</span><span class="sxs-lookup"><span data-stu-id="841fe-163">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="841fe-164">在 [選取規則動作]\*\*\*\* 頁面上，按一下 [允許]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-164">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="841fe-165">在 [發行類型]\*\*\*\* 頁面上，選取 [發行單一網站或負載平衡器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-165">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="841fe-166">在 [伺服器連線安全性]\*\*\*\* 頁面上，選取 [使用不安全的連線以連線到發行的 Web 伺服器或伺服器陣列]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-166">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="841fe-167">在 [ **內部發行詳細資料** ] 頁面的 [ **內部網站名稱**] 中，輸入前端集區的內部 Web 服務 FQDN (例如，lyncpool01 local) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-167">On the **Internal Publishing Details** page, in **Internal Site name**, type the internal Web Services FQDN for your Front End pool (for example, lyncpool01.contoso.local).</span></span>

8.  <span data-ttu-id="841fe-168">在 [ **內部發行詳細資料** ] 頁面的 [ \*\*路徑 (選用) \*\*中，輸入 **/\*** 要發佈的資料夾路徑，然後選取 **[轉寄原始主機標頭，而不是在內部網站名稱] 欄位中指定**的。</span><span class="sxs-lookup"><span data-stu-id="841fe-168">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="841fe-169">在 [公用名稱詳細資料]\*\*\*\* 頁面上，執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="841fe-169">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="841fe-170">在 [為右列接受要求]\*\*\*\* 底下，選取 [這個網域名稱]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-170">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="841fe-171">在 [ **公用名稱**] 中，輸入 **lyncdiscover。**\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="841fe-171">In **Public Name**, type **lyncdiscover.**\<sipdomain\></span></span> <span data-ttu-id="841fe-172"> (外部自動探索服務 URL) 。</span><span class="sxs-lookup"><span data-stu-id="841fe-172">(the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="841fe-173">在 [ **路徑**] 中輸入 **/\*** 。</span><span class="sxs-lookup"><span data-stu-id="841fe-173">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="841fe-174">在 [選取網頁接聽程式]\*\*\*\* 頁面上的 [網頁接聽程式]\*\*\*\* 中，選取接聽程式，或是使用 [新增網頁接聽程式定義精靈] 來建立新的接聽程式。</span><span class="sxs-lookup"><span data-stu-id="841fe-174">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="841fe-175">在 [驗證委派]\*\*\*\* 頁面上，選取 [沒有委派，用戶端無法直接驗證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-175">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="841fe-176">在 [使用者組]\*\*\*\* 頁面上，選取 [所有使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-176">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="841fe-177">在 [正在完成新網頁發行規則精靈]\*\*\*\* 頁面上，確認網頁發行規則設定正確，然後按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-177">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="841fe-178">在網頁發行規則的 Forefront TMG 清單中，按兩下您剛才加入的新規則，以開啟 [內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-178">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="841fe-179">在 [橋接]\*\*\*\* 索引標籤中，設定下列項目：</span><span class="sxs-lookup"><span data-stu-id="841fe-179">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="841fe-180">選取 [Web 伺服器]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-180">Select **Web server**.</span></span>
    
      - <span data-ttu-id="841fe-181">選取 [將要求重新導向至 HTTP 連接埠]\*\*\*\*，並輸入 **8080** 作為連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="841fe-181">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="841fe-182">確認未選取 [將要求重新導向至 SSL 連接埠]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-182">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="841fe-183">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="841fe-183">Click **OK**.</span></span>

17. <span data-ttu-id="841fe-184">按一下詳細資料窗格中的 **[套用]**，以儲存變更並更新設定。</span><span class="sxs-lookup"><span data-stu-id="841fe-184">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="841fe-185">按一下 **[測試規則]**，以確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="841fe-185">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="841fe-186">確認外部自動探索服務 URL 未定義在任何其他網頁發行規則上。</span><span class="sxs-lookup"><span data-stu-id="841fe-186">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="841fe-187">另請參閱</span><span class="sxs-lookup"><span data-stu-id="841fe-187">See Also</span></span>


[<span data-ttu-id="841fe-188">設定 Lync Server 2013 的反向 proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="841fe-188">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

