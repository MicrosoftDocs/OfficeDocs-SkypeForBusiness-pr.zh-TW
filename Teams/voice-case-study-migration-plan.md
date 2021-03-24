---
title: Teams Voice Contoso 案例研究
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
description: 多國公司的 Teams 語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0da56bc0da083654a0cd694bd5983f2fe4fe515
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093723"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="433f2-103">Contoso 案例研究：Teams 升級計畫</span><span class="sxs-lookup"><span data-stu-id="433f2-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="433f2-104">在決定從商務用 Skype 遷移到 Teams 時，Contoso 想要為使用者提供輕鬆的轉換體驗。</span><span class="sxs-lookup"><span data-stu-id="433f2-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="433f2-105">他們決定不同時將所有人切換到 Teams，而是決定設定混合式連接，並使用重迭功能方法將使用者移至 Teams。</span><span class="sxs-lookup"><span data-stu-id="433f2-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="433f2-106">這允許 Teams 和商務用 Skype 內部部署中的使用者共用目前狀態和通訊。</span><span class="sxs-lookup"><span data-stu-id="433f2-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="433f2-107">當使用者進入手機系統的試驗時，他們已移至 Teams Only 模式。</span><span class="sxs-lookup"><span data-stu-id="433f2-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="433f2-108">若要瞭解升級、方法及模式的基本概念，Contoso 請閱讀下列文章：</span><span class="sxs-lookup"><span data-stu-id="433f2-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="433f2-109">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="433f2-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="433f2-110">IT 系統管理員的升級策略</span><span class="sxs-lookup"><span data-stu-id="433f2-110">Upgrade strategies for IT administrators</span></span>](upgrade-to-teams-on-prem-implement.md) 
- [<span data-ttu-id="433f2-111">移移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="433f2-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="433f2-112">Contoso 也參加 Ignite 2019 會話，設計從商務用 [Skype 到 Teams 的路徑](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="433f2-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="433f2-113">Contoso 瞭解：</span><span class="sxs-lookup"><span data-stu-id="433f2-113">Contoso learned about:</span></span>

- <span data-ttu-id="433f2-114">互通性、聯盟和升級行為等基本概念</span><span class="sxs-lookup"><span data-stu-id="433f2-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="433f2-115">以 TeamsUpgradePolicy 為基礎的共存模式和管理</span><span class="sxs-lookup"><span data-stu-id="433f2-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="433f2-116">使用者經驗：</span><span class="sxs-lookup"><span data-stu-id="433f2-116">End user experience for:</span></span> 

  - <span data-ttu-id="433f2-117">聊天和通話</span><span class="sxs-lookup"><span data-stu-id="433f2-117">Chat and Calling</span></span> 

  - <span data-ttu-id="433f2-118">會議排程</span><span class="sxs-lookup"><span data-stu-id="433f2-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="433f2-119">Teams 用戶端中的共同合作功能可用性</span><span class="sxs-lookup"><span data-stu-id="433f2-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="433f2-120">若要規劃及設定混合式連接，這是將內部部署環境移動到雲端的第一個步驟，Contoso 請閱讀規劃[](/SkypeForBusiness/hybrid/plan-hybrid-connectivity)混合式連接和[](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)設定混合式連接，以瞭解如何：</span><span class="sxs-lookup"><span data-stu-id="433f2-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="433f2-121">設定其內部部署環境服務以與 Office 365 進行聯合。</span><span class="sxs-lookup"><span data-stu-id="433f2-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="433f2-122">設定其內部部署環境以信任 Office 365，並啟用 Office 365 的共用 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="433f2-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="433f2-123">在 Office 365 租使用者中啟用共用 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="433f2-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="433f2-124">在技術試驗期間使用群島模式。</span><span class="sxs-lookup"><span data-stu-id="433f2-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="433f2-125">使用者啟用電話系統後，切換至 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="433f2-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="433f2-126">通話方案與直接路由需要 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="433f2-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span>