---
title: 將 Lync 會議室系統裝置遷移到 Microsoft Teams 會議室
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
description: 請閱讀本主題，瞭解如何將 Lync Room System 裝置Microsoft Teams 會議室軟體。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117521"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="6ddcf-103">將 Lync 會議室系統 (LRS) 裝置Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="6ddcf-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="6ddcf-104">Lync Room System (LRS) 裝置與 Skype 會議室系統版本 1 (SRS v1) 軟體于[2018 年 10](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)月 9 日終止支援。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="6ddcf-105">這表示 Skype 會議室系統 v1 軟體將不再取得任何產品更新或修正。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="6ddcf-106">如果客戶的裝置是使用 Skype 會議室系統 v1 軟體的 Lync Room System 裝置，建議您將其裝置升級至「Microsoft Teams 會議室」。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="6ddcf-107">Microsoft Teams 會議室軟體可Microsoft Teams，商務用 Skype Server所有支援裝置上的會議和Microsoft Teams 會議室線上服務。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="6ddcf-108">您的現有裝置 **在** 會議室系統 v1 軟體支援結束後Skype繼續使用。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="6ddcf-109">不過，如果此軟體發生軟體錯誤，需要 Microsoft 發行修正程式，則不支援此修正程式。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="6ddcf-110">SRS v1 會使用 TLS 1.0/ 1.1，Microsoft 未來將會以 TLS 1.0/ 1.1 來代用。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="6ddcf-111">您可以深入瞭解如何準備 [TLS 1.0/1.1 棄用](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="6ddcf-112">哪些裝置受到影響？</span><span class="sxs-lookup"><span data-stu-id="6ddcf-112">Which devices are affected?</span></span>

<span data-ttu-id="6ddcf-113">以下是受此變更影響的裝置清單：</span><span class="sxs-lookup"><span data-stu-id="6ddcf-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="6ddcf-114">Cresron RL</span><span class="sxs-lookup"><span data-stu-id="6ddcf-114">Crestron RL</span></span>
- [<span data-ttu-id="6ddcf-115">Cresron RL2</span><span class="sxs-lookup"><span data-stu-id="6ddcf-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="6ddcf-116">SMART Room 系統</span><span class="sxs-lookup"><span data-stu-id="6ddcf-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="6ddcf-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="6ddcf-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="6ddcf-118">升級選項</span><span class="sxs-lookup"><span data-stu-id="6ddcf-118">Upgrade options</span></span>

<span data-ttu-id="6ddcf-119">有多種選項可升級 Lync 會議室系統至下一代Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="6ddcf-120">Cresron 硬體折中計畫</span><span class="sxs-lookup"><span data-stu-id="6ddcf-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="6ddcf-121">Cresron 會針對所有非 [Crsron](https://www.crestron.com/products/featured-solutions/crestron-sr) Lync Room System 客戶 (例如 Smart 或 Polycom LRS) 提供Crsron SR 系統的升級或同等) 。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="6ddcf-122">請在這裡查看此計畫 [詳細資料，](https://support.crestron.com/app/answers/answer_view/a_id/1000220) 或</span><span class="sxs-lookup"><span data-stu-id="6ddcf-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="6ddcf-123">[電子郵件](mailto:lrsupgrade@crestron.com) Cresron LRS 支援。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="6ddcf-124">將 Cresron RL2 升級至 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="6ddcf-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="6ddcf-125">現有的Crsron RL2 (也稱為Crsron RL200) 客戶可以取得升級套件，以將目前的 RL2 升級為 RL3，每個裝置的成本最低。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="6ddcf-126">請參閱此計畫 [詳細資料](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="6ddcf-127">SMART Room Systems 升級</span><span class="sxs-lookup"><span data-stu-id="6ddcf-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="6ddcf-128">針對 SMART LRS 客戶，除了使用Crsron 硬體折讓方案之外，SMART 也正在努力提供升級至 Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="6ddcf-129">此升級由 SMART Technologies Inc. 在產品支援下提供給客戶。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="6ddcf-130">請在這裡查看有關此 [的更多資訊](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="6ddcf-131">您應該怎麼做？</span><span class="sxs-lookup"><span data-stu-id="6ddcf-131">What should you do?</span></span>

<span data-ttu-id="6ddcf-132">我們建議您使用上述升級選項，在 TLS 1.0/1.1 Microsoft Teams 會議室之前，將 Lync Room System 裝置更新為最新版。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="6ddcf-133">此外，您也可以考慮將現有裝置取代為經過認證的新裝置Microsoft Teams 會議室。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="6ddcf-134">請參閱[會議室裝置](https://aka.ms/roomdevices)以瞭解詳細資料，並查看Microsoft Teams 會議室[需求](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="6ddcf-135">Microsoft Teams 會議室支援自 2018 年 12 月 14 日起使用 App 版本 4.0.64.0 的 TLS 1.2 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="6ddcf-136">對於內部部署客戶，Microsoft Teams 會議室 的 TLS 1.2 啟用通訊需要 商務用 Skype Server 2015 累積更新 9 (CU9) 或 商務用 Skype Server 2019 累積更新 1 (CU1) 。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="6ddcf-137">變更不應影響線上商務用 Skype，因為用戶端變更是向前和向後相容。</span><span class="sxs-lookup"><span data-stu-id="6ddcf-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>