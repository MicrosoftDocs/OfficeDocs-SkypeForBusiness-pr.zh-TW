---
title: 在 Microsoft 團隊中管理私人小組探索
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何透過團隊專案庫和搜尋結果中的建議，控制 Microsoft 團隊使用者是否可探索私人團隊。
ms.openlocfilehash: e06a9511d8198a069c3dccfdbbbacf3d3f1b2c42
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46554693"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="9f237-103">在 Microsoft 團隊中管理私人小組探索</span><span class="sxs-lookup"><span data-stu-id="9f237-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f237-104">根據客戶的意見反應，我們停用了2020年8月31日的這項功能。</span><span class="sxs-lookup"><span data-stu-id="9f237-104">Based on customer feedback, we're disabling this feature, effective August 31, 2020.</span></span> <span data-ttu-id="9f237-105">這表示在2020年8月31日之後，您將無法再將私人團隊設定為可供使用，而且所有現有和新的私人團隊都將無法再探索。</span><span class="sxs-lookup"><span data-stu-id="9f237-105">This means that after August 31, 2020, you will no longer be able to set private teams to be discoverable and all existing and new private teams will no longer be discoverable.</span></span> <span data-ttu-id="9f237-106">若要深入瞭解，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370)。</span><span class="sxs-lookup"><span data-stu-id="9f237-106">To learn more, see the [Microsoft 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?featureid=44370).</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="9f237-107">系統管理員和小組擁有者可以控制貴組織中的 Microsoft 團隊使用者是否可探索私有團隊。</span><span class="sxs-lookup"><span data-stu-id="9f237-107">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="9f237-108">當私人團隊可被發現時，會顯示在搜尋結果中，並包含在小組中與團隊中的公用小組有關的建議中。</span><span class="sxs-lookup"><span data-stu-id="9f237-108">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="9f237-109">這可讓使用者輕鬆搜尋並找到他們想要加入的私人小組。</span><span class="sxs-lookup"><span data-stu-id="9f237-109">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="9f237-110">使用者可以要求加入私人小組，而團隊擁有者則可以核准或拒絕要求。</span><span class="sxs-lookup"><span data-stu-id="9f237-110">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="9f237-111">在小組中公開團隊、私人團隊和探索的概覽</span><span class="sxs-lookup"><span data-stu-id="9f237-111">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="9f237-112">大多陣列織都有下列幾種團隊：公用團隊、可探索的私人小組，以及無法探索的私人團隊。</span><span class="sxs-lookup"><span data-stu-id="9f237-112">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![小組圖庫的螢幕擷取畫面](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="9f237-114">公開團隊</span><span class="sxs-lookup"><span data-stu-id="9f237-114">Public teams</span></span>

<span data-ttu-id="9f237-115">公用團隊可供貴組織中的所有使用者加入。</span><span class="sxs-lookup"><span data-stu-id="9f237-115">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="9f237-116">[小組] 圖庫中的每個人都能看到公開的小組，而使用者可以加入公開團隊，而不需取得小組擁有者的核准。</span><span class="sxs-lookup"><span data-stu-id="9f237-116">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="9f237-117">公用團隊的範例包括一小組討論技術新聞、小組以取得您產品的意見反應，以及供人員 carpooling 工作的小組。</span><span class="sxs-lookup"><span data-stu-id="9f237-117">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="9f237-118">可探索的私人團隊</span><span class="sxs-lookup"><span data-stu-id="9f237-118">Discoverable private teams</span></span>

<span data-ttu-id="9f237-119">只有在小組擁有者新增使用者時，才能加入可探索的私人小組。</span><span class="sxs-lookup"><span data-stu-id="9f237-119">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="9f237-120">當您將私人小組探索時，小組會包含在團隊圖庫中的建議團隊和搜尋結果清單中。</span><span class="sxs-lookup"><span data-stu-id="9f237-120">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="9f237-121">針對貴組織中所有人都知道的專案和群組，以及對團隊中的交談和檔案存取權進行控制的位置，使用可探索的私人小組。</span><span class="sxs-lookup"><span data-stu-id="9f237-121">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="9f237-122">範例包括您的人力資源部門小組、貴組織中所有經理的小組，以及主管及其直接下屬的團隊。</span><span class="sxs-lookup"><span data-stu-id="9f237-122">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="9f237-123">無法探索的私人團隊</span><span class="sxs-lookup"><span data-stu-id="9f237-123">Non-discoverable private teams</span></span>

