---
title: 團隊到期與續約Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: abgupta
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: 瞭解團隊到期與續約，以及如何使用群組Microsoft 365政策，在團隊中自動清理未使用的Microsoft Teams。
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 606d957b703725d631beec38237f4d9b4272433e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116951"
---
# <a name="team-expiration-and-renewal-in-microsoft-teams"></a><span data-ttu-id="95341-103">團隊到期與續約Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95341-103">Team expiration and renewal in Microsoft Teams</span></span>

<span data-ttu-id="95341-104">擁有大量團隊的組織通常擁有從未實際使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="95341-104">Organizations with a large number of teams often have teams that are never actually used.</span></span> <span data-ttu-id="95341-105">發生此情況的原因有幾個，包括產品試驗、短期小組共同合作，或團隊擁有者離開組織。</span><span class="sxs-lookup"><span data-stu-id="95341-105">This can happen because of several reasons including product experimentation, short-term team collaboration, or team owners leaving the organization.</span></span> <span data-ttu-id="95341-106">隨著時間的過去，這類團隊可能會累積並給租使用者資源造成負擔。</span><span class="sxs-lookup"><span data-stu-id="95341-106">Over time, such teams can accumulate and create a burden on tenant resources.</span></span>  

<span data-ttu-id="95341-107">若要限制未使用的團隊數量，作為系統管理員，您可以使用群組到期Microsoft 365[自動](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)清理未使用的團隊。</span><span class="sxs-lookup"><span data-stu-id="95341-107">To curb the number of unused teams, as an admin, you can use [Microsoft 365 group expiration policy](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy) to automatically clean up unused teams.</span></span> <span data-ttu-id="95341-108">由於團隊是由群組所支援，因此群組到期原則也會自動適用于團隊。</span><span class="sxs-lookup"><span data-stu-id="95341-108">Because teams are backed by groups, group expiration policies automatically apply to teams as well.</span></span>

<span data-ttu-id="95341-109">當您將到期原則適用于團隊時，團隊擁有者會于團隊到期日前 30 天、15 天和 1 天收到小組續約通知。</span><span class="sxs-lookup"><span data-stu-id="95341-109">When you apply an expiration policy to a team, a team owner receives a notification for team renewal 30 days, 15 days and 1 day before the team's expiration date.</span></span> <span data-ttu-id="95341-110">當團隊擁有者收到通知時，他們可以按一下 **[在** 小組設定中立即續約以續約團隊。</span><span class="sxs-lookup"><span data-stu-id="95341-110">When the team owner receives the notification, they can click **Renew now** in team settings to renew the team.</span></span>

<span data-ttu-id="95341-111">![在小組設定中更新團隊的立即續約按鈕螢幕擷取畫面](media/team-expiration.png "在小組設定中更新團隊的立即續約按鈕螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="95341-111">![Screenshot of the Renew Now button to renew a team in team settings](media/team-expiration.png "Screenshot of the Renew Now button to renew a team in team settings")</span></span>

<span data-ttu-id="95341-112">如果團隊擁有者未為小組續約，且在到期政策結束之前團隊中沒有任何進一步活動，團隊會置於「柔刪除」狀態，這表示小組可以在接下來 30 天內還原。</span><span class="sxs-lookup"><span data-stu-id="95341-112">If the team owner doesn't renew the team and there is no further activity on the team until the end of the expiration policy, the team is put in a "soft-deleted" state, which means it can be restored within the next 30 days.</span></span>

## <a name="team-auto-renewal"></a><span data-ttu-id="95341-113">小組自動續約</span><span class="sxs-lookup"><span data-stu-id="95341-113">Team auto-renewal</span></span>

<span data-ttu-id="95341-114">有時候，團隊擁有者可能因為忘記續約或因續約到期而無法續約。</span><span class="sxs-lookup"><span data-stu-id="95341-114">There can be times when a team owner is unable to renew the team perhaps because they forgot to renew or were away when renewal was due.</span></span> <span data-ttu-id="95341-115">在這些情況下，使用中團隊可能會因為適用于該團隊的到期原則而被刪除。</span><span class="sxs-lookup"><span data-stu-id="95341-115">In these scenarios, a team in active use can get deleted because of expiration policies that apply to the team.</span></span>  

<span data-ttu-id="95341-116">為了防止意外刪除，群組到期政策中的小組會自動啟用自動續約。</span><span class="sxs-lookup"><span data-stu-id="95341-116">To prevent accidental deletion, auto-renewal is automatically enabled for a team in the group expiration policy.</span></span> <span data-ttu-id="95341-117">設定群組到期政策時，任何在到期日之前至少有一個頻道拜訪的小組都會自動續約，而不需要團隊擁有者手動介入。</span><span class="sxs-lookup"><span data-stu-id="95341-117">When the group expiration policy is set up, any team that has at least one channel visit from any team member before its expiration date is automatically renewed without any manual intervention from the team owner.</span></span>

## <a name="known-issues"></a><span data-ttu-id="95341-118">已知問題</span><span class="sxs-lookup"><span data-stu-id="95341-118">Known issues</span></span>

<span data-ttu-id="95341-119">**團隊與基礎群組的到期日不相符**</span><span class="sxs-lookup"><span data-stu-id="95341-119">**Expiration date of team and underlying group don't match**</span></span>

<span data-ttu-id="95341-120">在團隊續約之前，先續約支援小組的群組。</span><span class="sxs-lookup"><span data-stu-id="95341-120">Before a team is renewed, the group that backs the team is renewed first.</span></span> <span data-ttu-id="95341-121">續約的一部分，會為群組設定未來日期的新到期日。</span><span class="sxs-lookup"><span data-stu-id="95341-121">As part of renewal, a new expiry date is set on the group for a future date.</span></span> <span data-ttu-id="95341-122">此新日期可能不會立即顯示在 Teams。</span><span class="sxs-lookup"><span data-stu-id="95341-122">This new date may not be immediately visible in Teams.</span></span> <span data-ttu-id="95341-123">同步最多可能需要 24 小時。如果您看到團隊及其基礎群組的到期日有差異，請等候 24 小時再尋求進一步支援。</span><span class="sxs-lookup"><span data-stu-id="95341-123">It can take up to 24 hours to sync. If you see a discrepancy between the expiry date for a team and its underlying group, wait 24 hours before seeking further support.</span></span>