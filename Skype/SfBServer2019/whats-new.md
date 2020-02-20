---
title: What's new in Skype for Business Server 2019 |功能
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
audience: ITPro
ms.topic: overview
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 這些功能是 Skype for Business Server 2019 的新功能。
ms.openlocfilehash: 86a8ce580a8aafcfb487a4b0cf839cd001dace8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129396"
---
# <a name="whats-in-skype-for-business-server-2019"></a><span data-ttu-id="7214d-103">什麼是 skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7214d-103">What's in Skype for Business Server 2019</span></span>

<span data-ttu-id="7214d-104">**摘要：** 閱讀此主題以了解用 Skype 的新功能的商務 Server 2019。</span><span class="sxs-lookup"><span data-stu-id="7214d-104">**Summary:** Read this topic to learn about new features in Skype for Business Server 2019.</span></span>  

<span data-ttu-id="7214d-105">Skype for Business Server 2019 的新功能包括下列：</span><span class="sxs-lookup"><span data-stu-id="7214d-105">New features in Skype for Business Server 2019 include the following:</span></span>
  
- <span data-ttu-id="7214d-106">雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="7214d-106">Cloud Voicemail</span></span>  
- <span data-ttu-id="7214d-107">呼叫資料連接器</span><span class="sxs-lookup"><span data-stu-id="7214d-107">Call Data Connector</span></span>
- <span data-ttu-id="7214d-108">並排顯示移轉</span><span class="sxs-lookup"><span data-stu-id="7214d-108">Side-by-side migration</span></span>

## <a name="unified-messaging-services-cloud-voicemail"></a><span data-ttu-id="7214d-109">整合通訊服務： 雲端語音信箱</span><span class="sxs-lookup"><span data-stu-id="7214d-109">Unified messaging services: Cloud Voicemail</span></span>

<span data-ttu-id="7214d-110">Exchange UM 會保留在 Skype for Business Server 2019 時您整合 Exchange 2013 或 Exchange 2016 的 Skype for Business 2019。</span><span class="sxs-lookup"><span data-stu-id="7214d-110">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="7214d-111">由於支援在 Exchange 2019 中的變更，而 Exchange UM 整合正在重視因雲端語音信箱和雲端自動語音應答的功能。</span><span class="sxs-lookup"><span data-stu-id="7214d-111">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  

<span data-ttu-id="7214d-112">雲端語音信箱啟用所有您 Skype for Business 2019 使用者&#x2014;是否他們位於內部部署或線上&#x2014;Microsoft 雲端中具有存取權之相同的語音信箱服務。</span><span class="sxs-lookup"><span data-stu-id="7214d-112">Cloud Voicemail enables all your Skype for Business 2019 users&#x2014;whether they are homed on premises or online&#x2014;to have access to the same voicemail service in the Microsoft Cloud.</span></span> <span data-ttu-id="7214d-113">雲端語音信箱您內部部署和線上的使用者提供下列優點：</span><span class="sxs-lookup"><span data-stu-id="7214d-113">Cloud Voicemail provides the following benefits for both your on-premises and online users:</span></span>

- <span data-ttu-id="7214d-114">藉由使用 Skype for Business Online、 microsoft Teams 或 Outlook 用戶端在 Exchange 信箱中的語音信箱的存取</span><span class="sxs-lookup"><span data-stu-id="7214d-114">Access to voicemail in their Exchange mailbox by using the Skype for Business Online, Teams, or Outlook clients</span></span>
- <span data-ttu-id="7214d-115">使用 web 式入口網站來管理他們的語音信箱選項的能力</span><span class="sxs-lookup"><span data-stu-id="7214d-115">Ability to use the web-based portal to manage their voicemail options</span></span>

<span data-ttu-id="7214d-116">如需詳細資訊，請參閱[規劃雲端語音信箱服務](../sfbhybrid/hybrid/plan-cloud-voicemail.md)和[計劃 Skype for Business Server 和 Exchange Server 移轉](../sfbhybrid/hybrid/plan-um-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="7214d-116">See [Plan Cloud Voicemail service](../sfbhybrid/hybrid/plan-cloud-voicemail.md) and [Plan for Skype for Business Server and Exchange Server migration](../sfbhybrid/hybrid/plan-um-migration.md) for more information.</span></span>
  
## <a name="call-monitoring-call-data-connector"></a><span data-ttu-id="7214d-117">呼叫監視： 通話資料連接器</span><span class="sxs-lookup"><span data-stu-id="7214d-117">Call monitoring: Call Data Connector</span></span>

<span data-ttu-id="7214d-118">通話資料連接器可大幅簡化了通話監視混合式環境中，因為您不再需要使用不同的內部部署和線上工具集來監視您的使用者通話品質的所有。</span><span class="sxs-lookup"><span data-stu-id="7214d-118">Call Data Connector greatly simplifies call monitoring in a hybrid environment because you no longer need to use different sets of on-premises and online tools to monitor all of your users call quality.</span></span>  <span data-ttu-id="7214d-119">是否適用於您的使用者位於內部部署或線上，您可以選擇要檢視線上您整個組織的通話品質。</span><span class="sxs-lookup"><span data-stu-id="7214d-119">Whether your users are homed on premises or online, you can choose to view call quality for your entire organization online.</span></span>

<span data-ttu-id="7214d-120">與呼叫資料連接器時，您可以使用單一工具組來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="7214d-120">With Call Data Connector, you can perform the following tasks by using a single toolset:</span></span>

- <span data-ttu-id="7214d-121">跨 Microsoft Teams、 Skype for Business Online 和商務用 Skype 商務伺服器監視您的使用者經驗。</span><span class="sxs-lookup"><span data-stu-id="7214d-121">Monitor your user experience across Microsoft Teams, Skype for Business Online, and Skype for Business Server.</span></span>
- <span data-ttu-id="7214d-122">檢視與您網路上進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="7214d-122">View and troubleshoot problems across your network</span></span>
- <span data-ttu-id="7214d-123">指派呼叫分析、 技術服務人員和系統管理員角色，讓您可以讓服務台工作者檢視及疑難排解責任範圍。</span><span class="sxs-lookup"><span data-stu-id="7214d-123">Assign helpdesk and administrator roles for Call Analytics, so that you can empower helpdesk workers to view and troubleshoot their areas of responsibility.</span></span>

<span data-ttu-id="7214d-124">如需詳細資訊，請參閱[規劃通話資料連接器](../sfbhybrid/hybrid/plan-call-data-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="7214d-124">See [Plan Call Data Connector](../sfbhybrid/hybrid/plan-call-data-connector.md) for more information.</span></span>

### <a name="see-also"></a><span data-ttu-id="7214d-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="7214d-125">See also</span></span>

[<span data-ttu-id="7214d-126">功能已被取代從 Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="7214d-126">What's deprecated from Skype for Business Server 2019</span></span>](deprecated.md)
