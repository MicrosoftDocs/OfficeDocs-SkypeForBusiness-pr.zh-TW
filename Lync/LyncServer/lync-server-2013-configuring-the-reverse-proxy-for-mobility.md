---
title: Lync Server 2013：設定行動的反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the reverse proxy for mobility
ms:assetid: 3f4a9e33-77e4-4c18-a73f-24d4bec8ea9c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690011(v=OCS.15)
ms:contentKeyID: 48183946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 657ddf0711b0a14c9ce861a0f237977c9a2369c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-reverse-proxy-for-mobility-in-lync-server-2013"></a><span data-ttu-id="fe1b4-102">在 Lync Server 2013 中設定行動的反向 Proxy</span><span class="sxs-lookup"><span data-stu-id="fe1b4-102">Configuring the reverse proxy for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe1b4-103">_**主題上次修改日期：** 2014-03-20_</span><span class="sxs-lookup"><span data-stu-id="fe1b4-103">_**Topic Last Modified:** 2014-03-20_</span></span>

<span data-ttu-id="fe1b4-104">如果您想要針對行動裝置用戶端使用自動探索，您必須針對反向 proxy 修改現有的或建立新的 web 發佈規則，無論您是否要更新反向 proxy 憑證上的 subject 備用名稱清單。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-104">If you want to use automatic discovery for mobile device clients, you need to modify an existing or create a new web publishing rule for the reverse proxy whether or not you update the subject alternative name lists on the reverse proxy certificates.</span></span>

<span data-ttu-id="fe1b4-105">如果您決定在初始的 Lync Server 2013 自動探索服務要求中使用 HTTPS，並更新反向 proxy 憑證上的消費者備用名稱清單，您必須將更新的公用憑證指派給安全通訊端層（SSL）偵聽程式（在您的反向 proxy。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-105">If you decide to use HTTPS for initial Lync Server 2013 Autodiscover Service requests and update the subject alternative names lists on the reverse proxy certificates, you need to assign the updated public certificate to the Secure Sockets Layer (SSL) Listener on your reverse proxy.</span></span> <span data-ttu-id="fe1b4-106">如需必要的消費者替換名稱專案的詳細資料，請參閱[Lync Server 2013 中行動的技術需求](lync-server-2013-technical-requirements-for-mobility.md)。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-106">For details about the required subject alternative name entries, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span> <span data-ttu-id="fe1b4-107">接著您需要修改外部 web 服務的現有偵聽程式，或為外部自動探索服務 URL 建立新的 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-107">You then need to modify the existing listener for the external web services or create a new web publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="fe1b4-108">如果您還沒有適用于前臺池之外部 Lync Server 2013 Web Services URL 的 web 發佈規則，您也必須發佈規則。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-108">If you do not already have a web publishing rule for the external Lync Server 2013 Web Services URL for your Front End pool, you also need to publish a rule for that.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe1b4-109">只要指派給監聽器的憑證包含這兩者所需的消費者名稱和消費者替換名稱，反向 proxy 發佈規則及監聽器就可以同時為外部 web 服務和自動探索服務提供服務。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-109">The reverse proxy publishing rule and listener can service both the external web services and the Autodiscover Service, as long as the certificate assigned to the listener contains the necessary subject name and subject alternative names for both.</span></span> <span data-ttu-id="fe1b4-110">如需有關網頁監聽器與發佈規則預設設定的詳細資料，請參閱<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">設定 Lync Server 2013 的反向 proxy 伺服器</A>以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-110">For details on the default configuration of the web listener and publishing rule, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> for more details.</span></span>



</div>

<span data-ttu-id="fe1b4-111">如果您決定將 HTTP 用於初始自動探索服務要求，因此您不需要更新反向 proxy 的消費者備用名稱，您必須建立或修改埠80的 web 發佈規則。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-111">If you decide to use HTTP for initial Autodiscover Service requests so that you do not need to update subject alternative names for the reverse proxy, you need to create or modify a web publishing rule for port 80.</span></span>

<span data-ttu-id="fe1b4-112">本節中的程式說明如何在 Microsoft Forefront 威脅管理閘道2010中建立或修改 web 發佈規則，以進行自動探索。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-112">The procedures in this section describe how to create or modify the web publishing rules in Microsoft Forefront Threat Management Gateway 2010 for automatic discovery.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe1b4-113">這些程式假設您已安裝標準版的 Forefront 威脅管理閘道（TMG）2010。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-113">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010.</span></span> <span data-ttu-id="fe1b4-114">如果您使用的是其他反向 proxy，程式會類似，但需要對應至協力廠商產品的檔。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-114">If you are using another reverse proxy, the procedures are similar, but will need to be mapped to the documentation for the third-party product.</span></span>



