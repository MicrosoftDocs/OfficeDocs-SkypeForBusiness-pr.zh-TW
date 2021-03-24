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
description: 在商務用 Skype Server 2019 中使用雲端自動語音應答的概覽。
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110489"
---
# <a name="plan-cloud-call-queues"></a><span data-ttu-id="f35d7-103">規劃雲端通話佇列</span><span class="sxs-lookup"><span data-stu-id="f35d7-103">Plan Cloud call queues</span></span>

<span data-ttu-id="f35d7-104">雲端通話佇列是一種服務，可接受客戶的來電、播放問候語訊息，然後在等候佇列中進行這些呼叫，然後搜尋預先設定的代理程式清單，以接聽這些呼叫。</span><span class="sxs-lookup"><span data-stu-id="f35d7-104">Cloud call queue is a service that accepts customer calls, plays a greeting message, and then places these calls in a wait queue while searching a pre-configured list of agents to answer these calls.</span></span> <span data-ttu-id="f35d7-105">您可以在啟用郵件功能的通訊群組清單或安全性群組中定義一組代理人。</span><span class="sxs-lookup"><span data-stu-id="f35d7-105">You can define the set of agents in mail-enabled distribution lists or security groups.</span></span> <span data-ttu-id="f35d7-106">您的組織可以有一或多個通話佇列。</span><span class="sxs-lookup"><span data-stu-id="f35d7-106">Your organization can have one or many call queues.</span></span> <span data-ttu-id="f35d7-107">通話佇列通常會與自動語音應答一起使用。</span><span class="sxs-lookup"><span data-stu-id="f35d7-107">Call queues are usually used in combination with auto attendants.</span></span>

<span data-ttu-id="f35d7-108">此外，雲端通話佇列可以提供：</span><span class="sxs-lookup"><span data-stu-id="f35d7-108">In addition, Cloud call queues can provide:</span></span>

- <span data-ttu-id="f35d7-109">來電者等候通話時的音樂</span><span class="sxs-lookup"><span data-stu-id="f35d7-109">Music while callers are waiting on hold</span></span>
- <span data-ttu-id="f35d7-110">通話佇列的自訂設定大小上限、timeout 及通話處理選項</span><span class="sxs-lookup"><span data-stu-id="f35d7-110">Customized settings for call queue maximum size, timeout, and call handling options</span></span>

<span data-ttu-id="f35d7-111">為每個通話佇列指派一個 **資源帳戶** (請參閱設定商務用 Skype Server 2019 系統上) 的 [資源帳戶](configure-onprem-ra.md) ，此系統會直接連結到 Microsoft 團隊系統管理中心中的呼叫佇列。</span><span class="sxs-lookup"><span data-stu-id="f35d7-111">Each call queue is assigned a **resource account** (see [Configure resource accounts](configure-onprem-ra.md)) on your Skype for Business Server 2019 system that will be linked directly to a call queue in the Microsoft Teams admin center.</span></span> <span data-ttu-id="f35d7-112">如需通話佇列的詳細資訊，以及通話佇列的選項及功能，請參閱 [Create a 雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue) 。</span><span class="sxs-lookup"><span data-stu-id="f35d7-112">See [Create a Cloud call queue](/MicrosoftTeams/create-a-phone-system-call-queue) for more detail on what call queues are and what options and features exist for call queues.</span></span>

> [!NOTE]
> <span data-ttu-id="f35d7-113">您可以將多個電話號碼指派給通話佇列，但必須是 Microsoft 服務號碼、直接路由號碼或混合號碼。</span><span class="sxs-lookup"><span data-stu-id="f35d7-113">You can assign multiple phone numbers to a call queue, but they must be Microsoft service numbers, Direct Routing numbers, or hybrid numbers.</span></span>

## <a name="requirements"></a><span data-ttu-id="f35d7-114">需求</span><span class="sxs-lookup"><span data-stu-id="f35d7-114">Requirements</span></span>

<span data-ttu-id="f35d7-115">下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="f35d7-115">The following requirements assume that you already have Skype for Business Server 2019 deployed in a supported topology.</span></span>  <span data-ttu-id="f35d7-116">您的需求取決於您的案例：</span><span class="sxs-lookup"><span data-stu-id="f35d7-116">Your requirements depend on your scenario:</span></span>

- <span data-ttu-id="f35d7-117">若為雲端通話佇列的新設定，請遵循 [設定資源帳戶](configure-onprem-ra.md)中所述的步驟。</span><span class="sxs-lookup"><span data-stu-id="f35d7-117">For a new configuration of Cloud call queues, follow the steps outlined in [Configure resource accounts](configure-onprem-ra.md).</span></span> <span data-ttu-id="f35d7-118">您必須在線上或商務用 Skype Server 2019 中建立資源帳戶，而且您可能還需要將電話號碼與通話佇列相關聯。</span><span class="sxs-lookup"><span data-stu-id="f35d7-118">You will need to create resource accounts either online or in Skype for Business Server 2019, and you may also need to associate a phone number with the call queue.</span></span>

