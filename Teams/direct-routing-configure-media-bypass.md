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
description: 瞭解如何設定媒體旁路電話系統直接路由Microsoft Teams一次切換所有使用者，或採用建議的逐步 (方法) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416893"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="ecd99-103">設定媒體旁路搭配直接路由</span><span class="sxs-lookup"><span data-stu-id="ecd99-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="ecd99-104">使用直接路由來配置媒體旁路之前，請務必先閱讀使用直接路由 [的媒體旁路方案](direct-routing-plan-media-bypass.md)。</span><span class="sxs-lookup"><span data-stu-id="ecd99-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="ecd99-105">若要開啟媒體旁路，必須符合下列條件：</span><span class="sxs-lookup"><span data-stu-id="ecd99-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="ecd99-106">請確定您的會話邊界控制器 (選擇) 廠商支援媒體旁路，並提供如何在 SBC 上設定旁路的指示。</span><span class="sxs-lookup"><span data-stu-id="ecd99-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="ecd99-107">請參閱認證頁面，以瞭解支援媒體旁路的 SBCs，以及指示。</span><span class="sxs-lookup"><span data-stu-id="ecd99-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="ecd99-108">您需要使用下列命令開啟主幹上的媒體旁路 **：Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true。**</span><span class="sxs-lookup"><span data-stu-id="ecd99-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="ecd99-109">請確定已開啟所需的埠。</span><span class="sxs-lookup"><span data-stu-id="ecd99-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="ecd99-110">從未忽略的主幹遷移到已啟用旁路的主幹</span><span class="sxs-lookup"><span data-stu-id="ecd99-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="ecd99-111">您可以一次切換所有使用者，也可以按照建議的方式， (逐步) 。</span><span class="sxs-lookup"><span data-stu-id="ecd99-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="ecd99-112">**一次切換所有使用者。**</span><span class="sxs-lookup"><span data-stu-id="ecd99-112">**Switch all users at once.**</span></span> <span data-ttu-id="ecd99-113">如果符合所有條件，您可以開啟旁路模式。</span><span class="sxs-lookup"><span data-stu-id="ecd99-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="ecd99-114">不過，所有生產使用者都會同時切換。</span><span class="sxs-lookup"><span data-stu-id="ecd99-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="ecd99-115">由於您一開始在設定主幹和埠時可能會遇到一些問題，因此您的生產使用者體驗可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="ecd99-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="ecd99-116">**階段方法。 (建議) 。**</span><span class="sxs-lookup"><span data-stu-id="ecd99-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="ecd99-117">為具有不同埠 (的同一個 SBC) 建立新主幹、進行測試，並變更使用者指向新主幹的線上語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="ecd99-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="ecd99-118">這是建議的方法，因為它可讓轉場更順暢，且使用者體驗不受干擾。</span><span class="sxs-lookup"><span data-stu-id="ecd99-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="ecd99-119">此方法需要 SBC 的組組、新的 FQDN 名稱，以及防火牆的組組。</span><span class="sxs-lookup"><span data-stu-id="ecd99-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="ecd99-120">請注意，您必須確定憑證支援這兩個主幹。</span><span class="sxs-lookup"><span data-stu-id="ecd99-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="ecd99-121">在 SAN 中，您必須有兩個名稱 (sbc1.contoso.com，sbc2.contoso.com) 萬用字元憑證。  </span><span class="sxs-lookup"><span data-stu-id="ecd99-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![從未忽略的主幹遷移到已啟用旁路的主幹) ](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="ecd99-123">有關如何設定主幹並執行移移的指示，請參閱 SBC 廠商提供的檔：</span><span class="sxs-lookup"><span data-stu-id="ecd99-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="ecd99-124">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="ecd99-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="ecd99-125">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="ecd99-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="ecd99-126">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="ecd99-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="ecd99-127">TE-Systems (任何) 部署檔</span><span class="sxs-lookup"><span data-stu-id="ecd99-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="ecd99-128">有關已通過直接路由 (SBC 的會話邊界控制器) ，請參閱通過直接路由認證的 [會話布](direct-routing-border-controllers.md)羅德控制器清單。</span><span class="sxs-lookup"><span data-stu-id="ecd99-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="ecd99-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="ecd99-129">Related topics</span></span>

[<span data-ttu-id="ecd99-130">使用直接路由規劃媒體旁路</span><span class="sxs-lookup"><span data-stu-id="ecd99-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



