---
title: Teams Contoso 案例研究
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams多國公司的語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093723"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="4a80c-103">Contoso 案例研究：Teams升級計畫</span><span class="sxs-lookup"><span data-stu-id="4a80c-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="4a80c-104">在決定從 商務用 Skype Teams，Contoso 想要為使用者提供輕鬆的轉換體驗。</span><span class="sxs-lookup"><span data-stu-id="4a80c-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="4a80c-105">他們決定設定混合式Teams，並採用重迭功能方法，將使用者移至Teams。</span><span class="sxs-lookup"><span data-stu-id="4a80c-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="4a80c-106">這允許Teams商務用 Skype內部部署中的使用者共用目前狀態和通訊。</span><span class="sxs-lookup"><span data-stu-id="4a80c-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="4a80c-107">當使用者進入試驗電話系統，他們已移至 Teams 模式。</span><span class="sxs-lookup"><span data-stu-id="4a80c-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="4a80c-108">若要瞭解升級、方法及模式的基本概念，Contoso 請閱讀下列文章：</span><span class="sxs-lookup"><span data-stu-id="4a80c-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="4a80c-109">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a80c-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="4a80c-110">適用于 IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="4a80c-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="4a80c-111">移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="4a80c-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="4a80c-112">Contoso 也參加 Ignite 2019 會話設計您從 商務用 Skype[到 Teams。](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)</span><span class="sxs-lookup"><span data-stu-id="4a80c-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="4a80c-113">Contoso 瞭解：</span><span class="sxs-lookup"><span data-stu-id="4a80c-113">Contoso learned about:</span></span>

- <span data-ttu-id="4a80c-114">互通性、聯盟和升級行為等基本概念</span><span class="sxs-lookup"><span data-stu-id="4a80c-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="4a80c-115">以 TeamsUpgradePolicy 為基礎的共存模式和管理</span><span class="sxs-lookup"><span data-stu-id="4a80c-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="4a80c-116">使用者經驗：</span><span class="sxs-lookup"><span data-stu-id="4a80c-116">End user experience for:</span></span> 

  - <span data-ttu-id="4a80c-117">聊天和通話</span><span class="sxs-lookup"><span data-stu-id="4a80c-117">Chat and Calling</span></span> 

  - <span data-ttu-id="4a80c-118">會議排程</span><span class="sxs-lookup"><span data-stu-id="4a80c-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="4a80c-119">用戶端中共同Teams功能的可用性</span><span class="sxs-lookup"><span data-stu-id="4a80c-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="4a80c-120">若要規劃及設定混合式連接，這是將內部部署環境移動到雲端的第一個步驟，Contoso 請閱讀規劃[](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)混合式連接和[](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)設定混合式連接，以瞭解如何：</span><span class="sxs-lookup"><span data-stu-id="4a80c-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="4a80c-121">設定其內部部署環境服務以與 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4a80c-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="4a80c-122">設定其內部部署環境以信任Office 365並啟用共用 SIP 位址空間Office 365</span><span class="sxs-lookup"><span data-stu-id="4a80c-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="4a80c-123">在租使用者中啟用共用 SIP 位址Office 365空間。</span><span class="sxs-lookup"><span data-stu-id="4a80c-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="4a80c-124">在技術試驗期間使用群島模式。</span><span class="sxs-lookup"><span data-stu-id="4a80c-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="4a80c-125">使用者一旦啟用 TeamsOnly 模式，電話系統。</span><span class="sxs-lookup"><span data-stu-id="4a80c-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="4a80c-126">通話方案與直接路由需要 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="4a80c-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>