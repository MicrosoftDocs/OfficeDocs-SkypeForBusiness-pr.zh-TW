---
title: Microsoft 團隊的敏感度標籤
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
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
description: 瞭解如何在 Microsoft 團隊中定義及使用敏感度標籤。
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653569"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="58582-103">Microsoft 團隊的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="58582-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="58582-104">[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)可讓團隊管理員控制在團隊中共同作業期間建立的機密組織內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="58582-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="58582-105">您可以在[安全性 & 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中定義敏感度標籤及其相關聯的原則。</span><span class="sxs-lookup"><span data-stu-id="58582-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="58582-106">這些標籤與原則會自動套用至貴組織中的小組。</span><span class="sxs-lookup"><span data-stu-id="58582-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="58582-107">敏感度標籤與團隊保密標籤之間的差異為何？</span><span class="sxs-lookup"><span data-stu-id="58582-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="58582-108">敏感度標籤與分類標籤不同，需要您使用 PowerShell 來建立它們。</span><span class="sxs-lookup"><span data-stu-id="58582-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="58582-109">分類標籤是可與群組相關聯但不含任何相關聯之實際原則的文字字串。</span><span class="sxs-lookup"><span data-stu-id="58582-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="58582-110">您可以使用分類標籤做為中繼資料，透過內部工具和腳本手動強制執行原則。</span><span class="sxs-lookup"><span data-stu-id="58582-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="58582-111">另一方面，敏感度標籤及其原則會自動強制執行，以結合群組平臺、安全性 & 合規性中心及團隊服務的組合來進行。</span><span class="sxs-lookup"><span data-stu-id="58582-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="58582-112">敏感度標籤可提供強大的基礎結構支援，以保護貴組織的機密資料。</span><span class="sxs-lookup"><span data-stu-id="58582-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="58582-113">建立及發佈小組的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="58582-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="58582-114">如需如何啟用、建立及發佈小組的敏感度標籤，請參閱[在 Microsoft 團隊、Office 365 群組和 SharePoint 網站上使用敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="58582-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="58582-115">在團隊中使用敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="58582-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="58582-116">以下是一些範例，說明如何將敏感度標籤與組織中的小組搭配使用。</span><span class="sxs-lookup"><span data-stu-id="58582-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="58582-117">團隊的隱私權設定</span><span class="sxs-lookup"><span data-stu-id="58582-117">Privacy setting of teams</span></span>

<span data-ttu-id="58582-118">您可以建立可在小組建立期間套用的敏感度標籤，讓使用者可以建立具備特定隱私權（公開或私人）設定的小組。</span><span class="sxs-lookup"><span data-stu-id="58582-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="58582-119">例如，您會在安全性 & 合規性中心建立名為 "機密" 的標籤，並設定團隊，讓使用此標籤建立的任何小組都必須是私人團隊。</span><span class="sxs-lookup"><span data-stu-id="58582-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="58582-120">當使用者建立新的小組並選取 [**機密**] 標籤時，使用者可以使用的唯一隱私權選項是 [**私人**]。</span><span class="sxs-lookup"><span data-stu-id="58582-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="58582-121">使用者已停用其他隱私權選項，例如公用與組織範圍。</span><span class="sxs-lookup"><span data-stu-id="58582-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![[機密敏感度] 標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="58582-123">同樣地，如果使用者在建立新團隊時選取 **[一般**]，他們就只能建立公用或組織範圍的團隊。</span><span class="sxs-lookup"><span data-stu-id="58582-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

<span data-ttu-id="58582-125">建立小組後，[敏感度] 標籤會顯示在小組中頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="58582-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

<span data-ttu-id="58582-127">小組擁有者可以隨時變更團隊的敏感度標籤和隱私權設定，只要前往小組，然後按一下 [**編輯團隊**] 即可。</span><span class="sxs-lookup"><span data-stu-id="58582-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="58582-129">對團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="58582-129">Guest access to teams</span></span>

<span data-ttu-id="58582-130">您可以指定使用特定標籤建立的小組是否允許來賓存取。</span><span class="sxs-lookup"><span data-stu-id="58582-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="58582-131">只有貴組織中的使用者可以使用不允許來賓存取權的標籤建立的團隊。</span><span class="sxs-lookup"><span data-stu-id="58582-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="58582-132">您組織外部的人員無法新增至小組。</span><span class="sxs-lookup"><span data-stu-id="58582-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="58582-133">已知問題</span><span class="sxs-lookup"><span data-stu-id="58582-133">Known issues</span></span>

<span data-ttu-id="58582-134">**Microsoft 團隊系統管理中心的敏感度標籤支援**</span><span class="sxs-lookup"><span data-stu-id="58582-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="58582-135">目前，Microsoft [團隊管理中心] 不支援敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="58582-136">如果您使用的是敏感度標籤，當您建立或編輯小組時，將無法設定敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="58582-137">敏感度標籤在小組屬性中也看不到，而且在 Microsoft 團隊系統管理中心的**分類**欄中不會顯示。</span><span class="sxs-lookup"><span data-stu-id="58582-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="58582-138">**支援小組圖形 Api、Powershell Cmdlet 及範本中的敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="58582-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="58582-139">目前，使用者將無法在直接透過圖形 Api、Powershell Cmdlet 及範本建立的小組上套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="58582-140">**在私人頻道的 SharePoint 網站集合上直接編輯敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="58582-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="58582-141">在團隊中建立的專用頻道會繼承已套用在小組中的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="58582-142">此外，在 [私人頻道] 的 SharePoint 網站集合上會自動套用相同的標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="58582-143">如果使用者直接更新私人頻道之 SharePoint 網站集合上的敏感度標籤，就不會在團隊用戶端中更新該標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="58582-144">在這種情況下，使用者會繼續在私人通道標題中查看在團隊上套用的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="58582-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="58582-145">**套用至團隊 app 外敏感度標籤變更的傳播時間**</span><span class="sxs-lookup"><span data-stu-id="58582-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="58582-146">在團隊 app 外對敏感度標籤所做的變更，可能需要長達24小時才能反映在團隊 app 中。</span><span class="sxs-lookup"><span data-stu-id="58582-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="58582-147">這適用于針對您啟用或停用租使用者的標籤所做的任何變更、標籤名稱、設定及原則的變更。</span><span class="sxs-lookup"><span data-stu-id="58582-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="58582-148">此外，直接針對支援小組的群組或 SharePoint 網站集合所做的任何變更，都可能需要長達24小時才能傳播至團隊 app。</span><span class="sxs-lookup"><span data-stu-id="58582-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>