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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用意見反應原則來控制貴組織中的小組使用者是否可以將團隊的意見反應提交給 Microsoft。
ms.openlocfilehash: 70771f4a5e7c1376970ac3ac96cb9a4f822882a8
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837543"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="cc1ee-103">管理 Microsoft 團隊中的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="cc1ee-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="cc1ee-104">貴組織中的使用者可以將團隊的意見反應傳送給 Microsoft，讓我們知道我們是如何直接從小組的桌面和 web 用戶端中進行。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="cc1ee-105">我們會持續改善團隊體驗，並利用這種意見來改善團隊。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

<span data-ttu-id="cc1ee-106">**[提供意見反應] 功能**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-106">**The Give feedback feature**</span></span>

<span data-ttu-id="cc1ee-107">使用者可以移至**協助** > **提供小組意見**反應，以傳送有關團隊的意見反應與建議給我們。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-107">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="cc1ee-108">透過 [**提供意見**反應] 傳送的資料在您的 Office 365 協定下被視為「支援資料」，包括其他會視為「客戶資料」或「個人資料」的資訊。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-108">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="cc1ee-110">**勘察**</span><span class="sxs-lookup"><span data-stu-id="cc1ee-110">**Surveys**</span></span>

<span data-ttu-id="cc1ee-111">使用者也可以為團隊評分並傳送其所提供評級的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-111">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="cc1ee-112">您可以在小組中的時間，向使用者顯示此彈出問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-112">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="cc1ee-113">當使用者按一下通知中的 [**提供意見**反應] 時，就會顯示該調查完成。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-113">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![小組中的「調查通知」和「表單」的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="cc1ee-115">設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc1ee-115">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="cc1ee-116">如果您是系統管理員，您可以控制貴組織中的使用者是否能透過**提供意見**反應，以及他們是否會收到問卷來傳送關於團隊的意見反應給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-116">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="cc1ee-117">根據預設，貴組織中的所有使用者都會自動獲指派全域（組織範圍預設值）原則，並在原則中啟用 [**提供意見**反應] 功能和問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-117">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="cc1ee-118">例外狀況是適用于教師的功能，以及學生已停用的功能。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-118">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="cc1ee-119">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-119">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="cc1ee-120">如果指派給使用者的是自訂原則，該原則會套用給使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="cc1ee-121">如果使用者未獲指派自訂原則，則全域原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="cc1ee-122">在您編輯全域原則或指派原則之後，變更才會生效24小時。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-122">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="cc1ee-123">例如，您想要允許貴組織中的所有使用者傳送意見反應，在訓練中的新員工以外，**提供意見**反應並接收問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-123">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="cc1ee-124">在這種情況下，您會建立自訂原則來關閉兩個功能，並將它指派給新的招聘。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-124">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="cc1ee-125">貴組織中的所有其他使用者都會在已開啟功能的情況下，取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-125">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="cc1ee-126">您*可以在[這裡找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)\*\*\*新的 CsTeamsFeedbackPolicy*\* Cmdlet，以建立自訂原則與**授與 CsTeamsFeedbackPolicy** Cmdlet，以將它指派給一或多個使用者或使用者群組（例如安全群組或通訊群組）。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-126">You use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="cc1ee-127">若要關閉並開啟這些功能，請設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="cc1ee-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="cc1ee-128">**提供意見**反應：將**userInitiatedMode**參數設定為 [**啟用**]，以允許獲指派該原則的使用者提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="cc1ee-129">將參數設定為 [**已停用**] 會關閉該功能，而且指派給該原則的使用者沒有提供意見反應的選項。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="cc1ee-130">**問卷**：將**receiveSurveysMode**參數設定為 [**啟用**]，以允許獲指派該原則的使用者接收問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="cc1ee-131">若要讓使用者收到問卷並允許他們退出宣告，請將參數設定為 [ **enabledUserOverride**]。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="cc1ee-132">在團隊中，使用者可以移至 [**設定** > **隱私權**]，並選擇是否要參與問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="cc1ee-133">將參數設定為 [**已停用**] 會關閉該功能，而且指派該原則的使用者將不會收到問卷。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="cc1ee-134">建立自訂的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="cc1ee-134">Create a custom feedback policy</span></span>

<span data-ttu-id="cc1ee-135">在這個範例中，我們會建立名為「新員工意見反應」原則的意見反應原則，然後關閉**提供意見反應和問卷**的功能。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="cc1ee-136">指派自訂意見反應原則</span><span class="sxs-lookup"><span data-stu-id="cc1ee-136">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="cc1ee-137">將自訂意見反應原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="cc1ee-137">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="cc1ee-138">在這個範例中，我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-138">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="cc1ee-139">將自訂意見反應原則指派給群組中的使用者</span><span class="sxs-lookup"><span data-stu-id="cc1ee-139">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="cc1ee-140">您可能會想要將自訂意見反應原則指派給已識別的多位使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-140">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="cc1ee-141">例如，您可能會想要將原則指派給安全性群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-141">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="cc1ee-142">在這個範例中，我們會將名為「新增員工意見反應」原則的自訂意見反應原則指派給 Contoso 新員工群組中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-142">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="cc1ee-143">取得特定群組的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-143">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="cc1ee-144">取得指定群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-144">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="cc1ee-145">將群組中的所有使用者指派給特定的意見反應原則。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-145">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="cc1ee-146">在這個範例中，它是新的雇用意見反應原則。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-146">In this example, it's New Hire Feedback Policy.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="cc1ee-147">根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。</span><span class="sxs-lookup"><span data-stu-id="cc1ee-147">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc1ee-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc1ee-148">Related topics</span></span>

- [<span data-ttu-id="cc1ee-149">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="cc1ee-149">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
