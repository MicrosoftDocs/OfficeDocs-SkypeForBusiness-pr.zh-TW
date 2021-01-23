---
title: Microsoft 團隊的敏感度標籤
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
description: 瞭解如何使用敏感度標籤來保護您的小組在 Microsoft 團隊中。
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937525"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="2f175-103">Microsoft 團隊的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2f175-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="2f175-104">[敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 可讓團隊管理員保護並控制在團隊中共同作業期間建立的機密組織內容的存取權。</span><span class="sxs-lookup"><span data-stu-id="2f175-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="2f175-105">在 [Microsoft 合規性中心](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)中使用相關聯的原則設定敏感度標籤之後，這些標籤就可以套用到貴組織中的小組。</span><span class="sxs-lookup"><span data-stu-id="2f175-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="2f175-106">目前不支援使用團隊教育版 Sku 的客戶使用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="2f175-107">若要深入瞭解授權，請參閱 [Microsoft 團隊服務說明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="2f175-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="2f175-108">敏感度標籤與團隊保密標籤之間的差異為何？</span><span class="sxs-lookup"><span data-stu-id="2f175-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="2f175-109">敏感度標籤與分類標籤（亦稱為 Azure AD 群組分類）不同。</span><span class="sxs-lookup"><span data-stu-id="2f175-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="2f175-110">分類標籤是可與 Microsoft 365 群組相關聯但沒有任何相關聯之實際原則的文字字串。</span><span class="sxs-lookup"><span data-stu-id="2f175-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="2f175-111">您使用分類標籤做為中繼資料，然後必須使用其他方法（例如內部工具和腳本）來強制執行原則。</span><span class="sxs-lookup"><span data-stu-id="2f175-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="2f175-112">使用敏感度標籤的優點是，其原則會透過 Microsoft 365 群組平臺、合規性中心及團隊服務的組合，自動強制執行。</span><span class="sxs-lookup"><span data-stu-id="2f175-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="2f175-113">敏感度標籤可提供強大的基礎結構支援，以保護貴組織的機密資料，並確保遵守您的內部原則或管理法規。</span><span class="sxs-lookup"><span data-stu-id="2f175-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="2f175-114">如果您目前使用的是分類標籤，請參閱下列檔，以取得詳細資訊，以及如何將其遷移至敏感度標籤的相關指示： [傳統 AZURE AD 群組分類](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)。</span><span class="sxs-lookup"><span data-stu-id="2f175-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="2f175-115">敏感度標籤範例案例</span><span class="sxs-lookup"><span data-stu-id="2f175-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="2f175-116">您可以如何將敏感度標籤與組織中的小組搭配使用的範例案例：</span><span class="sxs-lookup"><span data-stu-id="2f175-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="2f175-117">針對團隊 (公開或私人) 設定隱私權層級</span><span class="sxs-lookup"><span data-stu-id="2f175-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="2f175-118">控制對團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="2f175-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="2f175-119">設定團隊的隱私權等級</span><span class="sxs-lookup"><span data-stu-id="2f175-119">Set the privacy level for teams</span></span>

