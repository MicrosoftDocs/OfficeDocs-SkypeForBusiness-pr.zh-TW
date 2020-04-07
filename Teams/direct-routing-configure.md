---
title: 設定直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: 瞭解如何設定 Microsoft Phone 系統 Direct 路由。
ms.openlocfilehash: b596e5acb0002ad90f5c0298b56973f2490ad2e6
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170581"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="8f5eb-103">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="8f5eb-103">Configure Direct Routing</span></span>

<span data-ttu-id="8f5eb-104">Microsoft 手機系統 [直接路由] 可讓您將內部部署的電話結構連線至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="8f5eb-105">本文列出將支援的內部部署會話邊界控制器（SBC）連線至直接路由所需的高層級步驟，以及如何將團隊使用者設定為使用直接路由來連線到公用的交換電話網絡（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8f5eb-106">本文將連結至相關的文章，以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="8f5eb-107">如需有關直銷路由是否適合貴組織的相關資訊，請參閱[手機系統 Direct 路由](direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="8f5eb-108">如需系統必備及規劃部署的相關資訊，請參閱[規劃直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="8f5eb-109">您也可以觀看下列會話，瞭解直接路由的優點、如何規劃，以及部署方式：[直接在 Microsoft 團隊中傳送路線](https://aka.ms/teams-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="8f5eb-110">若要完成本文所述的步驟，管理員需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="8f5eb-111">如需有關使用 PowerShell 的詳細資訊，請參閱[設定您的 Windows PowerShell 電腦](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="8f5eb-112">在執行這些文章中的步驟之前，Microsoft 建議您確認您的 SBC 已按照您的 SBC 廠商的建議進行設定：</span><span class="sxs-lookup"><span data-stu-id="8f5eb-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="8f5eb-113">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="8f5eb-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="8f5eb-114">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="8f5eb-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="8f5eb-115">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="8f5eb-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="8f5eb-116">TE-系統（anynode）部署檔</span><span class="sxs-lookup"><span data-stu-id="8f5eb-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="8f5eb-117">Metaswitch 部署檔</span><span class="sxs-lookup"><span data-stu-id="8f5eb-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="8f5eb-118">如需支援的 SBCs 完整清單，請參閱針對[直接路由認證的會話邊界控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="8f5eb-119">若要設定 Microsoft 手機系統並讓使用者使用直接路由，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="8f5eb-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="8f5eb-120">**步驟1。**</span><span class="sxs-lookup"><span data-stu-id="8f5eb-120">**Step 1.**</span></span> [<span data-ttu-id="8f5eb-121">將 SBC 與 Microsoft Phone 系統連接並驗證連接</span><span class="sxs-lookup"><span data-stu-id="8f5eb-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="8f5eb-122">**步驟2。**</span><span class="sxs-lookup"><span data-stu-id="8f5eb-122">**Step 2.**</span></span> [<span data-ttu-id="8f5eb-123">允許使用者使用直接路由、語音及語音信箱</span><span class="sxs-lookup"><span data-stu-id="8f5eb-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8f5eb-124">**步驟3。**</span><span class="sxs-lookup"><span data-stu-id="8f5eb-124">**Step 3.**</span></span> [<span data-ttu-id="8f5eb-125">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="8f5eb-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8f5eb-126">**步驟4。**</span><span class="sxs-lookup"><span data-stu-id="8f5eb-126">**Step 4.**</span></span> [<span data-ttu-id="8f5eb-127">將數位轉換成替換格式</span><span class="sxs-lookup"><span data-stu-id="8f5eb-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8f5eb-128">如果您要為多個租使用者設定 SBC，您也會想要[為多個](direct-routing-sbc-multiple-tenants.md)租使用者閱讀 [設定 sbc]。</span><span class="sxs-lookup"><span data-stu-id="8f5eb-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8f5eb-129">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8f5eb-129">See also</span></span>

[<span data-ttu-id="8f5eb-130">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="8f5eb-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="8f5eb-131">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="8f5eb-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

