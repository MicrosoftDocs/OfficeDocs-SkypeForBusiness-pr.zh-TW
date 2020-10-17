---
title: Lync Server 2013：設定會議邀請
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bc948f81ddbc9bf4881b2188fc378315b3824ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532330"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="5d1e4-102">在 Lync Server 2013 中設定會議邀請</span><span class="sxs-lookup"><span data-stu-id="5d1e4-102">Configuring the meeting invitation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d1e4-103">_**主題上次修改日期：** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="5d1e4-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="5d1e4-104">您可以在會議邀請的本文中包含下列選用專案，以自訂 Lync 2013 線上會議增益集所傳送的會議邀請：</span><span class="sxs-lookup"><span data-stu-id="5d1e4-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="5d1e4-105">**組織的標誌** 使用 [標誌 URL] 選項，將組織的標誌新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="5d1e4-106">若會議邀請會傳送給組織外部的人員，該圖像應該位於公開提供的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="5d1e4-107">支援的影像格式為 GIF 和 JPG。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="5d1e4-108">雖然 Lync Server 2013 儲存的 URL 的圖像沒有大小限制，但為了獲得最佳結果，影像大小上限應為30圖元寬，188圖元寬。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="5d1e4-109">**自訂的** [說明] 或 [支援] 連結新增組織的 [說明] 或 [支援小組] 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="5d1e4-110">若會議邀請會傳送給組織外部的人員，URL 應該是公開可用的。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5d1e4-111">最大 URL 長度為 1 KB。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5d1e4-112">**法律免責聲明文字** 新增要顯示在所有會議邀請中的法律文字或免責聲明的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="5d1e4-113">若會議邀請會傳送給組織外部的人員，URL 應該是公開可用的。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5d1e4-114">最大 URL 長度為 1 KB。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5d1e4-115">**自訂頁腳文字** 新增將在邀請中呈現為自訂頁腳的文字。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="5d1e4-116">可以新增的文字最大長度為 2 KB。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="5d1e4-117">您可以使用 Lync Server 控制台或 Lync Server 管理命令介面來設定這些選項。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="5d1e4-118">**使用 Lync Server 控制台自訂會議邀請**</span><span class="sxs-lookup"><span data-stu-id="5d1e4-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="5d1e4-119">從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5d1e4-120">開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5d1e4-121">如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5d1e4-122">在左導覽列中，按一下 [ **會議** ]，然後按一下 [ **會議**設定]。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5d1e4-123">在 [ **會議** 設定] 頁面上，按一下 [ **新增**]，然後執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="5d1e4-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5d1e4-124">若要建立網站層級原則，請按一下 [ **網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-124">To create a site-level policy, click **Site configuration**.</span></span> <span data-ttu-id="5d1e4-125">在 [ **選取網站** ] 搜尋欄位中，輸入您要定義會議加入設定之網站的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-125">In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings.</span></span> <span data-ttu-id="5d1e4-126">在產生的網站清單中，按一下您想要的網站，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-126">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5d1e4-127">若要建立集區層級原則，請按一下 [ **集**區設定]。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-127">To create a pool-level policy, click **Pool configuration**.</span></span> <span data-ttu-id="5d1e4-128">在 [ **選取服務** ] 搜尋欄位中，輸入您要定義會議加入設定之集區服務的全部或部分名稱。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-128">In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings.</span></span> <span data-ttu-id="5d1e4-129">在產生的服務清單中，按一下您想要的集區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-129">In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="5d1e4-130">執行下列任一項作業：</span><span class="sxs-lookup"><span data-stu-id="5d1e4-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="5d1e4-131">在 [ **徽標 URL** ] 欄位中，輸入您組織之標誌圖像的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="5d1e4-132">在 [說明 **URL** ] 欄位中，輸入您組織的 [說明] 或 [支援] 網站的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="5d1e4-133">在 [ **法律文字** ] 欄位中，輸入您要包含在會議邀請中之法律文字或免責聲明的 URL。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="5d1e4-134">在 [ **自訂頁腳] 文字** 欄位中，輸入尾行文字，最多 2 KB。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="5d1e4-135">**使用 Lync Server 管理命令介面自訂會議邀請**</span><span class="sxs-lookup"><span data-stu-id="5d1e4-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="5d1e4-136">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5d1e4-137">執行 **New-CsMeetingConfiguration** 或 **Set-CsMeetingConfiguration** Cmdlet，以建立或設定會議邀請選項。</span><span class="sxs-lookup"><span data-stu-id="5d1e4-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="5d1e4-138">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="5d1e4-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

