---
title: 在移轉後變更簡單 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c9f46944e80c5eb7a2d81de6f164d19aab64d29
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="45b2d-102">在移轉後變更簡單 URL</span><span class="sxs-lookup"><span data-stu-id="45b2d-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45b2d-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="45b2d-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="45b2d-104">Lync Server 支援三種簡單的 URLs：</span><span class="sxs-lookup"><span data-stu-id="45b2d-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="45b2d-105">「**開會**」是網站或組織中所有會議的基礎 URL。</span><span class="sxs-lookup"><span data-stu-id="45b2d-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="45b2d-106">使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。</span><span class="sxs-lookup"><span data-stu-id="45b2d-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="45b2d-107">**撥入**功能可讓您存取電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="45b2d-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="45b2d-108">撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="45b2d-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="45b2d-109">系統**管理員**可讓您快速存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="45b2d-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="45b2d-110">系統管理員簡易 URL 是您組織內部。</span><span class="sxs-lookup"><span data-stu-id="45b2d-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="45b2d-111">在遷移至 Lync Server 2013 之後，您必須注意變更會如何影響您的 DNS 記錄和憑證，以進行簡單的 URLs。</span><span class="sxs-lookup"><span data-stu-id="45b2d-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="45b2d-112">如果舊版 Lync Server 2010 Director 仍在拓撲中使用，則不需要變更您的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="45b2d-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="45b2d-113">若 Lync Server 2010 Director 在遷移之後從拓撲移除，則必須更新簡單 URL DNS 記錄，以指向其中一個 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="45b2d-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="45b2d-114">不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 Enable-CsComputer，以註冊變更。</span><span class="sxs-lookup"><span data-stu-id="45b2d-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="45b2d-115">在遷移後變更簡單 URLs</span><span class="sxs-lookup"><span data-stu-id="45b2d-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="45b2d-116">**更新符合簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="45b2d-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="45b2d-117">在 [拓撲產生器] 中，以滑鼠右鍵按一下頂端節點 [ **Lync Server**]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="45b2d-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="45b2d-118">在左窗格中選取 [**簡單 URLs** ]，然後在 [**會議 URLs：** 選取 [符合 url]，然後按一下 [**編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="45b2d-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="45b2d-119">將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="45b2d-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="45b2d-120">**更新系統管理員簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="45b2d-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="45b2d-121">在 [拓撲產生器] 中，以滑鼠右鍵按一下頂端節點 [ **Lync Server**]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="45b2d-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="45b2d-122">在左窗格中選取 [**簡單 URLs** ]，然後在 [**管理存取 URL** ] 方塊中，輸入您要用來管理 Lync Server 2013 [控制台] 的簡易 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="45b2d-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="45b2d-123">建議您盡可能使用最簡單的 URL 作為 Admin URL。</span><span class="sxs-lookup"><span data-stu-id="45b2d-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="45b2d-124">最簡單的選項是<STRONG> https://admin 。</STRONG> &lt;網域 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="45b2d-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45b2d-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="45b2d-125">See Also</span></span>


[<span data-ttu-id="45b2d-126">在 Lync Server 2013 中規劃簡易 URLs</span><span class="sxs-lookup"><span data-stu-id="45b2d-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

