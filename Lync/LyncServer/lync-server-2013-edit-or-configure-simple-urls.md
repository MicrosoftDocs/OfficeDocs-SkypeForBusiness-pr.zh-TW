---
title: Lync Server 2013：編輯或設定簡單 URLs
description: Lync Server 2013：編輯或設定簡單 URLs。
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
ms.openlocfilehash: f9152a65083f71510f4cdb1189b3982afdd68b4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551629"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="f4e8c-103">在 Lync Server 2013 中編輯或設定簡單 URLs</span><span class="sxs-lookup"><span data-stu-id="f4e8c-103">Edit or configure simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4e8c-104">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="f4e8c-104">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f4e8c-p101">此程序不需要本機系統管理員或已授權網域群組中的成員資格。您應該以標準使用者身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-p101">This procedure does not require membership in a local administrator or privileged domain group. You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="f4e8c-107">Lync Server 2013 使用簡易 URLs，將內部和外部呼叫導向前端伺服器或 Director 上的服務（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-107">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="f4e8c-108">如需簡易 URLs 的詳細資訊，請參閱規劃檔中的 [規劃 Lync Server 2013 中的簡易 URLs](lync-server-2013-planning-for-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-108">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="f4e8c-109">您可以從數個選項中選取簡單 URLs 的格式。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-109">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="f4e8c-110">如需這些選項的詳細資訊，請參閱規劃檔中的 [簡易 URLs 在 Lync Server 2013 中的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-110">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="f4e8c-111">根據預設，會以 (形式設定簡單的 URLs 例如，撥入簡易 URL) ： https://dialin 。\<SIP Domain\></span><span class="sxs-lookup"><span data-stu-id="f4e8c-111">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="f4e8c-112">若要設定簡單 URL</span><span class="sxs-lookup"><span data-stu-id="f4e8c-112">To configure simple URLs</span></span>

1.  <span data-ttu-id="f4e8c-113">在 [拓撲產生器] 中，以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-113">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f4e8c-114">在 [ **簡易 URLs** ] 窗格中，選取 [ **電話存取 URLs：** (撥入式) 或 **會議 URLs：** (符合) 進行編輯，然後按一下 [ **編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-114">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="f4e8c-115">將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-115">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="f4e8c-116">這裡顯示的範例已修改的撥入 URL https://pool01.contoso.net/dialin 。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-116">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="f4e8c-117">必要時，使用相同步驟編輯 Meet URL。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-117">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="f4e8c-118">若要定義選用的 Admin 簡單 URL</span><span class="sxs-lookup"><span data-stu-id="f4e8c-118">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="f4e8c-119">在 [拓撲產生器] 中，以滑鼠右鍵按一下 [ **Lync Server** ] 節點，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-119">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f4e8c-120">在 [系統 **管理存取 url** ] 方塊中，輸入您要用於管理存取 Lync Server 2013 控制台的簡易 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-120">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f4e8c-121">建議您盡可能使用最簡單的 URL 作為 Admin URL。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-121">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="f4e8c-122">最簡單的選項是<STRONG> https://admin 。</STRONG> &lt;網域 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-122">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4e8c-123">如果您在初始部署之後變更簡單 URL，則必須留意有哪些變更會影響簡單 URL 的網域名稱系統 (DNS) 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-123">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="f4e8c-124">如果此變更會影響簡單 URL 的基底，您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-124">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="f4e8c-125">例如，從 lync.contoso.com 變更 https://lync.contoso.com/Meet 為 https://meet.contoso.com meet.contoso.com 時，您必須變更 DNS 記錄和憑證，以參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-125">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="f4e8c-126">如果您已將簡易 URL 變更 https://lync.contoso.com/Meet 為 https://lync.contoso.com/Meetings ，lync.contoso.com 的基底 url 會保持不變，因此不需要任何 DNS 或憑證變更。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-126">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="f4e8c-127">不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 <STRONG>Enable-CsComputer</STRONG> Cmdlet，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="f4e8c-127">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4e8c-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f4e8c-128">See Also</span></span>


[<span data-ttu-id="f4e8c-129">在 Lync Server 2013 中規劃簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="f4e8c-129">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

