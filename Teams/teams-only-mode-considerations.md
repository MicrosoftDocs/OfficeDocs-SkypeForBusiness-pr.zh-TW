---
title: 僅限團隊的模式考慮
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dearbeen
description: 準備升級至 [僅限 Microsoft 團隊] 模式
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsupgrade.upgradetoteams
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7ec2d9ede5fdd31070228995cefaa16a60ad6224
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42795996"
---
# <a name="teams-only-mode-considerations"></a><span data-ttu-id="87132-103">僅限團隊的模式考慮</span><span class="sxs-lookup"><span data-stu-id="87132-103">Teams Only mode considerations</span></span>

<span data-ttu-id="87132-104">如果您是 Office 365 租使用者的系統管理員，您現在會在 Microsoft 團隊系統管理中心看到 [升級為團隊專用模式] 的選項。</span><span class="sxs-lookup"><span data-stu-id="87132-104">If you are an administrator on your Office 365 tenant, you will now see the option to upgrade to Teams Only mode in the Microsoft Teams admin center.</span></span> <span data-ttu-id="87132-105">使用此功能，您可以升級個別使用者或整個租使用者。</span><span class="sxs-lookup"><span data-stu-id="87132-105">With this functionality you can upgrade either individual users, or alternatively, the entire tenant.</span></span>  

<span data-ttu-id="87132-106">升級至 [僅限團隊] 模式可透過單一用戶端體驗，為使用者提供 Microsoft 團隊的全部好處，即在 Office 365 中進行團隊合作的中心。</span><span class="sxs-lookup"><span data-stu-id="87132-106">Upgrading to Teams Only mode offers users the full benefits of Microsoft Teams, the hub for teamwork in Office 365, via a single client experience.</span></span> <span data-ttu-id="87132-107">此外，[團隊專用] 模式中的使用者會在團隊中收到所有通話和聊天，不論寄件者是使用商務用 Skype 還是小組，以及互通性與同盟支援的好處。</span><span class="sxs-lookup"><span data-stu-id="87132-107">Additionally, users in Teams Only mode will receive all calls and chats in Teams, regardless of whether the sender is using Skype for Business or Teams, and benefit from interop and federation support.</span></span>

<span data-ttu-id="87132-108">雖然成千上萬的客戶已成功升級至 Microsoft 團隊，但在這種情況下，可能也會影響貴組織的升級時程表和使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="87132-108">While thousands of customers have successfully upgraded to Microsoft Teams, there are considerations that may influence your organization’s upgrade timeline and user experience along the way.</span></span> <span data-ttu-id="87132-109">特別是，升級選項並不一定表示貴組織已準備好進行這項變更。</span><span class="sxs-lookup"><span data-stu-id="87132-109">In particular, having the option to upgrade doesn’t necessarily mean your organization is ready for this change.</span></span> <span data-ttu-id="87132-110">為了獲得最佳使用者體驗，請確認 Teams 符合您的共同作業與通訊需求，並確認您的網路已準備好可支援 Teams，並在將使用者升級至 Teams 之前，先進行您的使用者整備計劃。</span><span class="sxs-lookup"><span data-stu-id="87132-110">For the best user experience, confirm that Teams meets your collaboration and communication requirements, make sure that your network is ready to support Teams, and implement your user readiness plan before upgrading users to Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="87132-111">如果您剛剛開始升級規劃，請務必複習我們的完整升級指導方針和規劃資源。</span><span class="sxs-lookup"><span data-stu-id="87132-111">If you are just starting your upgrade planning, be sure to review our full upgrade guidance and planning resources.</span></span> <span data-ttu-id="87132-112">[從這裡開始](upgrade-start-here.md)。</span><span class="sxs-lookup"><span data-stu-id="87132-112">[Start here](upgrade-start-here.md).</span></span> 

<span data-ttu-id="87132-113">**共存考慮**：已使用商務用 skype Online 和/或商務用 skype 伺服器的組織，會以符合其需求的節奏，將小組引入他們的環境中。</span><span class="sxs-lookup"><span data-stu-id="87132-113">**Coexistence considerations**: Organizations already using Skype for Business Online and/or Skype for Business Server can introduce Teams into their environment at a pace that meets their needs.</span></span> <span data-ttu-id="87132-114">組織可以視需要將團隊逐漸推出給所需的使用者組，而使用團隊的使用者可以與使用商務用 Skype 的使用者通訊，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="87132-114">Organizations can incrementally roll out Teams to a desired set of users as needed, and users who use Teams can communicate with users who use Skype for Business and vice versa.</span></span> <span data-ttu-id="87132-115">若要管理此體驗，系統管理員會使用共存模式來定義最終使用者用戶端體驗、傳入聊天和通話的傳送行為，以及是否在團隊或商務用 Skype 中排程新會議。</span><span class="sxs-lookup"><span data-stu-id="87132-115">To manage this experience, administrators use coexistence modes, which define the end user client experience, the routing behavior of incoming chats and calls, as well as whether new meetings are scheduled in Teams or Skype for Business.</span></span> <span data-ttu-id="87132-116">如果使用者只升級至**團隊**，則使用者可以與其他組織中的使用者聯盟;不過，當兩個使用者都使用團隊時，就會提供最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="87132-116">Users can federate with users in other organizations if the user is upgraded to **Teams Only**; however, the best experience is provided when both users use Teams.</span></span> <span data-ttu-id="87132-117">已升級至團隊的使用者仍然可以加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="87132-117">Users who are upgraded to Teams Only can still join Skype for Business meetings.</span></span> 

