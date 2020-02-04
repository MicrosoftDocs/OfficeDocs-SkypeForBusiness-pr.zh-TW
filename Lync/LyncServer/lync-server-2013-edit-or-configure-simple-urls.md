---
title: Lync Server 2013：編輯或設定簡單 URL
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a><span data-ttu-id="f11aa-102">在 Lync Server 2013 中編輯或設定簡單 URL</span><span class="sxs-lookup"><span data-stu-id="f11aa-102">Edit or configure simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f11aa-103">_**主題上次修改日期：** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="f11aa-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="f11aa-104">此程式不需要本機系統管理員或許可權網域群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="f11aa-104">This procedure does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="f11aa-105">您應該以標準使用者的身分登入電腦。</span><span class="sxs-lookup"><span data-stu-id="f11aa-105">You should log on to a computer as a standard user.</span></span>

<span data-ttu-id="f11aa-106">Lync Server 2013 使用簡單的 Url，將內部和外部呼叫直接提供給前端伺服器或主管上的服務（如果已部署）。</span><span class="sxs-lookup"><span data-stu-id="f11aa-106">Lync Server 2013 uses simple URLs to direct internal and external calls to services on the Front End Server or on the Director, if one has been deployed.</span></span> <span data-ttu-id="f11aa-107">如需簡單 Url 的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的簡單 Url 規劃](lync-server-2013-planning-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="f11aa-107">For more information about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) in the Planning documentation.</span></span> <span data-ttu-id="f11aa-108">您可以從數個選項中選取簡單 Url 的格式。</span><span class="sxs-lookup"><span data-stu-id="f11aa-108">You can select the format for your simple URLs from several options.</span></span> <span data-ttu-id="f11aa-109">如需這些選項的詳細資訊，請參閱規劃檔中的[Lync Server 2013 簡單 url 的 DNS 需求](lync-server-2013-dns-requirements-for-simple-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="f11aa-109">For details about these options, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) in the Planning documentation.</span></span>

<span data-ttu-id="f11aa-110">根據預設，簡單的 Url 會以下列形式（例如，撥入式簡單 URL）來設定： https://dialin.\<SIP網域\></span><span class="sxs-lookup"><span data-stu-id="f11aa-110">By default, simple URLs will be configured in the form of (for example, the dial-in simple URL): https://dialin.\<SIP Domain\></span></span>

<div>

## <a name="to-configure-simple-urls"></a><span data-ttu-id="f11aa-111">若要設定簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="f11aa-111">To configure simple URLs</span></span>

1.  <span data-ttu-id="f11aa-112">在拓撲建立器中，以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f11aa-112">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f11aa-113">在 [**簡易 url** ] 窗格中，選取 [**電話存取 url：** （撥入）] 或 [**會議 url：** （見面）] 進行編輯，然後按一下 [**編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="f11aa-113">In the **Simple URLs** pane, select either **Phone access URLs:** (Dial-in) or **Meeting URLs:** (Meet) to edit, and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="f11aa-114">更新 URL 至您想要的值，然後按一下 **[確定]** 以儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="f11aa-114">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> <span data-ttu-id="f11aa-115">這裡顯示的範例已修改回撥入式 URL https://pool01.contoso.net/dialin。</span><span class="sxs-lookup"><span data-stu-id="f11aa-115">The example shown here has modified the Dial-in URL to https://pool01.contoso.net/dialin.</span></span>

4.  <span data-ttu-id="f11aa-116">如有需要，請使用相同的步驟編輯 [認識 URL]。</span><span class="sxs-lookup"><span data-stu-id="f11aa-116">Edit the Meet URL by using the same steps, if necessary.</span></span>

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a><span data-ttu-id="f11aa-117">定義選用的系統管理員簡易 URL</span><span class="sxs-lookup"><span data-stu-id="f11aa-117">To define the optional Admin simple URL</span></span>

1.  <span data-ttu-id="f11aa-118">在拓撲建立器中，以滑鼠右鍵按一下**Lync Server**節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="f11aa-118">In Topology Builder, right-click the **Lync Server** node, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="f11aa-119">在 [**管理存取 URL** ] 方塊中，輸入您想要用來管理 Lync Server 2013 [控制台] 的簡單 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f11aa-119">In the **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="f11aa-120">我們建議您使用最簡單的管理 URL URL。</span><span class="sxs-lookup"><span data-stu-id="f11aa-120">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="f11aa-121">最簡單的選項就是<STRONG> https://admin。</STRONG>&lt;網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="f11aa-121">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f11aa-122">如果您在初始部署之後變更簡單的 URL，您必須知道哪些變更會影響您的網域名稱系統（DNS）記錄及簡單 Url 的憑證。</span><span class="sxs-lookup"><span data-stu-id="f11aa-122">If you change a simple URL after initial deployment, you must be aware of what changes impact your Domain Name System (DNS) records and certificates for simple URLs.</span></span> <span data-ttu-id="f11aa-123">如果變更會影響簡單 URL 的基底，則您也必須變更 DNS 記錄和憑證。</span><span class="sxs-lookup"><span data-stu-id="f11aa-123">If the change impacts the base of a simple URL, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="f11aa-124">例如，從https://lync.contoso.com/Meet lync.contoso.com https://meet.contoso.com變更為 MEET.CONTOSO.COM 的基底 URL，因此您必須將 DNS 記錄和憑證變更為參照 meet.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="f11aa-124">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="f11aa-125">如果您將簡單的 URL 改https://lync.contoso.com/Meet為https://lync.contoso.com/Meetings[寄件者]，則 LYNC.CONTOSO.COM 的基底 url 會保持不變，因此不需要變更 DNS 或憑證。</span><span class="sxs-lookup"><span data-stu-id="f11aa-125">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span> <span data-ttu-id="f11aa-126">不過，每當您變更簡單的 URL 名稱時，您必須在每個主管和前端伺服器上執行<STRONG>Enable-CsComputer</STRONG> Cmdlet，才能註冊變更。</span><span class="sxs-lookup"><span data-stu-id="f11aa-126">Whenever you change a simple URL name, however, you must run the <STRONG>Enable-CsComputer</STRONG> cmdlet on each Director and Front End Server to register the change.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f11aa-127">請參閱</span><span class="sxs-lookup"><span data-stu-id="f11aa-127">See Also</span></span>


[<span data-ttu-id="f11aa-128">在 Lync Server 2013 中規劃簡單 URL</span><span class="sxs-lookup"><span data-stu-id="f11aa-128">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

