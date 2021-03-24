---
title: 在 Microsoft Teams 中管理團隊政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: 瞭解如何在組織中使用及管理團隊策略，以控制使用者在團隊和頻道中可以執行的工作。
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094203"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="d0bef-103">在 Microsoft Teams 中管理團隊政策</span><span class="sxs-lookup"><span data-stu-id="d0bef-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="d0bef-104">做為系統管理員，您可以使用 Microsoft Teams 中的團隊策略來控制貴組織中使用者可以在團隊和頻道中執行哪些工作。</span><span class="sxs-lookup"><span data-stu-id="d0bef-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="d0bef-105">例如，您可以設定是否允許使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="d0bef-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="d0bef-106">您可以到 Microsoft Teams 系統管理中心中的 **Teams**  >  **Teams** 政策來管理團隊政策。</span><span class="sxs-lookup"><span data-stu-id="d0bef-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d0bef-107">您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="d0bef-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="d0bef-108">除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="d0bef-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="d0bef-109">您可以編輯全域原則，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="d0bef-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="d0bef-110">編輯全域原則或指派策略後，可能需要數小時的時間，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="d0bef-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="d0bef-111">建立自訂團隊策略</span><span class="sxs-lookup"><span data-stu-id="d0bef-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="d0bef-112">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams**  >  **Teams 政策**。</span><span class="sxs-lookup"><span data-stu-id="d0bef-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="d0bef-113">按一下 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="d0bef-113">Click **Add**.</span></span>
3. <span data-ttu-id="d0bef-114">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="d0bef-114">Enter a name and description for the policy.</span></span>

    ![團隊策略設定螢幕擷取畫面](media/teams-policies.png)
4. <span data-ttu-id="d0bef-116">視您是否 **要允許使用者**<a name="createchannels"></a>建立私人頻道，開啟或關閉建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="d0bef-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="d0bef-117">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="d0bef-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="d0bef-118">編輯團隊策略</span><span class="sxs-lookup"><span data-stu-id="d0bef-118">Edit a teams policy</span></span>

<span data-ttu-id="d0bef-119">您可以編輯全域原則或任何您建立的任何自訂策略。</span><span class="sxs-lookup"><span data-stu-id="d0bef-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="d0bef-120">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **Teams**  >  **Teams 政策**。</span><span class="sxs-lookup"><span data-stu-id="d0bef-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="d0bef-121">按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。</span><span class="sxs-lookup"><span data-stu-id="d0bef-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d0bef-122">開啟或關閉您想要的設定，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="d0bef-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="d0bef-123">指派自訂團隊策略給使用者</span><span class="sxs-lookup"><span data-stu-id="d0bef-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="d0bef-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0bef-124">Related topics</span></span>

[<span data-ttu-id="d0bef-125">Teams 中的私人頻道</span><span class="sxs-lookup"><span data-stu-id="d0bef-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="d0bef-126">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="d0bef-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="d0bef-127">New-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="d0bef-127">New-CsTeamsChannelsPolicy</span></span>](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)