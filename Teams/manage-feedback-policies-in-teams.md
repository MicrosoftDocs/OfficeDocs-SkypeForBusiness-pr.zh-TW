---
title: 在 Microsoft Teams 中管理意見回饋政策
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
description: 瞭解如何使用意見回饋政策來控制貴組織的 Teams 使用者是否可以將 Teams 的意見回饋提交給 Microsoft。
ms.openlocfilehash: bc925320959c55b2fa06c8480f1011aab81aae9c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094263"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="8d91d-103">在 Microsoft Teams 中管理意見回饋政策</span><span class="sxs-lookup"><span data-stu-id="8d91d-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="8d91d-104">貴組織的使用者可以直接從 Teams 桌面和 Web 用戶端內傳送 Teams 的意見回饋給 Microsoft，讓我們知道我們的執行方式。</span><span class="sxs-lookup"><span data-stu-id="8d91d-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="8d91d-105">我們會持續改善 Teams 體驗，並使用此意見回饋讓 Teams 變得更好。</span><span class="sxs-lookup"><span data-stu-id="8d91d-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="8d91d-106">GCC、GCC High 或 DOD 部署中無法提供意見回饋政策。</span><span class="sxs-lookup"><span data-stu-id="8d91d-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="8d91d-107">**提供意見回饋功能**</span><span class="sxs-lookup"><span data-stu-id="8d91d-107">**The Give feedback feature**</span></span>

<span data-ttu-id="8d91d-108">使用者可以在 Teams 中協助提供意見，以傳送 Teams的意見和建議  >  給我們。</span><span class="sxs-lookup"><span data-stu-id="8d91d-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="8d91d-109">根據 Microsoft  365 或 Office 365 協定，透過 「意見回饋」所送出的資料視為「支援資料」，包括否則會被視為「客戶資料」或「個人資料」的資訊。</span><span class="sxs-lookup"><span data-stu-id="8d91d-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![Teams 中提供意見回饋選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="8d91d-111">**調查**</span><span class="sxs-lookup"><span data-stu-id="8d91d-111">**Surveys**</span></span>

<span data-ttu-id="8d91d-112">使用者也可以為 Teams 的體驗評分，並傳送他們給予評等的詳細資訊給我們。</span><span class="sxs-lookup"><span data-stu-id="8d91d-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="8d91d-113">此快顯視窗問卷會于 Teams 中時時向使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="8d91d-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="8d91d-114">當使用者按一下 **通知中提供** 意見回饋時，系統會顯示問卷供他們完成。</span><span class="sxs-lookup"><span data-stu-id="8d91d-114">When a user clicks **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![Teams 中問卷通知和表單的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="8d91d-116">設定使用者是否可以將 Teams 的意見回饋傳送至 Microsoft</span><span class="sxs-lookup"><span data-stu-id="8d91d-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="8d91d-117">做為系統管理員，您可以控制貴組織的使用者是否可以透過提供意見回饋，傳送 Teams 的意見回饋給 Microsoft，以及他們是否收到問卷。</span><span class="sxs-lookup"><span data-stu-id="8d91d-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="8d91d-118">根據預設，貴組織的所有使用者都會自動指派全域 (全組織的預設) 政策，且系統會在該政策中啟用提供意見回饋功能與問卷。</span><span class="sxs-lookup"><span data-stu-id="8d91d-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="8d91d-119">Teams 教育用除外，其中功能為教師啟用，而學生則停用。</span><span class="sxs-lookup"><span data-stu-id="8d91d-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="8d91d-120">您可以編輯全域原則，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="8d91d-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="8d91d-121">編輯全域原則或指派自訂策略之後，可能需要幾個小時，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="8d91d-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="8d91d-122">例如，假設您想要允許貴組織的所有使用者透過提供意見回饋傳送意見，並接收問卷，但接受訓練的新進人員除外。</span><span class="sxs-lookup"><span data-stu-id="8d91d-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="8d91d-123">在此情境中，您建立自訂政策以關閉這兩項功能，並將它指派給新員工。</span><span class="sxs-lookup"><span data-stu-id="8d91d-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="8d91d-124">貴組織的所有其他使用者會開啟功能，以取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="8d91d-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="8d91d-125">您可以使用 PowerShell 管理意見回饋政策。</span><span class="sxs-lookup"><span data-stu-id="8d91d-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="8d91d-126">使用 **New-CsTeamsFeedbackPolicy** Cmdlet *[](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* 來建立自訂策略和 **Grant-CsTeamsFeedbackPolicy** Cmdlet，將其指派給一或多個使用者或使用者群組，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="8d91d-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span>

<span data-ttu-id="8d91d-127">若要關閉並開啟功能，請設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="8d91d-127">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="8d91d-128">**提供意見回饋**：將 **UserInitiatedMode 參數** 設定為 **啟用** ，以允許指派策略的使用者提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="8d91d-128">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="8d91d-129">將 **參數設定為** 停用會關閉功能，而指派該策略的使用者沒有提供意見回饋的選項。</span><span class="sxs-lookup"><span data-stu-id="8d91d-129">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="8d91d-130">**問卷**：將 **receiveSurveysMode 參數** 設定為 **啟用** ，以允許獲派策略的使用者接收問卷。</span><span class="sxs-lookup"><span data-stu-id="8d91d-130">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="8d91d-131">若要讓使用者收到問卷並允許他們退出宣告，請設定參數以 **啟用UserOverride**。</span><span class="sxs-lookup"><span data-stu-id="8d91d-131">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="8d91d-132">在 Teams 中，使用者可以前往設定  >  **隱私權**，並選擇是否要參與問卷。</span><span class="sxs-lookup"><span data-stu-id="8d91d-132">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="8d91d-133">將參數設定為 **停用** 會關閉功能，而獲派該政策的使用者將不會收到問卷。</span><span class="sxs-lookup"><span data-stu-id="8d91d-133">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="8d91d-134">建立自訂的意見回饋政策</span><span class="sxs-lookup"><span data-stu-id="8d91d-134">Create a custom feedback policy</span></span>

<span data-ttu-id="8d91d-135">在此範例中，我們建立稱為新進員工意見回饋政策的意見回饋政策，並關閉透過提供意見和問卷 **提供** 意見回饋的能力。</span><span class="sxs-lookup"><span data-stu-id="8d91d-135">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="8d91d-136">指派自訂意見回饋政策給使用者</span><span class="sxs-lookup"><span data-stu-id="8d91d-136">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="8d91d-137">在此範例中，我們將名為新進員工的意見回饋政策指派給名為 user1 的自訂策略。</span><span class="sxs-lookup"><span data-stu-id="8d91d-137">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="8d91d-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="8d91d-138">Related topics</span></span>

- [<span data-ttu-id="8d91d-139">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="8d91d-139">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="8d91d-140">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="8d91d-140">Assign policies to your users in Teams</span></span>](assign-policies.md)