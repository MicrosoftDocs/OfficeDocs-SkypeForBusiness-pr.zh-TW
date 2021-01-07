---
title: 管理 Microsoft 團隊中的團隊原則
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何使用及管理組織中的小組原則，以控制使用者可在團隊和頻道中執行的動作。
ms.openlocfilehash: 0b4664c36f24a057a7c8237823b7eafaad8ea6ba
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772025"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="67a8c-103">管理 Microsoft 團隊中的團隊原則</span><span class="sxs-lookup"><span data-stu-id="67a8c-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="67a8c-104">做為管理員，您可以使用 Microsoft 團隊中的小組原則來控制貴組織中的使用者可在團隊和頻道中進行的動作。</span><span class="sxs-lookup"><span data-stu-id="67a8c-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="67a8c-105">例如，您可以設定是否允許使用者建立私人頻道。</span><span class="sxs-lookup"><span data-stu-id="67a8c-105">For example, you can set whether users are allowed to create private channels.</span></span>

<span data-ttu-id="67a8c-106">您可以移至  >  Microsoft 團隊系統管理中心的小組 **小組原則**，管理小組原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="67a8c-107">您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="67a8c-108">除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="67a8c-109">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="67a8c-110">在您編輯全域原則或指派原則後，可能需要幾個小時的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="67a8c-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="67a8c-111">建立自訂團隊原則</span><span class="sxs-lookup"><span data-stu-id="67a8c-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="67a8c-112">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊**  >  **小組原則**]。</span><span class="sxs-lookup"><span data-stu-id="67a8c-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="67a8c-113">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="67a8c-113">Click **Add**.</span></span>
3. <span data-ttu-id="67a8c-114">輸入原則的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="67a8c-114">Enter a name and description for the policy.</span></span>

    ![團隊原則設定的螢幕擷取畫面](media/teams-policies.png)
4. <span data-ttu-id="67a8c-116">根據您是否要允許使用者建立私人頻道 <a name="createchannels"></a> ，開啟或關閉 [**建立私人頻道**]。</span><span class="sxs-lookup"><span data-stu-id="67a8c-116">Turn on or turn off **Create private channels**, <a name="createchannels"> </a> depending on whether you want to allow users to create private channels.</span></span>

5. <span data-ttu-id="67a8c-117">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="67a8c-117">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="67a8c-118">編輯團隊原則</span><span class="sxs-lookup"><span data-stu-id="67a8c-118">Edit a teams policy</span></span>

<span data-ttu-id="67a8c-119">您可以編輯全域原則或您建立的任何自訂原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-119">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="67a8c-120">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**團隊**  >  **小組原則**]。</span><span class="sxs-lookup"><span data-stu-id="67a8c-120">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="67a8c-121">按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。</span><span class="sxs-lookup"><span data-stu-id="67a8c-121">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="67a8c-122">開啟或關閉您想要的設定，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="67a8c-122">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="67a8c-123">將自訂團隊原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="67a8c-123">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="67a8c-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="67a8c-124">Related topics</span></span>

[<span data-ttu-id="67a8c-125">團隊中的私人頻道</span><span class="sxs-lookup"><span data-stu-id="67a8c-125">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="67a8c-126">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="67a8c-126">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="67a8c-127">新-CsTeamsChannelsPolicy</span><span class="sxs-lookup"><span data-stu-id="67a8c-127">New-CsTeamsChannelsPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
