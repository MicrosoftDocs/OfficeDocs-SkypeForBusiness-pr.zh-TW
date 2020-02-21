---
title: Lync Server 2013： 編輯或設定簡單 Url
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e77d5ddf74d43cd277a701608e801a65262c929
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="db1d2-102">編輯或 Lync Server 2013 中設定簡單 Url</span><span class="sxs-lookup"><span data-stu-id="db1d2-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db1d2-103">_**上次修改主題：** 2014年-02-04_</span><span class="sxs-lookup"><span data-stu-id="db1d2-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="db1d2-p101">此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="db1d2-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="db1d2-106">Lync Server 2013 使用服務的直接內部和外部來電的簡單 Url Director 或前端伺服器上如果其中一個已部署。</span><span class="sxs-lookup"><span data-stu-id="db1d2-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="db1d2-107">如需簡單 Url 的詳細資訊，請參閱規劃文件中的[Planning for Lync Server 2013 中的簡單 Url](lync-server-2013-planning-for-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="db1d2-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="db1d2-108">您可以從數個選項您簡單 url 選取的格式。</span><span class="sxs-lookup"><span data-stu-id="db1d2-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="db1d2-109">如需這些選項的詳細資訊，請參閱規劃文件中的[Lync Server 2013 中的簡單 Url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="db1d2-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="db1d2-110">根據預設，會設定簡單 Url (例如，撥入簡單 URL) 的形式：https://dialin.\<SIP網域\></span><span class="sxs-lookup"><span data-stu-id="db1d2-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="db1d2-111">若要設定簡單 URL</span><span class="sxs-lookup"><span data-stu-id="db1d2-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="db1d2-112">在拓撲產生器，以滑鼠右鍵按一下 [ **Lync Server** ] 節點中，，，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="db1d2-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="db1d2-113">在 [**簡單 Url** ] 窗格中，選取 [**電話存取 Url:** （撥入） 或**會議 Url:** （符合），以編輯，然後按一下 [**編輯 URL**。</span><span class="sxs-lookup"><span data-stu-id="db1d2-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="db1d2-114">將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="db1d2-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="db1d2-115">範例如下所示已修改的撥號對應表中 URL https://pool01.contoso.net/dialin。</span><span class="sxs-lookup"><span data-stu-id="db1d2-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="db1d2-116">必要時，使用相同步驟編輯 Meet URL。</span><span class="sxs-lookup"><span data-stu-id="db1d2-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="db1d2-117">若要定義選用的 Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="db1d2-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="db1d2-118">在拓撲產生器，以滑鼠右鍵按一下 [ **Lync Server** ] 節點中，，，然後按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="db1d2-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="db1d2-119">在 [**系統管理存取 URL** ] 方塊中，輸入您想要管理存取權，Lync Server 2013 控制台，簡單 URL，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="db1d2-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="db1d2-120">建議您盡可能使用最簡單的 URL 作為 Admin URL。</span><span class="sxs-lookup"><span data-stu-id="db1d2-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="db1d2-121">最簡單的選項是<STRONG>https://admin。</STRONG>&lt;網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="db1d2-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="db1d2-122">如果您在初始部署之後變更簡單 URL，則必須留意有哪些變更會影響簡單 URL 的網域名稱系統 (DNS) 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="db1d2-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="db1d2-123">如果此變更會影響簡單 URL 的基底，您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="db1d2-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="db1d2-124">例如，從變更https://lync.contoso.com/Meet以https://meet.contoso.com基底 URL 從變成 lync.contoso.com meet.contoso.com，所以您需要變更 DNS 記錄和憑證，以參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="db1d2-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="db1d2-125">如果您變更從簡單 URLhttps://lync.contoso.com/Meet以https://lync.contoso.com/Meetings、 lync.contoso.com 的基底 URL 保持不變，因此沒有 DNS 或需要憑證的變更。</span><span class="sxs-lookup"><span data-stu-id="db1d2-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="db1d2-126">每當您變更了簡單 URL 名稱，但是，您必須執行<STRONG>Enable-cscomputer</STRONG>指令程式上每個 Director 與前端伺服器，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="db1d2-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db1d2-127">另請參閱</span><span class="sxs-lookup"><span data-stu-id="db1d2-127">See Also</span></span>


[<span data-ttu-id="db1d2-128">規劃 Lync Server 2013 中的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="db1d2-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

