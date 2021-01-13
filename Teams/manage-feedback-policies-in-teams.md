---
title: 管理 Microsoft 團隊中的意見反應原則
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: e2415204650ce47f875e432f062fd4a5e0438cd6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804693"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="15b36-103">管理 Microsoft 團隊中的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="15b36-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="15b36-104">貴組織中的使用者可以將團隊的意見反應傳送給 Microsoft，讓我們知道我們是如何直接從小組的桌面和 web 用戶端中進行。</span><span class="sxs-lookup"><span data-stu-id="15b36-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="15b36-105">我們會持續改善團隊體驗，並利用這種意見來改善團隊。</span><span class="sxs-lookup"><span data-stu-id="15b36-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="15b36-106">在 GCC、GCC 高或 DOD 部署中，意見反應原則無法使用。</span><span class="sxs-lookup"><span data-stu-id="15b36-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="15b36-107">**[提供意見反應] 功能**</span><span class="sxs-lookup"><span data-stu-id="15b36-107">**The Give feedback feature**</span></span>

<span data-ttu-id="15b36-108">使用者可以移至 **協助**  >  **提供小組意見** 反應，以傳送有關團隊的意見反應與建議給我們。</span><span class="sxs-lookup"><span data-stu-id="15b36-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="15b36-109">透過 [ **提供意見** 反應] 傳送的資料在您的 Microsoft 365 或 Office 365 協定下會被視為「支援資料」，包括其他會被視為「客戶資料」或「個人資料」的資訊。</span><span class="sxs-lookup"><span data-stu-id="15b36-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="15b36-111">**勘察**</span><span class="sxs-lookup"><span data-stu-id="15b36-111">**Surveys**</span></span>

<span data-ttu-id="15b36-112">使用者也可以為團隊評分並傳送其所提供評級的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="15b36-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="15b36-113">您可以在小組中的時間，向使用者顯示此彈出問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="15b36-114">當使用者按一下通知中的 [ **提供意見** 反應] 時，就會顯示該調查完成。</span><span class="sxs-lookup"><span data-stu-id="15b36-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![小組中的「調查通知」和「表單」的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="15b36-116">設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="15b36-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="15b36-117">如果您是系統管理員，您可以控制貴組織中的使用者是否能透過 **提供意見** 反應，以及他們是否會收到問卷來傳送關於團隊的意見反應給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="15b36-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="15b36-118">根據預設，貴組織中的所有使用者都會自動獲指派 [全域 (組織範圍的預設) 原則，並在原則中啟用 [ **提供意見** 反應] 功能和問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="15b36-119">例外狀況是適用于教師的功能，以及學生已停用的功能。</span><span class="sxs-lookup"><span data-stu-id="15b36-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="15b36-120">您可以編輯全域原則，或建立並指派自訂原則。</span><span class="sxs-lookup"><span data-stu-id="15b36-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="15b36-121">在您編輯全域原則或指派自訂原則後，可能需要幾個小時的時間，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="15b36-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="15b36-122">例如，您想要允許貴組織中的所有使用者傳送意見反應，在訓練中的新員工以外， **提供意見** 反應並接收問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="15b36-123">在這種情況下，您會建立自訂原則來關閉兩個功能，並將它指派給新的招聘。</span><span class="sxs-lookup"><span data-stu-id="15b36-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="15b36-124">貴組織中的所有其他使用者都會在已開啟功能的情況下，取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="15b36-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="15b36-125">您可以使用 PowerShell 來管理意見反應原則。</span><span class="sxs-lookup"><span data-stu-id="15b36-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="15b36-126">使用 *可在 [此找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* 的 **新-CsTeamsFeedbackPolicy** Cmdlet 來建立自訂原則，以及 **授與 CsTeamsFeedbackPolicy** Cmdlet，以將它指派給一或多個使用者或群組（例如安全群組或通訊群組）。</span><span class="sxs-lookup"><span data-stu-id="15b36-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="15b36-127">若要關閉並開啟這些功能，請設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="15b36-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="15b36-128">**提供意見** 反應：將 **userInitiatedMode** 參數設定為 [ **啟用** ]，以允許獲指派該原則的使用者提供意見反應。</span><span class="sxs-lookup"><span data-stu-id="15b36-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="15b36-129">將參數設定為 [ **已停用** ] 會關閉該功能，而且指派給該原則的使用者沒有提供意見反應的選項。</span><span class="sxs-lookup"><span data-stu-id="15b36-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="15b36-130">**問卷**：將 **receiveSurveysMode** 參數設定為 [ **啟用** ]，以允許獲指派該原則的使用者接收問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="15b36-131">若要讓使用者收到問卷並允許他們退出宣告，請將參數設定為 [ **enabledUserOverride**]。</span><span class="sxs-lookup"><span data-stu-id="15b36-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="15b36-132">在團隊中，使用者可以移至 [**設定**  >  **隱私權**]，並選擇是否要參與問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="15b36-133">將參數設定為 [ **已停用** ] 會關閉該功能，而且指派該原則的使用者將不會收到問卷。</span><span class="sxs-lookup"><span data-stu-id="15b36-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="15b36-134">建立自訂的意見反應原則</span><span class="sxs-lookup"><span data-stu-id="15b36-134">Create a custom feedback policy</span></span>

<span data-ttu-id="15b36-135">在這個範例中，我們會建立名為「新員工意見反應」原則的意見反應原則，然後關閉 **提供意見反應和問卷** 的功能。</span><span class="sxs-lookup"><span data-stu-id="15b36-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="15b36-136">將自訂意見反應原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="15b36-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="15b36-137">在這個範例中，我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。</span><span class="sxs-lookup"><span data-stu-id="15b36-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="15b36-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="15b36-138">Related topics</span></span>

- [<span data-ttu-id="15b36-139">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="15b36-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="15b36-140">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="15b36-140">Assign policies to your users in Teams</span></span>](assign-policies.md)