---
title: Teams僅模式考慮事項
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: landerl
description: 系統管理員可以瞭解如何在系統管理中心Microsoft Teams升級至 Microsoft Teams模式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2232d4774a31f3b081b2410371a5903debe9123
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239010"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="3d7ff-103">Teams僅模式考慮事項</span><span class="sxs-lookup"><span data-stu-id="3d7ff-103">Teams Only mode considerations</span></span>

<span data-ttu-id="3d7ff-104">組織或Microsoft 365 Office 365系統管理員可以將個別使用者或整個租使用者升級Teams模式。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-104">Administrators of Microsoft 365 or Office 365 organizations can upgrade either individual users or the entire tenant to Teams Only mode.</span></span>  

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="3d7ff-105">升級至 Teams 模式可透過單一用戶端體驗，為使用者提供 Microsoft Teams 的完整權益，Microsoft 365或 Office 365 團隊合作中心。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-105">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Microsoft 365 or Office 365, via a single client experience.</span></span> <span data-ttu-id="3d7ff-106">在 Teams 模式的使用者，無論寄件者是使用 商務用 Skype 或 Teams，都會在 Teams 中接聽所有通話和聊天，並受益于交互操作和聯盟支援。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-106">Users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="3d7ff-107">雖然有數千名客戶已成功升級至 Microsoft Teams，但有些考慮可能會影響貴組織的升級時程表和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-107">Although thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization's upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="3d7ff-108">為了獲得最佳使用者體驗，請確認 Teams 符合您的共同作業與通訊需求，並確認您的網路已準備好可支援 Teams，並在將使用者升級至 Teams 之前，先進行您的使用者整備計劃。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-108">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3d7ff-109">如果您剛開始進行升級規劃，請務必參考我們的升級指南Microsoft Teams[入門](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-109">If you are just starting your upgrade planning, be sure to review our [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md) guide.</span></span> 

<span data-ttu-id="3d7ff-110">**共存考慮：** 已經使用 商務用 Skype Online 和/或 商務用 Skype Server 的組織Teams以符合其需求的速度，將應用程式引入環境。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-110">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="3d7ff-111">組織可根據需要將 Teams逐步推出至想要的使用者集，而使用 Teams 的使用者可以與使用 商務用 Skype 的使用者通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-111">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="3d7ff-112">若要管理此體驗，系統管理員會使用共存模式，定義使用者用戶端體驗、傳入聊天和通話的路由行為，以及是否要在 Teams 或 商務用 Skype 中排程新會議。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-112">To manage this experience, administrators use coexistence modes, which define the end-user client experience, the routing behavior of incoming chats and calls, and whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="3d7ff-113">如果使用者升級為只升級為 **Teams，使用者可以與其他組織中的使用者進行Teams。** 不過，當兩個使用者使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-113">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="3d7ff-114">升級至 Teams 的使用者仍然可以加入商務用 Skype會議。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-114">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3d7ff-115">如需有關共存的詳細資訊，請參閱瞭解Microsoft Teams[及商務用 Skype互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-115">For more detailed information about coexistence, please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> <span data-ttu-id="3d7ff-116">如要進一Teams與Skype (消費者) ，請參閱Teams[及Skype互通性](teams-skype-interop.md)。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-116">For more information about Teams and Skype (Consumer), see [Teams and Skype interoperability](teams-skype-interop.md).</span></span>


<span data-ttu-id="3d7ff-117">**使用者特定考慮**：某些使用者案例仍在演進中，系統管理員可能會決定暫時延後特定使用者的升級，同時升級組織的其他使用者。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-117">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="3d7ff-118">特別是，我們仍在處理主要裝置為 VDI 的使用者案例。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-118">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="3d7ff-119">針對網站公告，請監控 Microsoft 365[藍圖](https://www.microsoft.com/microsoft-365/roadmap)。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-119">For site announcements, monitor the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

> [!NOTE]
> <span data-ttu-id="3d7ff-120">在移至僅Teams模式之前，您需要更換或更新不支援此Teams。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-120">Before you move to Teams Only mode you need to replace or update devices that don't support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="3d7ff-121">**請記住**：移轉Teams移轉並不僅僅是技術移轉。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-121">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="3d7ff-122">成功的升級會評估技術準備狀態和使用者準備狀態。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-122">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="3d7ff-123">請閱商務用 Skype升級Teams指南，以進一[](upgrade-framework.md)步規劃升級至Teams。</span><span class="sxs-lookup"><span data-stu-id="3d7ff-123">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