<span data-ttu-id="f35d7-119">除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft 雲端通話佇列服務：</span><span class="sxs-lookup"><span data-stu-id="f35d7-119">In addition to the requirements above, the below requirements must be configured to connect to the Microsoft Cloud call queue service:</span></span>

- <span data-ttu-id="f35d7-120">混合連接。</span><span class="sxs-lookup"><span data-stu-id="f35d7-120">Hybrid connectivity.</span></span> <span data-ttu-id="f35d7-121">如果您已部署商務用 Skype Server，而您想要為您的內部部署使用者啟用雲端通話佇列，您必須確定您的內部部署與線上環境之間已設定混合式連線能力。</span><span class="sxs-lookup"><span data-stu-id="f35d7-121">If you already have Skype for Business Server deployed, and you want to enable Cloud call queues for your on-premises users, you must ensure that you have hybrid connectivity set up between your on-premises and online environments.</span></span> <span data-ttu-id="f35d7-122">這有時稱為分割網域設定。</span><span class="sxs-lookup"><span data-stu-id="f35d7-122">This is sometimes called a split domain configuration.</span></span>

   <span data-ttu-id="f35d7-123">如需詳細資訊，請參閱 [規劃商務用 Skype server 與 microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md) 式連線，以及 [設定商務用 Skype server 與 Microsoft 365 或 office 365 的混合](configure-hybrid-connectivity.md)式連線。</span><span class="sxs-lookup"><span data-stu-id="f35d7-123">For more information, see [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md) and [Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](configure-hybrid-connectivity.md).</span></span>

- <span data-ttu-id="f35d7-124">若要將電話號碼指派給資源帳戶，您現在可以使用「成本免費電話系統虛擬使用者」授權。</span><span class="sxs-lookup"><span data-stu-id="f35d7-124">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="f35d7-125">這為組織層級的電話號碼提供電話系統功能，並讓您建立自動語音應答及通話佇列功能。</span><span class="sxs-lookup"><span data-stu-id="f35d7-125">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

- <span data-ttu-id="f35d7-126">針對每個通話佇列建立內部部署 [資源帳戶](configure-onprem-ra.md) ，並視需要指派授權和電話號碼。</span><span class="sxs-lookup"><span data-stu-id="f35d7-126">Create an on-premises [resource account](configure-onprem-ra.md) for each call queue, and assign a license and phone number if required.</span></span>  

<span data-ttu-id="f35d7-127">當您具有符合您需求的實體結構，以及可有效指導客戶有效的腳本時，請繼續  [設定資源帳戶](configure-onprem-ra.md)。</span><span class="sxs-lookup"><span data-stu-id="f35d7-127">When you have a solid structure that meets your needs and a script that guides customers efficiently, proceed to  [Configure resource accounts](configure-onprem-ra.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f35d7-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f35d7-128">See Also</span></span>

[<span data-ttu-id="f35d7-129">設定資源帳戶</span><span class="sxs-lookup"><span data-stu-id="f35d7-129">Configure resource accounts</span></span>](configure-onprem-ra.md)

[<span data-ttu-id="f35d7-130">使用電話使用者介面錄製自訂提示</span><span class="sxs-lookup"><span data-stu-id="f35d7-130">Enable custom prompt recording using the telephone user interface</span></span>](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[<span data-ttu-id="f35d7-131">什麼是雲端自動語音應答？</span><span class="sxs-lookup"><span data-stu-id="f35d7-131">What are Cloud auto attendants?</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[<span data-ttu-id="f35d7-132">設定雲端自動語音應答</span><span class="sxs-lookup"><span data-stu-id="f35d7-132">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[<span data-ttu-id="f35d7-133">規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線</span><span class="sxs-lookup"><span data-stu-id="f35d7-133">Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](plan-hybrid-connectivity.md)

[<span data-ttu-id="f35d7-134">設定商務用 Skype Server 與 Microsoft 365 或 Office 365 的混合式連線</span><span class="sxs-lookup"><span data-stu-id="f35d7-134">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](configure-hybrid-connectivity.md)

[<span data-ttu-id="f35d7-135">在 Microsoft Teams 中管理資源帳戶</span><span class="sxs-lookup"><span data-stu-id="f35d7-135">Manage resource accounts in Microsoft Teams</span></span>](/MicrosoftTeams/manage-resource-accounts)