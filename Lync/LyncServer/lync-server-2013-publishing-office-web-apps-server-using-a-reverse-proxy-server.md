---
title: 使用反向 Proxy 伺服器發佈 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing Office Web Apps Server using a reverse proxy server
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204665(v=OCS.15)
ms:contentKeyID: 48183384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a81fff75adbeadb6cfcead3316dab2c89b4269
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="a5b77-102">使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps 伺服器</span><span class="sxs-lookup"><span data-stu-id="a5b77-102">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5b77-103">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="a5b77-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="a5b77-104">如果您想要將外部使用者（也就是從組織外的防火牆以外的使用者登入），若要存取 Office Web Apps Server PowerPoint 簡報，您必須使用 Office Web Apps Server 和反向 proxy 伺服器（例如 Microsoft Forefront）。威脅管理閘道。</span><span class="sxs-lookup"><span data-stu-id="a5b77-104">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="a5b77-105">這也表示您將需要建立並設定網站發佈規則;該規則將協助確保使用者能夠連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5b77-105">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="a5b77-106">如果您不需要提供外部使用者的存取權，您就不需要設定網站發佈規則。</span><span class="sxs-lookup"><span data-stu-id="a5b77-106">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="a5b77-107">若要在 Forefront 威脅管理閘道設定網站發佈規則，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="a5b77-107">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="a5b77-108">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Forefront tmg**]，然後按一下 [ **Forefront tmg 管理**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-108">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="a5b77-109">在 Forefront TMG，以滑鼠右鍵按一下 [**防火牆原則**]，指向 [**新增**]，然後按一下 [**網站發佈規則**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-109">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="a5b77-110">在 [新增 Web 發佈規則嚮導] 的 [**歡迎使用新的 Web 發佈規則嚮導]** 頁面上，于 [ **Web 發佈規則名稱**] 方塊中輸入新規則的名稱（例如， **Office Web Apps Server 規則**），然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-110">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="a5b77-111">在 [**指定規則動作**] 頁面上，選取 [**允許**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-111">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="a5b77-112">在 [**發佈類型**] 頁面上，選取 [**發佈單一網站或負載平衡器**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-112">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="a5b77-113">在 [**伺服器連線安全性**] 頁面上，選取 [**使用 SSL 連線至已發佈的 Web 服務器或伺服器群]** ，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-113">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="a5b77-114">在 [**內部發佈詳細資料**] 頁面的 [**內部網站名稱**] 方塊中，輸入您的 Office Web Apps 伺服器（例如， **officewebapps01.contoso.com**）的 FQDN，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-114">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**.</span></span> <span data-ttu-id="a5b77-115">在 [**內部網站名稱**] 方塊中輸入的名稱，必須出現在 [主旨] 欄位中，或是您已指派給 Office Web Apps 伺服器的憑證的 [消費者替換名稱] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="a5b77-115">The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="a5b77-116">在 [**內部發佈詳細資料**] 頁面\*\* / \*\*上，輸入 [ **Path （選用）** ] 方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-116">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="a5b77-117">/\*語法可協助確保網站的所有資料夾和子資料夾都已發佈。</span><span class="sxs-lookup"><span data-stu-id="a5b77-117">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="a5b77-118">在 [**公用名稱詳細資料**] 頁面上，從 [**接受要求**] 下拉式清單中選取**此功能變數名稱（如下所示）** ，然後在 [公用名稱] 方塊中，輸入您的 Office Web Apps 伺服器的完整資格。</span><span class="sxs-lookup"><span data-stu-id="a5b77-118">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="a5b77-119">此名稱應該是用來存取您網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="a5b77-119">This name should be the name used to access your website.</span></span> <span data-ttu-id="a5b77-120">例如，如果您的網站是使用 URL http://officewebapps01.contoso.com來存取，則您應該在 [**公用名稱**] 方塊中輸入**officewebapps01.contoso.com** 。</span><span class="sxs-lookup"><span data-stu-id="a5b77-120">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="a5b77-121">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-121">Click **Next**.</span></span>

11. <span data-ttu-id="a5b77-122">在 [**選取網頁攔截器]** 頁面上，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-122">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="a5b77-123">在 [新增 Web 攔截器定義嚮導] 的 [**網頁監聽器名稱**] 方塊中，輸入新網頁攔截器（例如， **SSL**）的名稱，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-123">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="a5b77-124">在 [**用戶端連線安全性**] 頁面上，選取 [**與用戶端要求 SSL 安全**連線]，然後按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="a5b77-124">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="a5b77-125">在 [ **Web 攔截器 IP 位址]** 頁面上，選取 [**外部**]，選取 [**內部**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-125">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="a5b77-126">在 [**偵聽程式 SSL 憑證]** 頁面上，選取 [**針對此網頁監聽程式使用單一憑證]** ，然後按一下 [**選取憑證**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-126">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="a5b77-127">在 [**選取憑證**] 對話方塊中，選取要用於此網頁監聽程式的憑證，然後按一下 [**選取**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-127">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="a5b77-128">在 [**偵聽程式 SSL 憑證]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-128">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="a5b77-129">在 [**驗證設定**] 頁面上，從 [**選取用戶端將認證給 Forefront TMG** ] 下拉式清單中選取 [**無驗證**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-129">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="a5b77-130">在 [**單一登入設定**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-130">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="a5b77-131">在 [**完成新的 Web 攔截器嚮導]** 頁面上，查看您所做的配置選項摘要。</span><span class="sxs-lookup"><span data-stu-id="a5b77-131">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made.</span></span> <span data-ttu-id="a5b77-132">準備就緒時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-132">When ready, click **Finish**.</span></span>

21. <span data-ttu-id="a5b77-133">在 [**選取網頁攔截器]** 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-133">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="a5b77-134">在 [**驗證委派**] 頁面上，選取 [**無委派]，但用戶端可以直接**從 [**選取 Forefront TMG 使用的方法來驗證到已發佈的 Web 服務器**] 下拉式清單，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-134">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="a5b77-135">在 [**使用者集**] 頁面上，確認已列出適當的使用者組。</span><span class="sxs-lookup"><span data-stu-id="a5b77-135">On the **User Sets** page, confirm that the appropriate user sets are listed.</span></span> <span data-ttu-id="a5b77-136">根據預設，這是 [**所有使用者**] 設定。</span><span class="sxs-lookup"><span data-stu-id="a5b77-136">By default, this is the **All Users** user set.</span></span> <span data-ttu-id="a5b77-137">按一下 [**新增**]，新增您可能已定義的其他使用者組。</span><span class="sxs-lookup"><span data-stu-id="a5b77-137">Click **Add** to add other user sets you may have defined.</span></span> <span data-ttu-id="a5b77-138">完成時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-138">When complete, click **Next**.</span></span>

24. <span data-ttu-id="a5b77-139">在 [**完成新的 Web 發佈規則嚮導]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-139">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="a5b77-140">請注意，按一下 **[完成]** 並不表示您已完成處理常式;也就是說，這不會自動套用並啟用新的規則。</span><span class="sxs-lookup"><span data-stu-id="a5b77-140">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule.</span></span> <span data-ttu-id="a5b77-141">相反地，您需要按一下將出現在 Forefront TMG 使用者介面中**的 [套用**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a5b77-141">Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface.</span></span> <span data-ttu-id="a5b77-142">當您按一下 [套用設定**變更描述**] 對話方塊**時，就**會出現此對話方塊。</span><span class="sxs-lookup"><span data-stu-id="a5b77-142">When you click **Apply** the **Configuration Change Description** dialog box will appear.</span></span> <span data-ttu-id="a5b77-143">按一下**該**對話方塊中的 [套用]，即可啟用新的發佈規則。</span><span class="sxs-lookup"><span data-stu-id="a5b77-143">Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="a5b77-144">套用新規則之後，您必須對規則進行一些細微的修改，以確保使用者可以使用新的 PowerPoint 簡報功能。</span><span class="sxs-lookup"><span data-stu-id="a5b77-144">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="a5b77-145">若要這樣做，請完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="a5b77-145">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="a5b77-146">在 Forefront TMG，以滑鼠右鍵按一下新發佈規則的名稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-146">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="a5b77-147">在 [**屬性**] 對話方塊中的 [**至**] 索引標籤上，選取 [**轉寄原始主機頭] （而非實際主機標頭**）。</span><span class="sxs-lookup"><span data-stu-id="a5b77-147">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="a5b77-148">在 [**流量**] 索引標籤上，按一下 [**篩選**]，然後按一下 [**設定 HTTP**]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-148">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="a5b77-149">在 [設定**HTTP 原則規則**] 對話方塊中，清除 [**驗證正常化**] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-149">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="a5b77-150">按一下 [**屬性**] 對話方塊中的 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a5b77-150">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="a5b77-151">在 Forefront TMG 中，**按一下 [** 套用] 以啟用變更。</span><span class="sxs-lookup"><span data-stu-id="a5b77-151">In Forefront TMG, click **Apply** to enable the changes.</span></span> <span data-ttu-id="a5b77-152">當 [設定**變更變更描述**] 對話方塊出現時，**請按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="a5b77-152">When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="a5b77-153">完成安裝之後，您可以使用在[Lync Server 2013 中驗證 Office Web Apps server](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)設定主題中的程式，來測試您的 Office Web apps 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a5b77-153">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

