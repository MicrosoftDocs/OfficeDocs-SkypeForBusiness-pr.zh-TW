---
title: 在移轉後變更簡單 URL
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
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="a57c2-102">在移轉後變更簡單 URL</span><span class="sxs-lookup"><span data-stu-id="a57c2-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a57c2-103">_**主題上次修改日期：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="a57c2-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="a57c2-104">Lync Server 支援三個簡單的 Url：</span><span class="sxs-lookup"><span data-stu-id="a57c2-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="a57c2-105">[**開會**] 是用來做為網站或組織中所有會議的基底 URL。</span><span class="sxs-lookup"><span data-stu-id="a57c2-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="a57c2-106">使用 [符合簡單的 URL]，加入會議的連結就很容易理解，且易於溝通及發佈。</span><span class="sxs-lookup"><span data-stu-id="a57c2-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="a57c2-107">[**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。</span><span class="sxs-lookup"><span data-stu-id="a57c2-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="a57c2-108">[撥入] 簡單 URL 包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="a57c2-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="a57c2-109">[系統**管理**] 可讓您快速存取 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="a57c2-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="a57c2-110">系統管理員簡易 URL 是貴組織的內部。</span><span class="sxs-lookup"><span data-stu-id="a57c2-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="a57c2-111">遷移至 Lync Server 2013 之後，您必須知道變更對您的 DNS 記錄及證書有何影響，以取得簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="a57c2-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="a57c2-112">如果舊版 Lync Server 2010 控制器在拓撲中保持使用，則不需要變更您的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="a57c2-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="a57c2-113">如果 Lync Server 2010 控制器是在遷移之後從拓撲中移除，則必須更新簡單的 URL DNS 記錄，以指向其中一個 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="a57c2-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="a57c2-114">不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行 Enable-CsComputer，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="a57c2-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="a57c2-115">遷移後變更簡單的 Url</span><span class="sxs-lookup"><span data-stu-id="a57c2-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="a57c2-116">**若要更新 [符合簡單 URL]**</span><span class="sxs-lookup"><span data-stu-id="a57c2-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="a57c2-117">在拓撲建立器中，以滑鼠右鍵按一下頂層節點**Lync Server**，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a57c2-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a57c2-118">選取左窗格中的 [**簡單 url** ]，然後選取 [**會議 url]：** 選取 [認識 url]，然後按一下 [**編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="a57c2-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="a57c2-119">更新 URL 至您想要的值，然後按一下 **[確定]** 以儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="a57c2-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="a57c2-120">**更新管理員簡易 URL**</span><span class="sxs-lookup"><span data-stu-id="a57c2-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="a57c2-121">在拓撲建立器中，以滑鼠右鍵按一下頂層節點**Lync Server**，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a57c2-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="a57c2-122">選取左窗格中的 [**簡單 url** ]，然後在 [**管理存取 URL** ] 方塊中，輸入您要用來管理 Lync Server 2013 [控制台] 的簡單 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a57c2-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="a57c2-123">我們建議您使用最簡單的管理 URL URL。</span><span class="sxs-lookup"><span data-stu-id="a57c2-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="a57c2-124">最簡單的選項就是<STRONG> https://admin。</STRONG>&lt;網域&gt;。</span><span class="sxs-lookup"><span data-stu-id="a57c2-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a57c2-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="a57c2-125">See Also</span></span>


[<span data-ttu-id="a57c2-126">在 Lync Server 2013 中規劃簡單 URL</span><span class="sxs-lookup"><span data-stu-id="a57c2-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