<span data-ttu-id="9f237-124">無法探索的私人小組只能在小組擁有者新增使用者時加入。</span><span class="sxs-lookup"><span data-stu-id="9f237-124">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="9f237-125">當您將私人小組取消探索時，系統會將它隱藏在建議的小組清單中，並從 [團隊] 圖庫中的搜尋結果中移除。</span><span class="sxs-lookup"><span data-stu-id="9f237-125">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="9f237-126">使用無法探索的小組，在機密與高度機密的主題上共同作業。</span><span class="sxs-lookup"><span data-stu-id="9f237-126">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="9f237-127">範例包括一個小組，討論即將到來的收購，以及小組討論貴組織的戰略方向的變更。</span><span class="sxs-lookup"><span data-stu-id="9f237-127">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="9f237-128">設定新的私人團隊是否可被發現</span><span class="sxs-lookup"><span data-stu-id="9f237-128">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="9f237-129">當團隊擁有者建立私人團隊時，他們可以透過設定小組的搜尋設定，選擇讓它可供搜尋。</span><span class="sxs-lookup"><span data-stu-id="9f237-129">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="9f237-130">根據預設，新的私人團隊是可搜尋且可探索的。</span><span class="sxs-lookup"><span data-stu-id="9f237-130">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="9f237-131">如果小組擁有者不想要讓私人小組顯示在搜尋結果和建議中，您可以選取 [**此小組**] 旁的 [**變更設定**] 來關閉設定。</span><span class="sxs-lookup"><span data-stu-id="9f237-131">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![新私人團隊探索設定的螢幕擷取畫面](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="9f237-133">設定現有的私人團隊是否可被發現</span><span class="sxs-lookup"><span data-stu-id="9f237-133">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="9f237-134">小組擁有者可以直接在團隊設定中設定現有私人小組的探索設定，而且管理員可以使用 PowerShell 來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="9f237-134">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="9f237-135">在團隊設定中</span><span class="sxs-lookup"><span data-stu-id="9f237-135">In team settings</span></span>

<span data-ttu-id="9f237-136">在 [團隊] 中，移至 [私人小組]，按一下 [**更多選項**  >  **管理團隊**]。</span><span class="sxs-lookup"><span data-stu-id="9f237-136">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="9f237-137">在 [**設定**] 索引標籤上，展開 [**小組探索**]，然後清除或選取 [**開啟**可搜尋專案] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9f237-137">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![現有私人團隊探索設定的螢幕擷取畫面](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="9f237-139">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="9f237-139">Using PowerShell</span></span>

<span data-ttu-id="9f237-140">使用 [**[設定團隊](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** Cmdlet] 來關閉或開啟現有私人小組的探索設定。</span><span class="sxs-lookup"><span data-stu-id="9f237-140">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="9f237-141">以下是如何讓團隊易於搜尋的範例：</span><span class="sxs-lookup"><span data-stu-id="9f237-141">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="9f237-142">您可以在腳本中使用這個 Cmdlet 來大量設定現有私人小組的探索設定。</span><span class="sxs-lookup"><span data-stu-id="9f237-142">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="9f237-143">設定使用者是否可探索私人團隊</span><span class="sxs-lookup"><span data-stu-id="9f237-143">Set whether users can discover private teams</span></span>

<span data-ttu-id="9f237-144">身為管理員，您也可以控制貴組織中的哪些使用者能夠在搜尋結果中發現私人小組，以及在小組中提供建議。</span><span class="sxs-lookup"><span data-stu-id="9f237-144">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="9f237-145">使用**[新的 CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** Cmdlet 建立原則，然後將原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="9f237-145">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="9f237-146">將**AllowPrivateTeamDiscovery**參數設定為**true** ，以允許獲指派該原則的使用者在搜尋結果和建議中查看可探索的私人小組。</span><span class="sxs-lookup"><span data-stu-id="9f237-146">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="9f237-147">將**AllowPrivateTeamDiscovery**參數設定為**false** ，就會從搜尋結果中移除所有可探索的私人小組，並針對獲指派該原則的使用者提出建議。</span><span class="sxs-lookup"><span data-stu-id="9f237-147">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="9f237-148">根據預設，對於組織中的所有使用者， **AllowPrivateTeamDiscovery**都設定為**true** 。</span><span class="sxs-lookup"><span data-stu-id="9f237-148">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="9f237-149">在這個範例中，我們會建立名為 VendorPolicy 的原則，防止使用者發現任何已可探索的私人團隊，然後我們會將原則指派給名為 vendoruser1 的使用者。</span><span class="sxs-lookup"><span data-stu-id="9f237-149">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="9f237-150">不能探索的私人小組永遠不會顯示在搜尋結果和建議中，無論原則設定為何。</span><span class="sxs-lookup"><span data-stu-id="9f237-150">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="9f237-151">例如，如果您關閉私人團隊的探索設定，使用者就無法探索團隊，即使在這些使用者的原則設定中， **AllowPrivateTeamDiscovery**參數已設定為**true** 。</span><span class="sxs-lookup"><span data-stu-id="9f237-151">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f237-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f237-152">Related topics</span></span>
- [<span data-ttu-id="9f237-153">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="9f237-153">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
