---
title: 使用反向 proxy 伺服器發佈 Office Web Apps Server
description: 使用反向 proxy 伺服器發佈 Office Web Apps Server。
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
ms.openlocfilehash: 888399e315d90624ba41e23e173fa33813a92b43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571729"
---
# <a name="publishing-office-web-apps-server-in-lync-server-2013-using-a-reverse-proxy-server"></a><span data-ttu-id="4091d-103">使用反向 proxy 伺服器在 Lync Server 2013 中發佈 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="4091d-103">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4091d-104">_**主題上次修改日期：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="4091d-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="4091d-105">如果要讓外部使用者 (亦即，從組織防火牆外部登入的使用者) 能夠存取 Office Web Apps Server PowerPoint 簡報，您需要使用 Office Web Apps Server 及反向 Proxy 伺服器，例如 Microsoft Forefront Threat Management Gateway。</span><span class="sxs-lookup"><span data-stu-id="4091d-105">If you want external users (that is, users logging on from outside your organization’s firewall) to have access to Office Web Apps Server PowerPoint presentations then you will need to use Office Web Apps Server and a reverse proxy server such as Microsoft Forefront Threat Management Gateway.</span></span> <span data-ttu-id="4091d-106">這也表示您將需要建立及設定網站發行規則;該規則會協助確保使用者能夠連接到伺服器。</span><span class="sxs-lookup"><span data-stu-id="4091d-106">That also means that you will need to create and configure a website publishing rule; that rule will help ensure that users are able to connect to the server.</span></span> <span data-ttu-id="4091d-107">如果您不需要提供存取權給外部使用者，則不需要設定網站發行規則。</span><span class="sxs-lookup"><span data-stu-id="4091d-107">If you do not need to provide access to external users then you do not need to configure a website publishing rule.</span></span>

<span data-ttu-id="4091d-108">若要在 Forefront Threat Management Gateway 中設定網站發行規則，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="4091d-108">To configure a website publishing rule in Forefront Threat Management Gateway complete the following procedure:</span></span>

1.  <span data-ttu-id="4091d-109">依序按一下 [開始]\*\*\*\*、[所有程式]\*\*\*\*、[Microsoft Forefront TMG]\*\*\*\* 及 [Forefront TMG 管理]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-109">Click **Start**, click **All Programs**, click **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="4091d-110">在 Forefront TMG 中，用滑鼠右鍵按一下 [防火牆原則]\*\*\*\*，指向 [新增]\*\*\*\*，然後按一下 [網站發行規則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-110">In Forefront TMG, right-click **Firewall Policy**, point to **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="4091d-111">在 [新增網頁發行規則精靈] 中，於「歡迎使用新增網頁發行規則精靈」\*\*\*\* 頁面上的 [網頁發行規則名稱]\*\*\*\* 方塊中，輸入新規則的名稱 (例如，**Office Web Apps Server Rule**) ，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-111">In the New Web Publishing Rule Wizard, on the **Welcome to the New Web Publishing Rule Wizard** page, type a name for your new rule in the **Web publishing rule name** box (for example, **Office Web Apps Server Rule**) and then click **Next**.</span></span>

4.  <span data-ttu-id="4091d-112">在「指定規則動作」\*\*\*\* 頁面上，選取 [允許]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-112">On the **Specify Rule Action** page, select **Allow** and then click **Next**.</span></span>

5.  <span data-ttu-id="4091d-113">在「發行類型」\*\*\*\* 頁面上，選取 [發行單一網站或負載平衡器]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-113">On the **Publishing Type** page, select **Publish a single Web site or load balancer** and then click **Next**.</span></span>

6.  <span data-ttu-id="4091d-114">在「伺服器連線安全性」\*\*\*\* 頁面上，選取 [使用 SSL 連線到發行的 Web 伺服器或伺服器陣列]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-114">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm** and then click **Next**.</span></span>

7.  <span data-ttu-id="4091d-p102">在「內部發行詳細資料」\*\*\*\* 頁面上的 [內部網站名稱]\*\*\*\* 方塊中，輸入 Office Web Apps 伺服器的 FQDN (例如，**officewebapps01.contoso.com**)，然後按 [下一步]\*\*\*\*。在 [內部網站名稱]\*\*\*\* 方塊中輸入的名稱，必須出現在您指派給 Office Web Apps Server 之憑證的 [主體] 欄位或 [主體替代名稱] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="4091d-p102">On the **Internal Publishing Details** page, type the FQDN of your Office Web Apps server (for example, **officewebapps01.contoso.com**) in the **Internal site name** box and then click **Next**. The name entered in the **Internal site name** box must appear in the Subject field or the Subject Alternative Name field of the certificate you have assigned to Office Web Apps Server.</span></span>

