---
title: 團隊語音 Contoso 案例研究
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
description: 多國企業的小組語音案例研究
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785972"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="42dc5-103">Contoso 案例研究：團隊升級方案</span><span class="sxs-lookup"><span data-stu-id="42dc5-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="42dc5-104">在決定要從商務用 Skype 遷移至團隊時，Contoso 想要為使用者提供簡易轉場體驗。</span><span class="sxs-lookup"><span data-stu-id="42dc5-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="42dc5-105">他們決定要設定混合式連線，並使用重迭的功能方法將使用者移至團隊，而不是同時將每個人切換至團隊。</span><span class="sxs-lookup"><span data-stu-id="42dc5-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="42dc5-106">這可讓團隊和商務用 Skype 內部部署的使用者分享目前狀態並進行通訊。</span><span class="sxs-lookup"><span data-stu-id="42dc5-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="42dc5-107">當使用者進入電話系統的試用版時，他們會移至 [僅限團隊] 模式。</span><span class="sxs-lookup"><span data-stu-id="42dc5-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="42dc5-108">若要瞭解有關升級、方法和模式的基本概念，Contoso 請閱讀下列文章：</span><span class="sxs-lookup"><span data-stu-id="42dc5-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="42dc5-109">開始升級您的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42dc5-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="42dc5-110">從商務用 Skype 升級至 Teams</span><span class="sxs-lookup"><span data-stu-id="42dc5-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="42dc5-111">遷移和互通性指南</span><span class="sxs-lookup"><span data-stu-id="42dc5-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="42dc5-112">Contoso 也參與了 Ignite 2019 會話，[設計從商務用 Skype 至團隊的路徑](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="42dc5-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="42dc5-113">Contoso 已瞭解：</span><span class="sxs-lookup"><span data-stu-id="42dc5-113">Contoso learned about:</span></span>

- <span data-ttu-id="42dc5-114">互通性、同盟和升級行為等基本概念</span><span class="sxs-lookup"><span data-stu-id="42dc5-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="42dc5-115">共存模式與以 TeamsUpgradePolicy 為基礎的管理</span><span class="sxs-lookup"><span data-stu-id="42dc5-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="42dc5-116">最終使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="42dc5-116">End user experience for:</span></span> 

  - <span data-ttu-id="42dc5-117">聊天與通話</span><span class="sxs-lookup"><span data-stu-id="42dc5-117">Chat and Calling</span></span> 

  - <span data-ttu-id="42dc5-118">會議排程</span><span class="sxs-lookup"><span data-stu-id="42dc5-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="42dc5-119">團隊用戶端中的共同作業功能可用性</span><span class="sxs-lookup"><span data-stu-id="42dc5-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="42dc5-120">若要規劃及設定混合式連線性，請先將其內部部署環境移至雲端、Contoso 讀取[規劃混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity)並[設定混合式連接](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)，以瞭解如何進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="42dc5-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="42dc5-121">將其內部部署環境服務設定為與 Office 365 聯盟。</span><span class="sxs-lookup"><span data-stu-id="42dc5-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="42dc5-122">將其內部部署環境設定為信任 Office 365，並啟用 Office 365 共用的 SIP 位址空間</span><span class="sxs-lookup"><span data-stu-id="42dc5-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="42dc5-123">在其 Office 365 租使用者中啟用共用的 SIP 位址空間。</span><span class="sxs-lookup"><span data-stu-id="42dc5-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="42dc5-124">在技術試驗期間使用孤島模式。</span><span class="sxs-lookup"><span data-stu-id="42dc5-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="42dc5-125">使用者啟用電話系統之後，就能將使用者切換成 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="42dc5-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="42dc5-126">TeamsOnly 模式是通話方案和直接路由所必需的。</span><span class="sxs-lookup"><span data-stu-id="42dc5-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
