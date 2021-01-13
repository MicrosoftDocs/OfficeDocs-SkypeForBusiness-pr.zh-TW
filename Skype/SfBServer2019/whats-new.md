---
title: 商務用 Skype Server 2019 的新功能 |特徵
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：這些功能是商務用 Skype Server 2019 中的新功能。
ms.openlocfilehash: f20abfa7d48717052c8ee0144e143a21b168286d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812583"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="8c88c-103">商務用 Skype Server 2019 中的內容</span><span class="sxs-lookup"><span data-stu-id="8c88c-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="8c88c-104">**摘要：** 閱讀此主題以瞭解商務用 Skype Server 2019 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="8c88c-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="8c88c-105">商務用 Skype Server 2019 中的新功能包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="8c88c-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="8c88c-106">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="8c88c-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="8c88c-107">通話資料連接器</span><span class="sxs-lookup"><span data-stu-id="8c88c-107">Call Data Connector</span></span>
- <span data-ttu-id="8c88c-108">並列遷移</span><span class="sxs-lookup"><span data-stu-id="8c88c-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="8c88c-109">整合通訊服務：雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="8c88c-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="8c88c-110">當您整合商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 時，Exchange UM 仍可用於商務用 Skype Server 2019。</span><span class="sxs-lookup"><span data-stu-id="8c88c-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="8c88c-111">由於 Exchange 2019 中的支援變更，因此會取消考慮 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。</span><span class="sxs-lookup"><span data-stu-id="8c88c-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="8c88c-112">雲端語音信箱可讓您的所有商務用 Skype 2019 使用者&#x2014;是否位於內部部署或線上&#x2014;，以存取 Microsoft 雲端中相同的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="8c88c-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="8c88c-113">雲端語音信箱為您的內部部署和線上使用者提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="8c88c-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="8c88c-114">使用商務用 Skype Online、小組或 Outlook 用戶端，存取 Exchange 信箱中的語音信箱</span><span class="sxs-lookup"><span data-stu-id="8c88c-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="8c88c-115">使用以 web 為基礎的入口網站來管理其語音信箱選項</span><span class="sxs-lookup"><span data-stu-id="8c88c-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="8c88c-116">如需詳細資訊，請參閱 [Plan Cloud 語音信箱服務](../sfbhybrid/hybrid/plan-cloud-voicemail.md) 並 [規劃商務用 Skype Server 和 Exchange Server 遷移](../sfbhybrid/hybrid/plan-um-migration.md) 。</span><span class="sxs-lookup"><span data-stu-id="8c88c-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="8c88c-117">通話監控：通話資料連線器</span><span class="sxs-lookup"><span data-stu-id="8c88c-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="8c88c-118">呼叫資料連線器大幅簡化混合式環境中的呼叫監控，因為您不再需要使用不同的內部部署和線上工具來監視所有使用者的通話品質。</span><span class="sxs-lookup"><span data-stu-id="8c88c-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="8c88c-119">不論您的使用者是位於內部部署或線上，您可以選擇線上查看整個組織的通話品質。</span><span class="sxs-lookup"><span data-stu-id="8c88c-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="8c88c-120">使用「呼叫資料連線器」，您可以使用單一工具集來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="8c88c-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="8c88c-121">在 Microsoft 團隊、商務用 Skype Online 和商務用 Skype Server 上監視您的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="8c88c-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="8c88c-122">查看和疑難排解整個網路的問題</span><span class="sxs-lookup"><span data-stu-id="8c88c-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="8c88c-123">指派呼叫分析的「服務台」和「系統管理員」角色，讓輔助技術人員能夠查看及疑難排解其職責範圍。</span><span class="sxs-lookup"><span data-stu-id="8c88c-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="8c88c-124">如需詳細資訊，請參閱 [規劃通話資料連線器](../sfbhybrid/hybrid/plan-call-data-connector.md) 。</span><span class="sxs-lookup"><span data-stu-id="8c88c-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="8c88c-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8c88c-125">See also</span></span>

[<span data-ttu-id="8c88c-126">商務用 Skype Server 2019 中已被取代的功能</span><span class="sxs-lookup"><span data-stu-id="8c88c-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
