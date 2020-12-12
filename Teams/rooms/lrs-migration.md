---
title: 將 Lync 室系統裝置遷移至 Microsoft 團隊聊天室
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: 請閱讀本主題，瞭解如何將 Lync 室系統裝置遷移至使用 Microsoft 團隊聊天室軟體。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662618"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="0f2b1-103">將 Lync 會議室系統 (LRS) 裝置遷移至 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="0f2b1-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="0f2b1-104">Lync 會議室系統 (LRS) 使用 Skype 室系統版本 1 (SR v1) 軟體的裝置已 [于2018年10月9日取得支援結束](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="0f2b1-105">這表示 Skype 會議室系統 v1 軟體將不再取得任何產品更新或修正。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="0f2b1-106">如果客戶的裝置是使用 Skype 會議室系統 v1 軟體的 Lync Room System 裝置，建議您將其裝置升級至「Microsoft Teams 會議室」。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="0f2b1-107">Microsoft 團隊會議室軟體除了適用于 Microsoft 團隊之外，還可與 Microsoft 團隊搭配使用，在所有 Microsoft 團隊會議室支援的裝置上進行會議與通話的商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="0f2b1-108">在 Skype 會議室系統版本1之後，您現有的裝置 **可能會** 繼續運作。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="0f2b1-109">不過，如果這個軟體遇到需要 Microsoft 釋放修正程式的軟體錯誤，就不會受到支援。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="0f2b1-110">SRS v1 使用的是 TLS 1.0/1.1，在未來將會被 Microsoft 取代。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="0f2b1-111">您可以深入瞭解如何 [針對 TLS 1.0/1.1 過時進行準備](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="0f2b1-112">哪些裝置會受到影響？</span><span class="sxs-lookup"><span data-stu-id="0f2b1-112">Which devices are affected?</span></span>

<span data-ttu-id="0f2b1-113">以下是受此變更影響的裝置清單：</span><span class="sxs-lookup"><span data-stu-id="0f2b1-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="0f2b1-114">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="0f2b1-114">Crestron RL</span></span>
- [<span data-ttu-id="0f2b1-115">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="0f2b1-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="0f2b1-116">智慧房間系統</span><span class="sxs-lookup"><span data-stu-id="0f2b1-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="0f2b1-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="0f2b1-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="0f2b1-118">升級選項</span><span class="sxs-lookup"><span data-stu-id="0f2b1-118">Upgrade options</span></span>

<span data-ttu-id="0f2b1-119">有多個選項可將 Lync 系統升級至新一代的 Microsoft 團隊會議室。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="0f2b1-120">Crestron 硬體外貿程式</span><span class="sxs-lookup"><span data-stu-id="0f2b1-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="0f2b1-121">Crestron 將會提供 [CRESTRON SR 系統](https://www.crestron.com/products/featured-solutions/crestron-sr) 的升級，或針對所有非 Crestron Lync 會議室系統客戶的更新， (例如 Smart 或 Polycom LRS) 。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="0f2b1-122">請 [在](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 此查看此程式的詳細資料，或</span><span class="sxs-lookup"><span data-stu-id="0f2b1-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="0f2b1-123">[電子郵件](mailto:lrsupgrade@crestron.com) Crestron LRS 支援。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="0f2b1-124">Crestron RL2 升級至 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="0f2b1-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="0f2b1-125">現有的 Crestron RL2 (也稱為 Crestron RL200) 客戶可以取得升級套件，以將目前的 RL2 升級至 RL3，以在每個裝置上使用最低成本。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="0f2b1-126">請 [在](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)此查看此程式的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="0f2b1-127">智慧房間系統升級</span><span class="sxs-lookup"><span data-stu-id="0f2b1-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="0f2b1-128">針對智慧型 LRS 客戶而言，除了 Crestron 硬體交易程式之外，聰明也是提供升級至 Microsoft 團隊聊天室的解決方案。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="0f2b1-129">此升級將由 SMART 技術 Inc. 提供給客戶，以供產品支援人員使用。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="0f2b1-130">請 [在](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)此查看更多相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="0f2b1-131">您該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="0f2b1-131">What should you do?</span></span>

<span data-ttu-id="0f2b1-132">我們建議您先使用上述升級選項，在 TLS 1.0/1.1 過時版本中，將 Lync 室系統裝置更新為 Microsoft 團隊聊天室。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="0f2b1-133">此外，您也可以考慮使用針對 Microsoft 團隊聊天室認證的新裝置來取代現有的裝置。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="0f2b1-134">如需詳細資訊，請參閱 [會議室裝置](https://aka.ms/roomdevices) ，並查看 [Microsoft 團隊會議室需求](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="0f2b1-135">Microsoft 團隊聊天室軟體支援 TLS 1.2 通訊協定，在2018中有應用程式版本4.0.64.0 的12月14日。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="0f2b1-136">針對內部部署客戶，在 Microsoft 團隊聊天室啟用經由 TLS 1.2 的通訊需要商務用 Skype Server 2015 累計更新 9 (CU9) 或商務用 Skype Server 2019 累加更新 1 (CU1) 。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="0f2b1-137">因為用戶端變更是轉寄及後相容，所以變更不應該影響商務用 Skype Online 客戶。</span><span class="sxs-lookup"><span data-stu-id="0f2b1-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
