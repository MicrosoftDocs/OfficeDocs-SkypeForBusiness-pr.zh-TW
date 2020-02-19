---
title: 移轉後變更簡單 Url
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: a8e96c6a1d33c9c50208c7cdea628b2c4464a7b7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="6694b-102">移轉後變更簡單 Url</span><span class="sxs-lookup"><span data-stu-id="6694b-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6694b-103">_**主題上次修改日期：** 2012年-09-22_</span><span class="sxs-lookup"><span data-stu-id="6694b-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="6694b-104">Lync Server 支援三個簡單 Url:</span><span class="sxs-lookup"><span data-stu-id="6694b-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="6694b-105">**符合**用於做為基底 URL 的網站或組織中的所有會議。</span><span class="sxs-lookup"><span data-stu-id="6694b-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="6694b-106">Meet 簡單 URL，來加入會議的連結有可更容易理解，且更容易溝通與分送。</span><span class="sxs-lookup"><span data-stu-id="6694b-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="6694b-107">**撥號對應表中**啟用 [存取電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="6694b-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="6694b-108">撥入簡單 URL 包含所有會議邀請中，讓要撥入會議的使用者可以存取的必要的電話號碼及 pin 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="6694b-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="6694b-109">**系統管理員**可讓您快速存取 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="6694b-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="6694b-110">Admin 簡單 URL 是您組織內部。</span><span class="sxs-lookup"><span data-stu-id="6694b-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="6694b-111">移轉至 Lync Server 2013 之後，您必須知道如何變更會影響您的 DNS 記錄和憑證簡單 url。</span><span class="sxs-lookup"><span data-stu-id="6694b-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="6694b-112">如果舊版的 Lync Server 2010 Director 中保持使用中拓樸，不允許變更簡單 Url 所需。</span><span class="sxs-lookup"><span data-stu-id="6694b-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="6694b-113">如果從拓撲移除 Lync Server 2010 Director 移轉之後，必須更新簡單 URL 的 DNS 記錄，以指向下列其中一個 [Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="6694b-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="6694b-114">每當您變更了簡單 URL 名稱，但是，您必須執行 Enable-cscomputer 上每個 Director 與前端伺服器，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="6694b-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="6694b-115">移轉後變更簡單 Url</span><span class="sxs-lookup"><span data-stu-id="6694b-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="6694b-116">**更新 Meet 簡單 URL**</span><span class="sxs-lookup"><span data-stu-id="6694b-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="6694b-117">在拓撲產生器，以滑鼠右鍵按一下頂端節點 [ **Lync Server**，，，然後按一下 [**編輯內容**。</span><span class="sxs-lookup"><span data-stu-id="6694b-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6694b-118">選取 [**簡單 Url**在左窗格中，然後下方**會議 Url:** 選取 Meet URL，然後按一下 [**編輯 URL**。</span><span class="sxs-lookup"><span data-stu-id="6694b-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="6694b-119">將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="6694b-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="6694b-120">**更新 Admin 簡單 URL**</span><span class="sxs-lookup"><span data-stu-id="6694b-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="6694b-121">在拓撲產生器，以滑鼠右鍵按一下頂端節點 [ **Lync Server**，，，然後按一下 [**編輯內容**。</span><span class="sxs-lookup"><span data-stu-id="6694b-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="6694b-122">在左窗格中，然後下方**系統管理存取 URL** ] 方塊中選取 [**簡單 Url** ，輸入您想要管理存取權，Lync Server 2013 控制台，簡單 URL，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="6694b-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="6694b-123">建議您盡可能使用最簡單的 URL 作為 Admin URL。</span><span class="sxs-lookup"><span data-stu-id="6694b-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="6694b-124">最簡單的選項是<STRONG>https://admin。</STRONG>&lt;網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="6694b-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6694b-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6694b-125">See Also</span></span>


[<span data-ttu-id="6694b-126">規劃 Lync Server 2013 中的簡單 Url</span><span class="sxs-lookup"><span data-stu-id="6694b-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

