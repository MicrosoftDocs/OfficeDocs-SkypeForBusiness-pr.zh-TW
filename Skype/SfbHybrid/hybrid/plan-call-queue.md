---
title: 規劃雲端通話佇列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動 Attendant 概觀。
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918739"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="d6ba9-103">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="d6ba9-103">Plan Cloud call queues</span></span>

<span data-ttu-id="d6ba9-104">雲端通話佇列是一種服務，可接受客戶通話、播放問候訊息，然後在搜尋預先配置的代理程式清單時，將這些通話排入等候佇列以接聽這些通話。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="d6ba9-105">您可以在已啟用郵件功能的通訊群組清單或安全性群組中定義一組代理程式。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="d6ba9-106">您的組織可以有一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="d6ba9-107">通話佇列通常會與自動參與人員搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="d6ba9-108">此外，雲端通話佇列也可提供：</span><span class="sxs-lookup"><span data-stu-id="d6ba9-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="d6ba9-109">當來電者等候等候時播放音樂</span><span class="sxs-lookup"><span data-stu-id="d6ba9-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="d6ba9-110">自訂通話佇列最大大小、超時及來電處理選項的設定</span><span class="sxs-lookup"><span data-stu-id="d6ba9-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="d6ba9-111">每個通話佇列都會被指派一個資源帳戶 **(** 請參閱在商務用 Skype Server 2019 系統上設定資源帳戶 [) ，](configure-onprem-ra.md) 這個帳戶會直接連結到 Microsoft Teams 系統管理中心的通話佇列。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d6ba9-112">請參閱 [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue) ，以進一步瞭解什麼是通話佇列，以及通話佇列可用的選項和功能。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="d6ba9-113">您可以將多個電話號碼指派給通話佇列，但這些號碼必須是 Microsoft 服務號碼、直接路由號碼或混合式號碼。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6ba9-114">需求</span><span class="sxs-lookup"><span data-stu-id="d6ba9-114">Requirements</span></span>

<span data-ttu-id="d6ba9-115">下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="d6ba9-116">您的需求視您的案例而不同：</span><span class="sxs-lookup"><span data-stu-id="d6ba9-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="d6ba9-117">若要設定新的雲端通話佇列設定，請遵循設定資源帳戶 [中列出的步驟](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="d6ba9-118">您必須在線上或商務用 Skype Server 2019 中建立資源帳戶，而且您可能也需要將電話號碼與通話佇列建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="d6ba9-119">除了上述要求之外，必須針對下列需求進行配置，以連接至 Microsoft Cloud 通話佇列服務：</span><span class="sxs-lookup"><span data-stu-id="d6ba9-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="d6ba9-120">混合式連接。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-120">Hybrid connectivity.</span></span> <span data-ttu-id="d6ba9-121">如果您已經部署商務用 Skype Server，而且想要為內部部署使用者啟用雲端通話佇列，您必須確保您的內部部署和線上環境之間已設定混合式連線。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="d6ba9-122">這有時稱為分割網域組配置。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="d6ba9-123">詳細資訊請參閱規劃商務用 Skype Server 與 [Microsoft 365 或 Office 365](plan-hybrid-connectivity.md) 之間的混合式連接，以及設定商務用 Skype Server 與 [Microsoft 365 或 Office 365](configure-hybrid-connectivity.md)之間的混合式連接。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="d6ba9-124">如果您要將電話號碼指派給資源帳戶，現在可以使用無成本的電話系統虛擬使用者授權。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="d6ba9-125">這提供組織層級的電話號碼的電話系統功能，並可讓您建立自動撥打和通話佇列功能。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="d6ba9-126">為每個 [通話佇列建立](configure-onprem-ra.md) 內部部署資源帳戶，並指派授權和電話號碼 ，如果需要。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="d6ba9-127">當您擁有符合您需求的實心結構，以及可有效率地引導客戶的腳本時，請繼續設定  [資源帳戶](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="d6ba9-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d6ba9-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d6ba9-128">See Also</span></span>

[<span data-ttu-id="d6ba9-129">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d6ba9-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="d6ba9-130">使用電話使用者介面錄製自訂提示</span><span class="sxs-lookup"><span data-stu-id="d6ba9-130">Enable custom prompt recording using the telephone user interface</span></span>](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="d6ba9-131">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="d6ba9-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="d6ba9-132">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="d6ba9-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="d6ba9-133">規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="d6ba9-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="d6ba9-134">設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接</span><span class="sxs-lookup"><span data-stu-id="d6ba9-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="d6ba9-135">在 Microsoft Teams 中管理資源帳戶</span><span class="sxs-lookup"><span data-stu-id="d6ba9-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)