> [!NOTE]
> <span data-ttu-id="87132-118">已升級至團隊的使用者將無法與使用客戶用 Skype 的使用者進行通訊。</span><span class="sxs-lookup"><span data-stu-id="87132-118">Users who are upgraded to Teams Only cannot communicate with users who are using Skype for Consumer.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87132-119">如需有關共存的詳細資訊，請參閱[瞭解 Microsoft 團隊及商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="87132-119">For more detailed information about coexistence please refer to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span> 

<span data-ttu-id="87132-120">**整個租**使用者的考慮：我們正在努力在下列環境中啟用團隊;不過，如果您的商務用 Skype 租使用者是以下列其中一種環境為宿主，系統管理員就不應該升級組織中的任何使用者：</span><span class="sxs-lookup"><span data-stu-id="87132-120">**Tenant-wide considerations**: We are working on enabling Teams in the following environments; however, for now, administrators shouldn't upgrade any users in their organization if their Skype for Business tenant is hosted in one of the following environments:</span></span>

 - <span data-ttu-id="87132-121">由世紀互聯運營的 Office 365</span><span class="sxs-lookup"><span data-stu-id="87132-121">Office 365 operated by 21Vianet</span></span>
 - <span data-ttu-id="87132-122">Office 365 德國</span><span class="sxs-lookup"><span data-stu-id="87132-122">Office 365 Germany</span></span>
 - <span data-ttu-id="87132-123">商務用 Skype 租使用者託管于韓國 **，** 組織需要將團隊資料儲存在韓國中。</span><span class="sxs-lookup"><span data-stu-id="87132-123">Skype for Business tenant is hosted in South Korea **and** the organization requires Teams data to be stored in South Korea.</span></span> <span data-ttu-id="87132-124">目前，以韓國所儲存的商務用 Skype 資料升級至團隊的組織，會將其小組資料儲存在亞太地區，而不是在韓國資料中心區域中。</span><span class="sxs-lookup"><span data-stu-id="87132-124">Currently, organizations with Skype for Business data stored in South Korea that upgrade to Teams will have their Teams data stored in the Asia datacenter region, not in the South Korea datacenter region.</span></span>

<span data-ttu-id="87132-125">**使用者專用的考慮**：有些使用者案例仍在演變，管理員可能會決定在升級組織中的其他使用者時，暫時推遲特定使用者的升級。</span><span class="sxs-lookup"><span data-stu-id="87132-125">**User-specific considerations**: Some user scenarios are still evolving, and administrators may decide to temporarily postpone the upgrade of certain users while upgrading other users in the organization.</span></span> <span data-ttu-id="87132-126">特別是，我們仍在針對主要裝置是使用 VDI 的使用者解決案例。</span><span class="sxs-lookup"><span data-stu-id="87132-126">In particular, we are still working on addressing scenarios for users whose primary device is VDI-based.</span></span> <span data-ttu-id="87132-127">請監控[Office 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap)網站以取得通知。</span><span class="sxs-lookup"><span data-stu-id="87132-127">Please monitor the [Office 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) site for announcements.</span></span>

> [!NOTE]
> <span data-ttu-id="87132-128">在您移至 [僅限團隊] 模式前，您需要更換或更新不支援小組的裝置。</span><span class="sxs-lookup"><span data-stu-id="87132-128">Before you move to Teams Only mode you need to replace or update devices that don’t support Teams.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="87132-129">**請記住**： [移至] 團隊不只是技術遷移。</span><span class="sxs-lookup"><span data-stu-id="87132-129">**Remember**: The move to Teams is more than a technical migration.</span></span> <span data-ttu-id="87132-130">成功的升級會評估技術就緒性和最終使用者就緒性。</span><span class="sxs-lookup"><span data-stu-id="87132-130">A successful upgrade assesses both technical readiness and end-user readiness.</span></span> <span data-ttu-id="87132-131">如需規劃升級至團隊的相關詳細資訊，請參閱商務用 Skype 的團隊[升級指導](upgrade-framework.md)方針。</span><span class="sxs-lookup"><span data-stu-id="87132-131">Review our Skype for Business to Teams [upgrade guidance](upgrade-framework.md) for more information on planning an implementing your upgrade to Teams.</span></span>  