</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-the-external-autodiscover-url"></a><span data-ttu-id="fe1b4-115">建立外部自動探索 URL 的 web 發佈規則</span><span class="sxs-lookup"><span data-stu-id="fe1b4-115">To create a web publishing rule for the external Autodiscover URL</span></span>

1.  <span data-ttu-id="fe1b4-116">按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-116">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="fe1b4-117">在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-117">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="fe1b4-118">在 [**歡迎使用新的 Web 發佈規則**] 頁面上，輸入新發佈規則的顯示名稱（例如，LyncDiscoveryURL）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-118">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, LyncDiscoveryURL).</span></span>

4.  <span data-ttu-id="fe1b4-119">在 [**選取規則動作**] 頁面上，選取 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-119">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="fe1b4-120">在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-120">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="fe1b4-121">在 [**伺服器連線安全性**] 頁面上，選取 [**使用 SSL 連線至已發佈的 Web 服務器或伺服器**伺服器陣列]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-121">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="fe1b4-122">在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 中，輸入您的主管池（例如 lyncdir01）的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-122">On the **Internal Publishing Details** page, in **Internal Site name**, type the fully qualified domain name (FQDN) of your Director pool (for example, lyncdir01.contoso.local).</span></span> <span data-ttu-id="fe1b4-123">如果您是在 [前端] 池中為 [外部 Web 服務] URL 建立規則，請在 [前端] 池前面輸入硬體負載平衡器（HLB）的 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-123">If you are creating a rule for the external Web Services URL on the Front End pool, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="fe1b4-124">在 [**內部發佈詳細資料**] 頁面的 **[Path （選用）**] 中，輸入\*\* / \*\*要發行之資料夾的路徑，然後選取 **[轉寄原始主機標頭**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-124">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header**.</span></span>