8.  <span data-ttu-id="4091d-117">在 [ **內部發行詳細資料** ] 頁面上，輸入 **/\*** \*\* (選用) \*\* ] 方塊中的路徑，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4091d-117">On the **Internal Publishing Details** page, type **/\*** in the **Path (optional)** box and then click **Next**.</span></span> <span data-ttu-id="4091d-118">/ \* 語法會協助確保發佈網站的所有資料夾與子資料夾。</span><span class="sxs-lookup"><span data-stu-id="4091d-118">The /\* syntax will help ensure that all the folders and subfolders for the site are published.</span></span>

9.  <span data-ttu-id="4091d-119">在「公用名稱詳細資料」\*\*\*\* 頁面上，從 [為右列接受要求]\*\*\*\* 下拉式清單中選取 [這個網域名稱 (在下方鍵入)]\*\*\*\*，然後在 [公用名稱] 方塊中輸入 Office Web Apps Server 的完整名稱。</span><span class="sxs-lookup"><span data-stu-id="4091d-119">On the **Public Name Details** page, select **This domain name (type below)** from the **Accept requests for** drop-down list and then type the fully qualified for your Office Web Apps Server in the Public name box.</span></span> <span data-ttu-id="4091d-120">此名稱應該是用來存取網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="4091d-120">This name should be the name used to access your website.</span></span> <span data-ttu-id="4091d-121">例如，如果您的網站是使用 URL 來存取，則 http://officewebapps01.contoso.com 您應該在 [**公用名稱**] 方塊中輸入**officewebapps01.contoso.com** 。</span><span class="sxs-lookup"><span data-stu-id="4091d-121">For example, if your site is accessed using the URL http://officewebapps01.contoso.com then you should enter **officewebapps01.contoso.com** in the **Public name** box.</span></span>

10. <span data-ttu-id="4091d-122">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-122">Click **Next**.</span></span>

11. <span data-ttu-id="4091d-123">在「選取網頁接聽程式」\*\*\*\* 頁面上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-123">On the **Select Web Listener** page, click **New**.</span></span>

12. <span data-ttu-id="4091d-124">在 [新增網頁接聽程式定義精靈] 的 [網頁接聽程式名稱]\*\*\*\* 方塊中，輸入新網頁接聽程式的名稱 (例如，**SSL**)，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-124">In the New Web Listener Definition Wizard, type a name for the new Web listener (for example, **SSL**) in the **Web listener name** box and then click **Next**.</span></span>

13. <span data-ttu-id="4091d-125">在「用戶端連線安全性」\*\*\*\* 頁面上，選取 [需要與用戶端之間的 SSL 安全連線]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-125">On the **Client Connection Security** page, select **Require SSL secured connections with clients** and then click **Next**.</span></span>

14. <span data-ttu-id="4091d-126">在「網頁接聽程式 IP 位址」\*\*\*\* 頁面上，選取 [外部]\*\*\*\*，選取 [內部]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-126">On the **Web Listener IP Addresses** page, select **External**, select **Internal**, and then click **Next**.</span></span>

