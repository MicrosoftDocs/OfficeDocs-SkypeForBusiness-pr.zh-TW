---
title: 設定媒體旁路搭配直接路由
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 請閱讀本主題，瞭解如何使用 [電話系統直接路由] 設定媒體旁路。
ms.openlocfilehash: 8d6891d8ecabace3b093e2dc788edee6e9cc5bd1
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837603"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="01616-103">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="01616-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="01616-104">在使用直接路由配置旁路媒體之前，請確定您有[使用直接路由的媒體旁路方案](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="01616-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="01616-105">若要開啟 [媒體旁路]，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="01616-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="01616-106">請確定您的會話邊界控制器（SBC）選擇支援媒體旁路，並提供如何在 SBC 上設定旁路的指示。</span><span class="sxs-lookup"><span data-stu-id="01616-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="01616-107">請參閱認證頁面，瞭解 SBCs、支援媒體旁路的資訊，以及相關指示。</span><span class="sxs-lookup"><span data-stu-id="01616-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="01616-108">您必須使用下列命令在幹線上開啟媒體旁路： **CSOnlinePSTNGateway 身分識別 <sbc_FQDN>-MediaBypass $true**。</span><span class="sxs-lookup"><span data-stu-id="01616-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="01616-109">確定所需的埠已開啟。</span><span class="sxs-lookup"><span data-stu-id="01616-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="01616-110">從非回避 trunks 遷移到旁路啟用的 trunks</span><span class="sxs-lookup"><span data-stu-id="01616-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="01616-111">您可以一次切換所有使用者，或者您可以執行分階段的階段（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="01616-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="01616-112">**一次切換所有使用者。**</span><span class="sxs-lookup"><span data-stu-id="01616-112">**Switch all users at once.**</span></span> <span data-ttu-id="01616-113">如果符合所有條件，您可以開啟 [略過] 模式。</span><span class="sxs-lookup"><span data-stu-id="01616-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="01616-114">不過，您所有的生產使用者都會同時進行切換。</span><span class="sxs-lookup"><span data-stu-id="01616-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="01616-115">因為您在最初設定 trunks 和埠時可能會遇到一些問題，所以您的生產使用者體驗可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="01616-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="01616-116">**分階段的方法。（建議使用）**。</span><span class="sxs-lookup"><span data-stu-id="01616-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="01616-117">針對同一個 SBC （使用不同的埠）建立新的主幹，進行測試，然後變更使用者的線上語音路由原則，以指向新的主幹。</span><span class="sxs-lookup"><span data-stu-id="01616-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="01616-118">這是建議的方法，因為它可讓您更順暢地轉換和不間斷的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="01616-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="01616-119">這個方法需要使用 SBC、新的 FQDN 名稱和防火牆的設定。</span><span class="sxs-lookup"><span data-stu-id="01616-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="01616-120">注意：您必須確認您的憑證同時支援這兩個 trunks。</span><span class="sxs-lookup"><span data-stu-id="01616-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="01616-121">在 SAN 中，您必須有兩個名稱（**sbc1.contoso.com**和**sbc2.contoso.com**），或是擁有萬用字元證書。</span><span class="sxs-lookup"><span data-stu-id="01616-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![從非回避 trunks 遷移到旁路啟用的 trunks）](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="01616-123">如需如何設定 trunks 及執行遷移的指示，請參閱來自 SBC 廠商的檔：</span><span class="sxs-lookup"><span data-stu-id="01616-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="01616-124">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="01616-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="01616-125">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="01616-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="01616-126">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="01616-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="01616-127">TE-系統（anynode）部署檔</span><span class="sxs-lookup"><span data-stu-id="01616-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="01616-128">如需直接路由認證的會話邊界控制器（SBCs）清單，請參閱[認證直接路由的會話 Broder 控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="01616-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="01616-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="01616-129">See also</span></span>

[<span data-ttu-id="01616-130">使用直接路由規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="01616-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



