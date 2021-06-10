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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解如何設定 Microsoft 電話直接路由，將您的內部部署電話基礎結構連接到Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122237"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="a0951-103">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="a0951-103">Configure Direct Routing</span></span>

<span data-ttu-id="a0951-104">Microsoft 電話系統直接路由可讓您將內部部署電話基礎結構連接到Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a0951-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="a0951-105">本文列出將支援的內部部署會話邊界控制器 (SBC) 連接到直接路由所需的高層級步驟，以及如何將 Teams 使用者設定為使用直接路由來連接到公用交換電話網絡 (PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="a0951-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="a0951-106">本文連結至相關文章以尋找詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a0951-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="a0951-107">有關直接路由是否適合貴組織的解決方案，請參閱直接路由[電話系統> 。](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="a0951-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="a0951-108">有關先決條件和規劃部署的資訊，請參閱規劃 [直接路由](direct-routing-plan.md)。</span><span class="sxs-lookup"><span data-stu-id="a0951-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="a0951-109">您也可以觀看下列會話，以瞭解直接路由的好處、如何規劃，[以及如何](https://aka.ms/teams-direct-routing)部署：直接路由在 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a0951-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="a0951-110">若要完成本文說明的步驟，系統管理員需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a0951-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="a0951-111">有關使用 PowerShell 的資訊，請參閱設定您的電腦[Windows PowerShell。](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="a0951-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="a0951-112">在執行這些文章中的步驟之前，Microsoft 建議您確認您的 SBC 已按照 SBC 廠商的建議進行配置：</span><span class="sxs-lookup"><span data-stu-id="a0951-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="a0951-113">AudioCodes 部署檔</span><span class="sxs-lookup"><span data-stu-id="a0951-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a0951-114">Oracle 部署檔</span><span class="sxs-lookup"><span data-stu-id="a0951-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a0951-115">功能區通訊部署檔</span><span class="sxs-lookup"><span data-stu-id="a0951-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a0951-116">TE-Systems (任何) 部署檔</span><span class="sxs-lookup"><span data-stu-id="a0951-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="a0951-117">Metaswitch 部署檔</span><span class="sxs-lookup"><span data-stu-id="a0951-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="a0951-118">有關支援 SBC 的完整清單，請參閱通過直接路由認證的會話 [邊界控制器清單](direct-routing-border-controllers.md)。</span><span class="sxs-lookup"><span data-stu-id="a0951-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="a0951-119">若要設定 Microsoft 電話，並讓使用者使用直接路由，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a0951-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="a0951-120">**步驟 1。**</span><span class="sxs-lookup"><span data-stu-id="a0951-120">**Step 1.**</span></span> [<span data-ttu-id="a0951-121">連線系統Microsoft 電話 SBC 並驗證連接</span><span class="sxs-lookup"><span data-stu-id="a0951-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="a0951-122">**步驟 2.**</span><span class="sxs-lookup"><span data-stu-id="a0951-122">**Step 2.**</span></span> [<span data-ttu-id="a0951-123">啟用使用者進行直接路由、語音和語音信箱</span><span class="sxs-lookup"><span data-stu-id="a0951-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="a0951-124">**步驟 3.**</span><span class="sxs-lookup"><span data-stu-id="a0951-124">**Step 3.**</span></span> [<span data-ttu-id="a0951-125">設定語音路由</span><span class="sxs-lookup"><span data-stu-id="a0951-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="a0951-126">**步驟 4.**</span><span class="sxs-lookup"><span data-stu-id="a0951-126">**Step 4.**</span></span> [<span data-ttu-id="a0951-127">將數位轉換成替代格式</span><span class="sxs-lookup"><span data-stu-id="a0951-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="a0951-128">如果您要為多個租使用者設定 SBC，您也會想要閱讀為多個租使用者設定[SBC。](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="a0951-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a0951-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="a0951-129">Related topics</span></span>

[<span data-ttu-id="a0951-130">電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="a0951-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="a0951-131">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="a0951-131">Plan Direct Routing</span></span>](direct-routing-plan.md)