15. <span data-ttu-id="4091d-127">在「接聽程式 SSL 憑證」\*\*\*\* 頁面上，選取 [在這個網頁接聽程式使用單一憑證]\*\*\*\* ，然後按一下 [選取憑證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-127">On the **Listener SSL Certificates** page, select **Use a single certificate for this Web Listener** and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="4091d-128">在 [選取憑證]\*\*\*\* 對話方塊中，選取要用於這個網頁接聽程式的憑證，然後按一下 [選取]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-128">In the **Select Certificate** dialog box, select the certificate to be used for this Web Listener and then click **Select**.</span></span>

17. <span data-ttu-id="4091d-129">在「接聽程式 SSL 憑證」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-129">On the **Listener SSL Certificates** page, click **Next**.</span></span>

18. <span data-ttu-id="4091d-130">在「驗證設定」\*\*\*\* 頁面上，從 **[選取用戶端提供憑證給 Forefront TMG 的方式]** 下拉式清單中選取 [無驗證]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-130">On the **Authentication Settings** page, select **No Authentication** from the **Select how clients will provide credentials to Forefront TMG** drop-down list, and then click **Next**.</span></span>

19. <span data-ttu-id="4091d-131">在「單一登入設定」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-131">On the **Single Sign On Settings** page, click **Next**.</span></span>

20. <span data-ttu-id="4091d-p105">在「正在完成新網頁接聽程式精靈」\*\*\*\* 頁面上，檢閱您已選擇的設定摘要。準備好時，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-p105">On the **Completing the New Web Listener Wizard** page, review the summary of the configuration choices you have made. When ready, click **Finish**.</span></span>

21. <span data-ttu-id="4091d-134">在「選取網頁接聽程式」\*\*\*\* 頁面上，按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-134">On the **Select Web Listener** page, click **Next**.</span></span>

22. <span data-ttu-id="4091d-135">在「驗證委派」\*\*\*\* 頁面上，從 [選取 Forefront TMG 用來向發行的 Web 伺服器驗證的方法]\*\*\*\* 下拉式清單中選取 [沒有委派，但用戶端可以直接驗證]\*\*\*\*，然後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-135">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly** from the **Select the method used by Forefront TMG to authenticate to the published Web server** drop-down list and then click **Next**.</span></span>

23. <span data-ttu-id="4091d-p106">在「使用者組」\*\*\*\* 頁面上，確認已列出適當的使用者組。依預設，這是 [所有使用者]\*\*\*\* 使用者組。按一下 [新增]\*\*\*\*，以新增您已定義的其他使用者組。完成後按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-p106">On the **User Sets** page, confirm that the appropriate user sets are listed. By default, this is the **All Users** user set. Click **Add** to add other user sets you may have defined. When complete, click **Next**.</span></span>

24. <span data-ttu-id="4091d-140">在「正在完成新增網頁發行規則精靈」\*\*\*\* 頁面上，按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-140">On the **Completing the New Web Publishing Rule Wizard** page, click **Finish**.</span></span>

<span data-ttu-id="4091d-p107">請注意，按一下 [完成]\*\*\*\* 並不表示您已完成程序；也就是說，這並不會自動套用或及啟用新規則。您必須按一下出現在 Forefront TMG 使用者介面中的 [套用]\*\*\*\* 按鈕。當您按一下 [套用]\*\*\*\* 時，會出現 [設定變更說明]\*\*\*\* 對話方塊。按一下該對話方塊中的 [套用]\*\*\*\*，以啟用新的發行規則。</span><span class="sxs-lookup"><span data-stu-id="4091d-p107">Note that clicking **Finish** does not mean that you completed the process; that is, this does not automatically apply and enable the new rule. Instead, you will need to click the **Apply** button that will appear in the Forefront TMG user interface. When you click **Apply** the **Configuration Change Description** dialog box will appear. Click **Apply** in that dialog box to enable the new publishing rule.</span></span>

<span data-ttu-id="4091d-145">套用您的新規則之後，您將需要對規則進行一些次要修改，以確保使用者可以使用新的 PowerPoint 簡報功能。</span><span class="sxs-lookup"><span data-stu-id="4091d-145">After your new rule has been applied, you will then need to make some minor modifications to the rule to make sure that users can use the new PowerPoint presentation capabilities.</span></span> <span data-ttu-id="4091d-146">若要執行這項作業，請完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="4091d-146">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="4091d-147">在 Forefront TMG 中，以滑鼠右鍵按一下新發行規則的名稱，然後按一下 [內容]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-147">In Forefront TMG, right-click the name of the new publishing rule and then click **Properties**.</span></span>

2.  <span data-ttu-id="4091d-148">在 [內容]\*\*\*\* 對話方塊中的 [到]\*\*\*\* 索引標籤上，選取 [轉寄原始主機標頭，而非實際標頭]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-148">In the **Properties** dialog box, on the **To** tab, select the option **Forward the original host header instead of the actual one**.</span></span>

3.  <span data-ttu-id="4091d-149">在 [流量]\*\*\*\* 索引標籤上，按一下 [篩選]\*\*\*\* ，然後按一下 [設定 HTTP]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-149">On the **Traffic** tab, click **Filtering** and then click **Configure HTTP**.</span></span>

4.  <span data-ttu-id="4091d-150">在 [設定規則的 HTTP 原則]\*\*\*\* 對話方塊中，清除 [確認正規化]\*\*\*\* 核取方塊，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-150">In the **Configuring HTTP policy for rule** dialog box, clear the **Verify normalization** check box and then click **OK**.</span></span>

5.  <span data-ttu-id="4091d-151">在 [內容]\*\*\*\* 對話方塊中，按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-151">In the **Properties** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="4091d-p109">在 Forefront TMG 中，按一下 [套用]\*\*\*\*，以啟用變更。[設定變更說明]\*\*\*\* 對話方塊出現時，按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4091d-p109">In Forefront TMG, click **Apply** to enable the changes. When the **Configuration Change Description** dialog box appears, click **Apply**.</span></span>

<span data-ttu-id="4091d-154">完成安裝之後，您可以使用在 [Lync Server 2013 中驗證 Office Web Apps server](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)的主題中的程式，測試您的 Office Web apps server。</span><span class="sxs-lookup"><span data-stu-id="4091d-154">After completing the installation you can test your Office Web Apps Server using the procedures in the topic [Validating the configuration of Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