<span data-ttu-id="2f175-120">您可以建立及設定在小組建立期間套用的敏感度標籤，讓使用者能夠在公開或私人) 設定中，建立具有特定隱私權 (小組。</span><span class="sxs-lookup"><span data-stu-id="2f175-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="2f175-121">例如，您可以建立併發布一個名為「機密」的敏感度標籤，並將 [標籤隱私權] 選項設定為 [ **私人**]。</span><span class="sxs-lookup"><span data-stu-id="2f175-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="2f175-122">因此，使用此標籤建立的任何團隊都必須是私人團隊。</span><span class="sxs-lookup"><span data-stu-id="2f175-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="2f175-123">當使用者建立新的小組並選取 [ **機密** ] 標籤時，使用者可以使用的唯一隱私權選項是 [ **私人**]。</span><span class="sxs-lookup"><span data-stu-id="2f175-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="2f175-124">使用者無法選取其他隱私權選項（例如公用與組織範圍）：</span><span class="sxs-lookup"><span data-stu-id="2f175-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![[機密敏感度] 標籤的螢幕擷取畫面](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="2f175-126">同樣地，您也可以建立併發布名為「一般」的敏感度標籤，並將 [標籤隱私權] 選項設定為 [ **公開**]。</span><span class="sxs-lookup"><span data-stu-id="2f175-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="2f175-127">當使用者建立新的小組時，他們在選取此標籤時，只會建立公用或組織範圍的團隊：</span><span class="sxs-lookup"><span data-stu-id="2f175-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![一般敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-general-example.png)

<span data-ttu-id="2f175-129">建立小組後，[敏感度] 標籤會顯示在小組中頻道的右上角。</span><span class="sxs-lookup"><span data-stu-id="2f175-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![小組頻道中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-channel.png)

<span data-ttu-id="2f175-131">小組擁有者可以隨時變更團隊的敏感度標籤和隱私權設定，只要前往小組，然後按一下 [ **編輯團隊**] 即可。</span><span class="sxs-lookup"><span data-stu-id="2f175-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![團隊屬性中敏感度標籤的螢幕擷取畫面](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="2f175-133">控制對團隊的來賓存取權</span><span class="sxs-lookup"><span data-stu-id="2f175-133">Control guest access to teams</span></span>

<span data-ttu-id="2f175-134">您可以使用敏感度標籤來控制來賓對您團隊的存取權。</span><span class="sxs-lookup"><span data-stu-id="2f175-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="2f175-135">只有貴組織中的使用者可以使用不允許來賓存取權的標籤建立的團隊。</span><span class="sxs-lookup"><span data-stu-id="2f175-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="2f175-136">您組織外部的人員無法新增至小組。</span><span class="sxs-lookup"><span data-stu-id="2f175-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="2f175-137">Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="2f175-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="2f175-138">當您在 Microsoft 團隊系統管理中心建立或編輯小組時，您可以套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="2f175-139">在團隊屬性以及 Microsoft 團隊系統管理中心 [**管理團隊**] 頁面上的 [**分類**] 欄中，也會顯示敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="2f175-140">有限</span><span class="sxs-lookup"><span data-stu-id="2f175-140">Limitations</span></span>

<span data-ttu-id="2f175-141">在您針對團隊使用敏感度標籤之前，請注意下列限制：</span><span class="sxs-lookup"><span data-stu-id="2f175-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="2f175-142">**Sublabels 不會顯示父標籤名稱**</span><span class="sxs-lookup"><span data-stu-id="2f175-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="2f175-143">團隊支援 sublabels，但不會顯示父標籤的名稱。</span><span class="sxs-lookup"><span data-stu-id="2f175-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="2f175-144">例如，[ **機密**] \\ **所有員工都會** 顯示為 [ **所有員工**]。</span><span class="sxs-lookup"><span data-stu-id="2f175-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="2f175-145">**團隊圖形 Api、PowerShell Cmdlet 及範本不支援敏感度標籤**</span><span class="sxs-lookup"><span data-stu-id="2f175-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="2f175-146">使用者將無法在直接透過團隊圖形 Api、團隊 PowerShell Cmdlet 和團隊範本建立的團隊上套用敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="2f175-147">**支援專用通道**</span><span class="sxs-lookup"><span data-stu-id="2f175-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="2f175-148">在團隊中建立的專用頻道會繼承已套用在小組中的敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="2f175-149">在 [私人頻道] 的 SharePoint 網站集合上，系統會自動套用相同的標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="2f175-150">不過，如果使用者在 SharePoint 網站上直接變更私人頻道的敏感度標籤，則該標籤變更不會反映在團隊用戶端中。</span><span class="sxs-lookup"><span data-stu-id="2f175-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="2f175-151">在這種情況下，使用者會繼續在私人通道標題中查看在團隊上套用的原始敏感度標籤。</span><span class="sxs-lookup"><span data-stu-id="2f175-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="2f175-152">如何建立及設定小組的敏感度標籤</span><span class="sxs-lookup"><span data-stu-id="2f175-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="2f175-153">使用 Microsoft 365 檔中的指示來建立及設定小組的敏感度標籤：</span><span class="sxs-lookup"><span data-stu-id="2f175-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="2f175-154">[使用敏感度標籤來保護 Microsoft 團隊、microsoft 365 群組和 SharePoint 網站中的內容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="2f175-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
