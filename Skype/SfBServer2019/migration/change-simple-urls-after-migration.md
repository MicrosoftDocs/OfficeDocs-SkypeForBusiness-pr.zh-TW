---
title: 在移轉後變更簡單 URL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype 伺服器支援簡單的 Url。
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813881"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="7a236-103">在移轉後變更簡單 URL</span><span class="sxs-lookup"><span data-stu-id="7a236-103">Change simple URLs after migration</span></span>

<span data-ttu-id="7a236-104">商務用 Skype 伺服器支援三個簡單的 Url：</span><span class="sxs-lookup"><span data-stu-id="7a236-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="7a236-105">[**開會**] 是用來做為網站或組織中所有會議的基底 URL。</span><span class="sxs-lookup"><span data-stu-id="7a236-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="7a236-106">使用 [符合簡單的 URL]，加入會議的連結就很容易理解，且易於溝通及發佈。</span><span class="sxs-lookup"><span data-stu-id="7a236-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="7a236-107">[**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。</span><span class="sxs-lookup"><span data-stu-id="7a236-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="7a236-108">[撥入] 簡單 URL 包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。</span><span class="sxs-lookup"><span data-stu-id="7a236-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="7a236-109">[系統**管理**] 可讓您快速存取商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7a236-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="7a236-110">系統管理員簡易 URL 是貴組織的內部。</span><span class="sxs-lookup"><span data-stu-id="7a236-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="7a236-111">遷移到商務用 Skype Server 之後，您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。</span><span class="sxs-lookup"><span data-stu-id="7a236-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="7a236-112">如果舊版商務用 Skype Server 主管在拓撲中保持使用，則不需要變更您的簡單 Url。</span><span class="sxs-lookup"><span data-stu-id="7a236-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="7a236-113">如果在遷移之後從拓撲中移除商務用 Skype Server 主管，則必須更新簡單的 URL DNS 記錄，以指向其中一個商務用 Skype 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="7a236-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="7a236-114">不過，每當您變更簡單的 URL 名稱時，您必須在每個控制器和前端伺服器上執行 Enable-CsComputer，以登錄變更。</span><span class="sxs-lookup"><span data-stu-id="7a236-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="7a236-115">若要更新 [符合簡單 URL]</span><span class="sxs-lookup"><span data-stu-id="7a236-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="7a236-116">在拓撲建立器中，以滑鼠右鍵按一下**商務用 Skype 伺服器**的頂端節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="7a236-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="7a236-117">選取左窗格中的 [**簡單 url** ]，然後選取 [**會議 url]：** 選取 [認識 url]，然後按一下 [**編輯 URL**]。</span><span class="sxs-lookup"><span data-stu-id="7a236-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="7a236-118">更新 URL 至您想要的值，然後按一下 **[確定]** 以儲存編輯的 URL。</span><span class="sxs-lookup"><span data-stu-id="7a236-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="7a236-119">更新管理員簡易 URL</span><span class="sxs-lookup"><span data-stu-id="7a236-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="7a236-120">在拓撲建立器中，以滑鼠右鍵按一下**商務用 Skype 伺服器**的頂端節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="7a236-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="7a236-121">選取左窗格中的 [**簡單 url** ]，然後在 [**管理存取 URL** ] 方塊中，輸入您要用來管理商務用 Skype Server [控制台] 的簡單 URL，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7a236-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="7a236-122">我們建議您使用最簡單的管理 URL URL。</span><span class="sxs-lookup"><span data-stu-id="7a236-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="7a236-123">最簡單的選項https://admin就是。<em> \<網域\></em>。</span><span class="sxs-lookup"><span data-stu-id="7a236-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="7a236-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7a236-124">See also</span></span>

[<span data-ttu-id="7a236-125">商務用 Skype Server 中簡單 Url 的 DNS 需求</span><span class="sxs-lookup"><span data-stu-id="7a236-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
