---
title: 規劃雲端通話佇列
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動語音應答的概覽。
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185542"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="b848e-103">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="b848e-103">Plan Cloud call queues</span></span>

<span data-ttu-id="b848e-104">雲端通話佇列是一項服務, 可接受客戶來電、播放問候語訊息, 然後在等待佇列中進行這些呼叫, 然後搜尋預先設定的代理程式清單來應答這些來電。</span><span class="sxs-lookup"><span data-stu-id="b848e-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="b848e-105">您可以在已啟用郵件功能的通訊群組清單或安全性群組中定義一組代理程式。</span><span class="sxs-lookup"><span data-stu-id="b848e-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="b848e-106">貴組織可以有一個或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="b848e-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="b848e-107">通話佇列通常與自動語音應答搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b848e-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="b848e-108">此外, 雲端通話佇列可以提供:</span><span class="sxs-lookup"><span data-stu-id="b848e-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="b848e-109">在呼叫者等待保留時的音樂</span><span class="sxs-lookup"><span data-stu-id="b848e-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="b848e-110">通話佇列的自訂設定大小上限、超時及呼叫處理選項</span><span class="sxs-lookup"><span data-stu-id="b848e-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="b848e-111">每個通話佇列都會獲指派**資源帳戶**(請參閱在商務用 Skype Server 2019 系統上[設定資源](configure-onprem-ra.md)帳戶), 該系統會直接連結到 Microsoft 團隊系統管理中心的呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="b848e-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="b848e-112">如需通話佇列的用途, 以及呼叫佇列的選項和功能, 請參閱[建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)。</span><span class="sxs-lookup"><span data-stu-id="b848e-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="b848e-113">您可以將多個電話號碼指派給通話佇列, 但必須是 Microsoft 服務號碼或混合式號碼。</span><span class="sxs-lookup"><span data-stu-id="b848e-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="b848e-114">需求</span><span class="sxs-lookup"><span data-stu-id="b848e-114">Requirements</span></span>

<span data-ttu-id="b848e-115">下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="b848e-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="b848e-116">您的需求取決於您的案例:</span><span class="sxs-lookup"><span data-stu-id="b848e-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="b848e-117">針對雲端呼叫佇列的新設定, 請按照[設定資源帳戶](configure-onprem-ra.md)中所述的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="b848e-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="b848e-118">您將需要在線上或商務用 Skype Server 2019 中建立資源帳戶, 而且您可能也需要將電話號碼與通話佇列建立關聯。</span><span class="sxs-lookup"><span data-stu-id="b848e-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="b848e-119">除了上述需求之外, 下列需求必須設定為連線至 Microsoft 雲端通話佇列服務:</span><span class="sxs-lookup"><span data-stu-id="b848e-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="b848e-120">混合式連線性。</span><span class="sxs-lookup"><span data-stu-id="b848e-120">Hybrid connectivity.</span></span> <span data-ttu-id="b848e-121">如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端通話佇列, 您必須確保您在內部部署與線上環境之間有混合式連線性設定。</span><span class="sxs-lookup"><span data-stu-id="b848e-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="b848e-122">這有時稱為分割網域配置。</span><span class="sxs-lookup"><span data-stu-id="b848e-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="b848e-123">如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="b848e-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="b848e-124">如果您要將電話號碼指派給資源帳戶, 您現在可以使用 [免付費電話系統虛擬使用者授權]。</span><span class="sxs-lookup"><span data-stu-id="b848e-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="b848e-125">這會提供手機系統功能給組織階層的電話號碼, 並可讓您建立自動語音應答及呼叫佇列功能。</span><span class="sxs-lookup"><span data-stu-id="b848e-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="b848e-126">針對每個通話佇列建立內部部署[資源帳戶](configure-onprem-ra.md), 並視需要指派授權和電話號碼。</span><span class="sxs-lookup"><span data-stu-id="b848e-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

## <a name="additional-planning-resources"></a><span data-ttu-id="b848e-127">其他規劃資源</span><span class="sxs-lookup"><span data-stu-id="b848e-127">Additional planning resources</span></span>

<span data-ttu-id="b848e-128">標題為「小型企業」的教學課程[範例-設定自動](/microsoftteams/tutorial-org-aa)語音應答: 完成收集使用者需求之資訊的程式、規劃自動語音應答及使用者的結構 (以及可能通話佇列)、撰寫功能表提示, 以及在線上系統管理中心實施方案。</span><span class="sxs-lookup"><span data-stu-id="b848e-128">The tutorial titled [Small business example - Set up an auto attendant](/microsoftteams/tutorial-org-aa) goes through the process of gathering information about user needs, planning a structure of auto attendants and users (and possibly call queues), writing the menu prompts, and implementing the plan in the Online Admin center.</span></span> <span data-ttu-id="b848e-129">查看教學課程, 並使用 [在此練習] 建立您的方案。</span><span class="sxs-lookup"><span data-stu-id="b848e-129">review the tutorial and use the exercises there t create your plan.</span></span>

<span data-ttu-id="b848e-130">當您有符合您需求的實體結構, 以及能有效引導客戶的腳本時, 請繼續[設定資源帳戶](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="b848e-130">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b848e-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="b848e-131">See Also</span></span>

[<span data-ttu-id="b848e-132">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b848e-132">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="b848e-133">使用電話使用者介面啟用自訂提示錄製</span><span class="sxs-lookup"><span data-stu-id="b848e-133">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="b848e-134">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="b848e-134">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="b848e-135">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="b848e-135">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="b848e-136">規劃商務用 Skype Server 與 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="b848e-136">Plan hybrid connectivity between Skype for Business Server and Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="b848e-137">在商務用 Skype Server 和 Office 365 之間設定混合式連接</span><span class="sxs-lookup"><span data-stu-id="b848e-137">Configure hybrid connectivity between Skype for Business Server and Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="b848e-138">管理 Microsoft 團隊中的資源帳戶</span><span class="sxs-lookup"><span data-stu-id="b848e-138">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