9.  <span data-ttu-id="fe1b4-125">在 [**公用名稱詳細資料**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fe1b4-125">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="fe1b4-126">在 [**接受要求**] 下，選取 [**此功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-126">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="fe1b4-127">在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> （外部自動探索服務 URL）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-127">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span> <span data-ttu-id="fe1b4-128">如果您是在 [前端] 池中為 [外部 Web 服務] URL 建立規則，請在您的前端池中輸入外部 Web 服務的 FQDN （例如，lyncwebextpool01.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-128">If you are creating a rule for the external Web Services URL on the Front End pool, type the FQDN for the external Web Services on your Front End pool (for example, lyncwebextpool01.contoso.com).</span></span>
    
      - <span data-ttu-id="fe1b4-129">在 [ **Path**] \*\* /\*\* 中，輸入。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-129">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="fe1b4-130">在 [**選取網頁偵聽**程式] 頁面上的 [**網頁監聽器]** 中，選取您的現有 SSL 偵聽程式及已更新的公用證書。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-130">On **Select Web Listener** page, in **Web Listener**, select your existing SSL Listener with the updated public certificate.</span></span>

11. <span data-ttu-id="fe1b4-131">在 [**驗證委派**] 頁面上，選取 [**無委派]，但用戶端可以直接驗證**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-131">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

12. <span data-ttu-id="fe1b4-132">在 [**使用者組**] 頁面上，選取 [**所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-132">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="fe1b4-133">在 [**完成新的 Web 發佈規則嚮導]** 頁面上，確認 Web 發佈規則設定正確無誤，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-133">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="fe1b4-134">在 web 發佈規則的 Forefront TMG 清單中，按兩下您剛剛新增的新規則，以開啟 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-134">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="fe1b4-135">在 [**至**] 索引標籤上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fe1b4-135">On the **To** tab, do the following:</span></span>
    
      - <span data-ttu-id="fe1b4-136">選取 **[轉寄原始主機標頭，而不是實際主機**名]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-136">Select **Forward the original host header instead of the actual one**.</span></span>
    
      - <span data-ttu-id="fe1b4-137">選取**要求會顯示為來自 FOREFRONT TMG 電腦**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-137">Select **Requests appear to come from the Forefront TMG computer**.</span></span>

16. <span data-ttu-id="fe1b4-138">在 [**橋接**] 索引標籤上，設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="fe1b4-138">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="fe1b4-139">選取 [ **Web 服務器**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-139">Select **Web server**.</span></span>
    
      - <span data-ttu-id="fe1b4-140">選取 [**將要求重新導向至 HTTP 埠**]，然後輸入**8080**作為埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-140">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="fe1b4-141">選取 [重新**導向 SSL 埠**]，然後輸入**4443**作為埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-141">Select **Redirect requests to SSL port**, and type **4443** for the port number.</span></span>

17. <span data-ttu-id="fe1b4-142">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-142">Click **OK**.</span></span>

18. <span data-ttu-id="fe1b4-143">按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-143">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

19. <span data-ttu-id="fe1b4-144">按一下 [**測試規則**]，確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-144">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-web-publishing-rule-to-add-the-external-autodiscover-san-and-url"></a><span data-ttu-id="fe1b4-145">修改現有的 web 發佈規則，以新增外部自動探索 SAN 和 URL</span><span class="sxs-lookup"><span data-stu-id="fe1b4-145">To modify an existing web publishing rule to add the external Autodiscover SAN and URL</span></span>

1.  <span data-ttu-id="fe1b4-146">按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-146">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fe1b4-147">您將針對您擁有的每個發佈規則和偵聽程式重複進行修改。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-147">You will repeat the modification for each publishing rule and listener that you have.</span></span> <span data-ttu-id="fe1b4-148">通常，這會是前端池的一個規則和偵聽程式，另一個則是用於選用的控制器或控制器池（如果您已部署）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-148">Typically, this will be one rule and listener for the Front End pools and one for the optional Directors or Director pools, if you have deployed them.</span></span>

    
    </div>

2.  <span data-ttu-id="fe1b4-149">在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，然後按一下適用的規則。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-149">In the left pane, expand **ServerName**, right-click **Firewall Policy**, click the applicable rule.</span></span> <span data-ttu-id="fe1b4-150">按一下 [**任務**] 索引標籤上的 [**編輯選取的規則**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-150">On the **Tasks** tab, click **Edit Selected rule**.</span></span>

3.  <span data-ttu-id="fe1b4-151">在 [**公用名稱**] 索引標籤的 [**此規則適用**于] 中，選取下列網站的**要求**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-151">On the **Public Name** tab, in **This rule applies to**, select **Requests for the following Web sites**.</span></span>

4.  <span data-ttu-id="fe1b4-152">按一下 **[新增]**，輸入新的自動探索網站名稱（例如，"lyncdiscover.contoso.com"），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-152">Click **Add**, type the name of the new Autodiscover site (for example, “lyncdiscover.contoso.com”), and then click **OK**.</span></span>

5.  <span data-ttu-id="fe1b4-153">在 [**攔截器**] 索引標籤上，按一下 [**選取憑證**]，然後將新憑證指派給已新增的自動探索 SAN 專案。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-153">On the **Listener** tab, click **Select Certificate** and assign the new certificate with the added Autodiscover SAN entries.</span></span> <span data-ttu-id="fe1b4-154">關閉 [監聽器] 和 [Web 發佈] 屬性。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-154">Close the Listener and Web Publishing properties.</span></span>

6.  <span data-ttu-id="fe1b4-155">按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-155">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

7.  <span data-ttu-id="fe1b4-156">按一下 [**測試規則**]，確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-156">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

</div>

<div>

## <a name="to-create-a-web-publishing-rule-for-port-80"></a><span data-ttu-id="fe1b4-157">建立埠80的網路發佈規則</span><span class="sxs-lookup"><span data-stu-id="fe1b4-157">To create a web publishing rule for port 80</span></span>

1.  <span data-ttu-id="fe1b4-158">按一下 [**開始**]，指向 [**程式**]，指向 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront TMG 管理**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-158">Click **Start**, point to **Programs**, point to **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="fe1b4-159">在左窗格中，展開 [**伺服器名稱**]，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-159">In the left pane, expand **ServerName**, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="fe1b4-160">在 [**歡迎使用新的 Web 發佈規則**] 頁面上，輸入新發佈規則的顯示名稱（例如 [Lync 自動探索（HTTP）]）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-160">On the **Welcome to the New Web Publishing Rule** page, type a display name for the new publishing rule (for example, Lync Autodiscover (HTTP)).</span></span>

4.  <span data-ttu-id="fe1b4-161">在 [**選取規則動作**] 頁面上，選取 [**允許**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-161">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="fe1b4-162">在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-162">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="fe1b4-163">在 [**伺服器連線安全性**] 頁面上，選取 [**使用非安全連線來連線至已發佈的 Web 服務器或伺服器**伺服器陣列]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-163">On the **Server Connection Security** page, select **Use non-secured connections to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="fe1b4-164">在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 中，輸入硬體負載平衡器（HLB）在前端池前面的 VIP 位址。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-164">On the **Internal Publishing Details** page, in **Internal Site name**, type the VIP address of the Hardware Load Balancer (HLB) in front of the Front End pool.</span></span>

8.  <span data-ttu-id="fe1b4-165">在 [**內部發佈詳細資料**] 頁面的 **[Path （選用）**] 中，輸入\*\* / \*\*要發行之資料夾的路徑，然後選取 **[轉寄原始主機標頭]，而不是在 [內部網站名稱] 欄位中指定的主機名稱**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-165">On the **Internal Publishing Details** page, in **Path (optional)**, type **/\*** as the path of the folder to be published, and then select **Forward the original host header instead of the one specified in the Internal site name field**.</span></span>

9.  <span data-ttu-id="fe1b4-166">在 [**公用名稱詳細資料**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fe1b4-166">On the **Public Name Details** page, do the following:</span></span>
    
      - <span data-ttu-id="fe1b4-167">在 [**接受要求**] 下，選取 [**此功能變數名稱**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-167">Under **Accept Requests for**, select **This domain name**.</span></span>
    
      - <span data-ttu-id="fe1b4-168">在 [**公用名稱**] 中，輸入**lyncdiscover。**\<sipdomain\> （外部自動探索服務 URL）。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-168">In **Public Name**, type **lyncdiscover.**\<sipdomain\> (the external Autodiscover Service URL).</span></span>
    
      - <span data-ttu-id="fe1b4-169">在 [ **Path**] \*\* /\*\* 中，輸入。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-169">In **Path**, type **/\***.</span></span>

10. <span data-ttu-id="fe1b4-170">在 [**選取 Web 攔截器]** 頁面上的 [**網頁偵聽**程式] 中，選取網頁監聽程式，或使用新的 web 攔截器定義嚮導來建立新的。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-170">On **Select Web Listener** page, in **Web Listener**, select a Web Listener or use the New Web Listener Definition Wizard to create a new one.</span></span>

11. <span data-ttu-id="fe1b4-171">在 [**驗證委派**] 頁面上，選取 [**無委派]，而且用戶端無法直接驗證**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-171">On the **Authentication Delegation** page, select **No delegation, and client cannot authenticate directly**.</span></span>

12. <span data-ttu-id="fe1b4-172">在 [**使用者組**] 頁面上，選取 [**所有使用者**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-172">On the **User Set** page, select **All Users**.</span></span>

13. <span data-ttu-id="fe1b4-173">在 [**完成新的 Web 發佈規則嚮導]** 頁面上，確認 Web 發佈規則設定正確無誤，然後按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-173">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

14. <span data-ttu-id="fe1b4-174">在 web 發佈規則的 Forefront TMG 清單中，按兩下您剛剛新增的新規則，以開啟 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-174">In the Forefront TMG list of web publishing rules, double-click the new rule you just added to open **Properties**.</span></span>

15. <span data-ttu-id="fe1b4-175">在 [**橋接**] 索引標籤上，設定下列專案：</span><span class="sxs-lookup"><span data-stu-id="fe1b4-175">On the **Bridging** tab, configure the following:</span></span>
    
      - <span data-ttu-id="fe1b4-176">選取 [ **Web 服務器**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-176">Select **Web server**.</span></span>
    
      - <span data-ttu-id="fe1b4-177">選取 [**將要求重新導向至 HTTP 埠**]，然後輸入**8080**作為埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-177">Select **Redirect requests to HTTP port**, and type **8080** for the port number.</span></span>
    
      - <span data-ttu-id="fe1b4-178">確認沒有選取 [重新**導向 SSL 埠的重新導向要求**]。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-178">Verify that **Redirect requests to SSL port** is not selected.</span></span>

16. <span data-ttu-id="fe1b4-179">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-179">Click **OK**.</span></span>

17. <span data-ttu-id="fe1b4-180">按一下 [詳細資料] 窗格**中的 [** 套用]，儲存變更並更新配置。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-180">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

18. <span data-ttu-id="fe1b4-181">按一下 [**測試規則**]，確認您的新規則設定正確。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-181">Click **Test Rule** to verify that your new rule is set up correctly.</span></span>

19. <span data-ttu-id="fe1b4-182">確認未在任何其他 web 發佈規則上定義外部自動探索服務 URL。</span><span class="sxs-lookup"><span data-stu-id="fe1b4-182">Verify that the external Autodiscover Service URL is not defined on any other web publishing rule.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe1b4-183">請參閱</span><span class="sxs-lookup"><span data-stu-id="fe1b4-183">See Also</span></span>


[<span data-ttu-id="fe1b4-184">設定 Lync Server 2013 的反向 Proxy 伺服器</span><span class="sxs-lookup"><span data-stu-id="fe1b4-184">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)  
[<span data-ttu-id="fe1b4-185">Lync Server 2013 行動技術需求</span><span class="sxs-lookup"><span data-stu-id="fe1b4-185">Technical requirements for mobility in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-mobility.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

