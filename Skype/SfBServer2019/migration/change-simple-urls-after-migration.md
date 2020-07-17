---
title: 在移轉後變更簡單 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype 伺服器支援簡單 URLs。
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753903"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="96ea4-103">在移轉後變更簡單 URL</span><span class="sxs-lookup"><span data-stu-id="96ea4-103">Change simple URLs after migration</span></span>

<span data-ttu-id="96ea4-104">商務用 Skype 伺服器支援三個簡單的 URLs：</span><span class="sxs-lookup"><span data-stu-id="96ea4-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="96ea4-105">「**開會**」是網站或組織中所有會議的基礎 URL。</span><span class="sxs-lookup"><span data-stu-id="96ea4-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="96ea4-106">使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。</span><span class="sxs-lookup"><span data-stu-id="96ea4-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="96ea4-107">**撥入**功能可讓您存取電話撥入式會議設定網頁。</span><span class="sxs-lookup"><span data-stu-id="96ea4-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="96ea4-108">撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。</span><span class="sxs-lookup"><span data-stu-id="96ea4-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="96ea4-109">系統**管理員**可讓您快速存取商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="96ea4-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="96ea4-110">系統管理員簡易 URL 是您組織內部。</span><span class="sxs-lookup"><span data-stu-id="96ea4-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="96ea4-111">在遷移至商務用 Skype Server 之後，您必須注意變更會如何影響您的 DNS 記錄和憑證以取得簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="96ea4-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="96ea4-112">如果舊版商務用 Skype Server Director 仍在拓撲中使用，則不需要變更您的簡單 URLs。</span><span class="sxs-lookup"><span data-stu-id="96ea4-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="96ea4-113">如果在遷移之後從拓撲移除商務用 Skype 伺服器 Director，則必須更新簡單 URL DNS 記錄，以指向其中一個商務用 Skype 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="96ea4-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="96ea4-114">不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 Enable-CsComputer，以註冊變更。</span><span class="sxs-lookup"><span data-stu-id="96ea4-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="96ea4-115">更新符合簡易 URL</span><span class="sxs-lookup"><span data-stu-id="96ea4-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="96ea4-116">在 [拓撲產生器] 中，以滑鼠右鍵按一下上方節點 [**商務用 Skype 伺服器**]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="96ea4-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="96ea4-117">在左窗格中選取 [**簡單 URLs** ]，然後在 [**會議 URLs：** 選取 [符合 url]，然後按一下 [**編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="96ea4-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="96ea4-118">將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="96ea4-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="96ea4-119">更新系統管理員簡易 URL</span><span class="sxs-lookup"><span data-stu-id="96ea4-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="96ea4-120">在 [拓撲產生器] 中，以滑鼠右鍵按一下上方節點 [**商務用 Skype 伺服器**]，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="96ea4-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="96ea4-121">在左窗格中選取 [**簡單 URLs** ]，然後在 [系統**管理存取 URL** ] 方塊中，輸入您要用於系統管理存取商務用 Skype SERVER 控制台的簡易 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="96ea4-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="96ea4-122">建議您盡可能使用最簡單的 URL 作為 Admin URL。</span><span class="sxs-lookup"><span data-stu-id="96ea4-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="96ea4-123">最簡單的選項是 https://admin ... <em>\<domain\></em></span><span class="sxs-lookup"><span data-stu-id="96ea4-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="96ea4-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="96ea4-124">See also</span></span>

[<span data-ttu-id="96ea4-125">商務用 Skype Server 中簡易 URLs 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="96ea4-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
