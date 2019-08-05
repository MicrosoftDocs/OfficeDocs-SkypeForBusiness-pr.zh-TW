---
title: 管理 Microsoft 團隊中的意見反應原則
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用意見反應原則來控制貴組織中的小組使用者是否可以將團隊的意見反應提交給 Microsoft。
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2019
ms.locfileid: "36184680"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="90956-103">管理 Microsoft 團隊中的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="90956-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="90956-104">使用者可以移至**協助** > **提供**小組客戶的意見反應, 以傳送關於團隊的意見及建議給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="90956-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="90956-105">我們會持續改善團隊體驗, 並利用這種意見來改善團隊。</span><span class="sxs-lookup"><span data-stu-id="90956-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="90956-107">透過 [**提供意見**反應] 傳送的資料在您的 Office 365 協定下被視為「支援資料」, 包括其他會視為「客戶資料」或「個人資料」的資訊。</span><span class="sxs-lookup"><span data-stu-id="90956-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="90956-108">設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="90956-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="90956-109">做為管理員, 您可以控制貴組織中的使用者是否可以將團隊的意見反應傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="90956-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="90956-110">根據預設, 貴組織中的所有使用者都會自動獲指派全域 (組織範圍預設值) 原則, 並在原則中啟用該功能。</span><span class="sxs-lookup"><span data-stu-id="90956-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="90956-111">例外狀況是適用于教師的功能, 以及學生已停用的功能。</span><span class="sxs-lookup"><span data-stu-id="90956-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="90956-112">您可以編輯全域原則, 或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="90956-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="90956-113">如果指派給使用者的是自訂原則, 該原則會套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="90956-114">如果使用者未獲指派自訂原則, 則全域原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="90956-115">在您編輯全域原則或指派原則之後, 變更才會生效24小時。</span><span class="sxs-lookup"><span data-stu-id="90956-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="90956-116">例如, 您想要允許貴組織中的所有使用者傳送意見反應, 除了訓練中的新員工外。</span><span class="sxs-lookup"><span data-stu-id="90956-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="90956-117">在這種情況下, 您會建立自訂原則來關閉此功能, 並將它指派給新的招聘。</span><span class="sxs-lookup"><span data-stu-id="90956-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="90956-118">貴組織中的所有其他使用者都會在已開啟此功能的情況下, 取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="90956-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="90956-119">您使用**CsTeamsFeedbackPolicy** Cmdlet 來建立自訂原則, 以及**授與 CsTeamsFeedbackPolicy** Cmdlet, 以將它指派給一或多個使用者或使用者群組, 例如安全群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="90956-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="90956-120">將**userInitiatedMode**參數設定為 [**啟用**], 以允許獲指派該原則的使用者提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="90956-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="90956-121">將參數設定為 [**已停用**] 會關閉該功能, 而且指派給該原則的使用者沒有提供意見反應的選項。</span><span class="sxs-lookup"><span data-stu-id="90956-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="90956-122">建立自訂的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="90956-122">Create a custom feedback policy</span></span>

<span data-ttu-id="90956-123">在這個範例中, 我們會建立名為「新員工意見反應」原則的意見反應原則, 並關閉提供意見反應的功能。</span><span class="sxs-lookup"><span data-stu-id="90956-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="90956-124">指派自訂意見反應原則</span><span class="sxs-lookup"><span data-stu-id="90956-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="90956-125">將自訂意見反應原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="90956-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="90956-126">在這個範例中, 我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="90956-127">將自訂意見反應原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="90956-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="90956-128">您可能會想要將自訂意見反應原則指派給已識別的多位使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="90956-129">例如, 您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="90956-130">在這個範例中, 我們會將名為「新增員工意見反應」原則的自訂意見反應原則指派給 Contoso 新員工群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="90956-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="90956-131">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="90956-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="90956-132">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="90956-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="90956-133">將群組中的所有使用者指派給特定的意見反應原則。</span><span class="sxs-lookup"><span data-stu-id="90956-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="90956-134">在這個範例中, 它是新的雇用意見反應原則。</span><span class="sxs-lookup"><span data-stu-id="90956-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="90956-135">根據群組中的成員數目而定, 此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="90956-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="90956-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="90956-136">Related topics</span></span>

- [<span data-ttu-id="90956-137">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="90956-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)