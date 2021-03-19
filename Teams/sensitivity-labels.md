---
title: Microsoft Teams 的敏感度標籤
ms.author: mikeplum
author: cabailey
manager: laurawi
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用敏感度標籤來保護 Microsoft Teams 中的團隊。
ms.openlocfilehash: 6929e9c51f35cb4483c81323048b2a1f9ec6243a
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875103"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="78bcd-103">Microsoft Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="78bcd-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="78bcd-104">[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 可允許 Teams 系統管理員保護並規範在團隊內共同合作期間所建立之機密組織內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="78bcd-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="78bcd-105">在 Microsoft 合規性中心中設定敏感度標籤及其關聯原則[](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)之後，這些標籤可以適用于貴組織的小組。</span><span class="sxs-lookup"><span data-stu-id="78bcd-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="78bcd-106">使用 Teams Education SKUs 的客戶目前不支援敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="78bcd-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="78bcd-107">若要深入瞭解授權，請參閱 Microsoft [Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="78bcd-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="78bcd-108">敏感度標籤和 Teams 分類標籤之間有什麼不同？</span><span class="sxs-lookup"><span data-stu-id="78bcd-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="78bcd-109">敏感度標籤與分類標籤不同，也稱為 Azure AD 群組分類。</span><span class="sxs-lookup"><span data-stu-id="78bcd-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="78bcd-110">分類標籤是可與 Microsoft 365 群組相關聯的文字字串，但沒有任何與其相關聯的實際政策。</span><span class="sxs-lookup"><span data-stu-id="78bcd-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="78bcd-111">您可以使用分類標籤做為中繼資料，然後必須使用其他方法 ，例如內部工具和腳本，以強制執行策略。</span><span class="sxs-lookup"><span data-stu-id="78bcd-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="78bcd-112">使用敏感度標籤的好處，是透過 Microsoft 365 群組平臺、合規性中心和 Teams 服務的組合，自動強制執行其政策。</span><span class="sxs-lookup"><span data-stu-id="78bcd-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="78bcd-113">敏感度標籤提供強大的基礎結構支援，可保護組織的機密資料，並確保符合您的內部政策或法規。</span><span class="sxs-lookup"><span data-stu-id="78bcd-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="78bcd-114">如果您目前使用分類標籤，請參閱下列檔以進一步瞭解如何將它們遷移到敏感度標籤： [傳統 Azure AD 群組分類](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。</span><span class="sxs-lookup"><span data-stu-id="78bcd-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="78bcd-115">敏感度標籤的範例案例</span><span class="sxs-lookup"><span data-stu-id="78bcd-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="78bcd-116">如何在貴組織中將敏感度標籤用於 Teams 的範例案例：</span><span class="sxs-lookup"><span data-stu-id="78bcd-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="78bcd-117">設定團隊的 (或私人) 層級</span><span class="sxs-lookup"><span data-stu-id="78bcd-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="78bcd-118">控制團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="78bcd-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="78bcd-119">設定團隊的隱私權等級</span><span class="sxs-lookup"><span data-stu-id="78bcd-119">Set the privacy level for teams</span></span>

<span data-ttu-id="78bcd-120">您可以建立和設定敏感度標籤，在建立小組時，允許使用者建立具有特定隱私權的小組， (公開或) 設定。</span><span class="sxs-lookup"><span data-stu-id="78bcd-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="78bcd-121">例如，您建立併發布名為「機密」的敏感度標籤，其標籤隱私權選項已配置為 **「私人」。**</span><span class="sxs-lookup"><span data-stu-id="78bcd-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="78bcd-122">因此，使用此標籤建立的任何團隊都必須是私人團隊。</span><span class="sxs-lookup"><span data-stu-id="78bcd-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="78bcd-123">當使用者建立新團隊並選取機密標籤時，使用者唯一可用的隱私權選項是 **私人**。</span><span class="sxs-lookup"><span data-stu-id="78bcd-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="78bcd-124">使用者無法選取其他隱私權選項 ，例如公用和全組織：</span><span class="sxs-lookup"><span data-stu-id="78bcd-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![機密敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="78bcd-126">同樣地，您建立併發布名為「一般」的敏感度標籤，其標籤隱私權選項已配置為 **公用**。</span><span class="sxs-lookup"><span data-stu-id="78bcd-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="78bcd-127">當使用者建立新團隊時，他們只有在選取此標籤時，才能建立公用或全組織團隊：</span><span class="sxs-lookup"><span data-stu-id="78bcd-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

<span data-ttu-id="78bcd-129">建立團隊時，敏感度標籤會顯示在團隊中頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="78bcd-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> <span data-ttu-id="78bcd-130">請注意，如果您使用的是階層式父子標籤 ，例如「機密\財務」，則只有父標籤會顯示在頻道標題中。</span><span class="sxs-lookup"><span data-stu-id="78bcd-130">Note that if you are using hierarchical parent child labels such as "Confidential\Finance" then only the parent label will be showin the channel header.</span></span>


![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

<span data-ttu-id="78bcd-132">團隊擁有者可以隨時變更小組的敏感度標籤和隱私權設定，方法為進入團隊，然後按一下 [ **編輯團隊**。</span><span class="sxs-lookup"><span data-stu-id="78bcd-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![小組屬性中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="78bcd-134">控制團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="78bcd-134">Control guest access to teams</span></span>

<span data-ttu-id="78bcd-135">您可以使用敏感度標籤來控制來賓對團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="78bcd-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="78bcd-136">使用不允許來賓存取的標籤所建立的團隊，只有貴組織的使用者才能使用。</span><span class="sxs-lookup"><span data-stu-id="78bcd-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="78bcd-137">組織外部人員無法新加入團隊。</span><span class="sxs-lookup"><span data-stu-id="78bcd-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="78bcd-138">Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="78bcd-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="78bcd-139">您可以在 Microsoft Teams 系統管理中心建立或編輯團隊時，使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="78bcd-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="78bcd-140">敏感度標籤也會顯示在小組屬性中，以及 Microsoft  Teams 系統管理中心的管理小組頁面的分類欄。</span><span class="sxs-lookup"><span data-stu-id="78bcd-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="78bcd-141">限制</span><span class="sxs-lookup"><span data-stu-id="78bcd-141">Limitations</span></span>

<span data-ttu-id="78bcd-142">使用 Teams 的敏感度標籤之前，請注意下列限制：</span><span class="sxs-lookup"><span data-stu-id="78bcd-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="78bcd-143">**子標記不會顯示父標籤名稱**</span><span class="sxs-lookup"><span data-stu-id="78bcd-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="78bcd-144">Teams 支援子標記，但不會顯示父標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="78bcd-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="78bcd-145">例如 **，機密** \\ **所有員工會顯示** 為 **所有員工**。</span><span class="sxs-lookup"><span data-stu-id="78bcd-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="78bcd-146">**Teams Graph API、PowerShell Cmdlet 和範本不支援敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="78bcd-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="78bcd-147">使用者將無法將敏感度標籤直接透過 Teams Graph API、Teams PowerShell Cmdlet 和 Teams 範本建立的團隊上。</span><span class="sxs-lookup"><span data-stu-id="78bcd-147">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="78bcd-148">**支援私人頻道**</span><span class="sxs-lookup"><span data-stu-id="78bcd-148">**Support for private channels**</span></span>
    
    <span data-ttu-id="78bcd-149">在團隊中建立的私人頻道會繼承已用於團隊的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="78bcd-149">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="78bcd-150">相同的標籤會自動用於私人頻道的 SharePoint 網站集合。</span><span class="sxs-lookup"><span data-stu-id="78bcd-150">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="78bcd-151">不過，如果使用者直接變更私人頻道 SharePoint 網站上敏感度標籤，該標籤變更不會反映在 Teams 用戶端中。</span><span class="sxs-lookup"><span data-stu-id="78bcd-151">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="78bcd-152">在此情境中，使用者會繼續在私人頻道標題中看到在小組上所應用的原始敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="78bcd-152">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="78bcd-153">如何建立及設定 Teams 的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="78bcd-153">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="78bcd-154">使用 Microsoft 365 檔的指示為 Teams 建立和設定敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="78bcd-154">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="78bcd-155">[使用敏感度標籤來保護 Microsoft Teams、Microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="78bcd-155">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
