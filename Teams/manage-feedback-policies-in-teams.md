---
title: 管理意見Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: heprecel
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
description: 瞭解如何使用意見回饋政策來控制Teams中的使用者是否可以將相關意見Teams Microsoft。
ms.openlocfilehash: 66f14467e66456f244664a8273e0ff962297c05f
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656719"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="31297-103">管理意見Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="31297-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="31297-104">貴組織的使用者可以直接在桌面Teams用戶端內傳送有關Teams Microsoft 的意見。</span><span class="sxs-lookup"><span data-stu-id="31297-104">Users in your organization can send feedback about Teams to Microsoft let us know how we're doing, directly from within the Teams desktop and web clients.</span></span> <span data-ttu-id="31297-105">我們會持續改善Teams體驗，並使用此意見Teams改善。</span><span class="sxs-lookup"><span data-stu-id="31297-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

> [!NOTE]
> <span data-ttu-id="31297-106">意見回饋政策不適用於GCC、GCC高或 DOD 部署。</span><span class="sxs-lookup"><span data-stu-id="31297-106">Feedback policies aren't available in GCC, GCC High, or DOD deployments.</span></span>

<span data-ttu-id="31297-107">**提供意見回饋功能**</span><span class="sxs-lookup"><span data-stu-id="31297-107">**The Give feedback feature**</span></span>

<span data-ttu-id="31297-108">使用者可以在 Teams 中提供意見  >  \*\*\*\* Teams。</span><span class="sxs-lookup"><span data-stu-id="31297-108">Users can send comments and suggestions about Teams to us by going to **Help** > **Give feedback** in Teams.</span></span> <span data-ttu-id="31297-109">透過 「意見回饋」所送出的資料，根據您的Microsoft 365或Office 365視為「支援資料」，包括否則會視為「客戶資料」或「個人資料」的資訊。</span><span class="sxs-lookup"><span data-stu-id="31297-109">Data sent through **Give feedback** is considered as "Support Data" under your Microsoft 365 or Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

![其中提供意見回饋選項的螢幕擷取畫面Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="31297-111">**調查**</span><span class="sxs-lookup"><span data-stu-id="31297-111">**Surveys**</span></span>

<span data-ttu-id="31297-112">使用者也可以評等他們Teams，並傳送他們給予評等的詳細資訊給我們。</span><span class="sxs-lookup"><span data-stu-id="31297-112">Users can also rate their experience with Teams and send us details about the rating they give.</span></span> <span data-ttu-id="31297-113">此快顯視窗問卷會以即時方式顯示在 Teams。</span><span class="sxs-lookup"><span data-stu-id="31297-113">This pop-up survey is displayed to users from time-to-time in Teams.</span></span> <span data-ttu-id="31297-114">當使用者在 **通知中選取** 提供意見回饋時，系統會顯示問卷供他們完成。</span><span class="sxs-lookup"><span data-stu-id="31297-114">When a user selects **Provide feedback** in the notification, the survey is displayed for them to complete.</span></span>

![問卷通知和表單Teams](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="31297-116">設定使用者是否可以傳送關於Teams的意見回饋給 Microsoft</span><span class="sxs-lookup"><span data-stu-id="31297-116">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="31297-117">做為系統管理員，您可以控制貴組織的使用者是否可透過提供意見Teams意見，以及使用者是否收到問卷，將有關您資料的意見Teams傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="31297-117">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft through **Give feedback** and whether they receive the survey.</span></span> <span data-ttu-id="31297-118">根據預設，貴組織中的所有使用者都會自動指派全域 (全組織的預設) 政策，且系統會在該政策中啟用提供意見回饋功能與問卷。</span><span class="sxs-lookup"><span data-stu-id="31297-118">By default, all users in your organization are automatically assigned the global (Org-wide default) policy, and the **Give feedback** feature and survey are enabled in the policy.</span></span> <span data-ttu-id="31297-119">教育Teams例外，其中功能為教師啟用，學生則停用。</span><span class="sxs-lookup"><span data-stu-id="31297-119">The exception is Teams for Education, where the features are enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="31297-120">您可以編輯全域原則，或建立及指派自訂策略。</span><span class="sxs-lookup"><span data-stu-id="31297-120">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="31297-121">編輯全域原則或指派自訂策略之後，可能需要幾個小時，變更才能生效。</span><span class="sxs-lookup"><span data-stu-id="31297-121">After you edit the global policy or assign a custom policy, it can take a few hours for changes to take effect.</span></span>

<span data-ttu-id="31297-122">例如，假設您想要允許貴組織的所有使用者透過提供意見回饋傳送意見，並接收問卷，但接受訓練的新進人員除外。</span><span class="sxs-lookup"><span data-stu-id="31297-122">Say, for example, you want to allow all users in your organization to send feedback through **Give feedback** and receive surveys except for new hires in training.</span></span> <span data-ttu-id="31297-123">在此情境中，您建立自訂策略以關閉這兩項功能，並將它指派給新員工。</span><span class="sxs-lookup"><span data-stu-id="31297-123">In this scenario, you create a custom policy to turn off both features and assign it to new hires.</span></span> <span data-ttu-id="31297-124">貴組織的所有其他使用者會開啟功能，以取得全域原則。</span><span class="sxs-lookup"><span data-stu-id="31297-124">All other users in your organization get the global policy with the features turned on.</span></span>  

<span data-ttu-id="31297-125">您可以使用 PowerShell 管理意見回饋政策。</span><span class="sxs-lookup"><span data-stu-id="31297-125">You manage feedback policies by using PowerShell.</span></span> <span data-ttu-id="31297-126">使用 **New-CsTeamsFeedbackPolicy** Cmdlet *[](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*，您可以在這裡找到它，以建立自訂策略。</span><span class="sxs-lookup"><span data-stu-id="31297-126">Use the **New-CsTeamsFeedbackPolicy** cmdlet, *which can be [found here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)*, to create a custom policy.</span></span> <span data-ttu-id="31297-127">使用 **Grant-CsTeamsFeedbackPolicy** Cmdlet 將其指派給一或多個使用者或使用者群組，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="31297-127">Use the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> <span data-ttu-id="31297-128">使用 **Set-CsTeamsFeedbackPolicy** 來設定特定標標。</span><span class="sxs-lookup"><span data-stu-id="31297-128">Use **Set-CsTeamsFeedbackPolicy** to set specific flags.</span></span>

<span data-ttu-id="31297-129">若要關閉並開啟功能，請設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="31297-129">To turn off and turn on the features, set the following parameters:</span></span>

 - <span data-ttu-id="31297-130">**提供意見回饋**：將 **UserInitiatedMode 參數** 設定為 **啟用** ，以允許指派該策略的使用者提供意見回饋。</span><span class="sxs-lookup"><span data-stu-id="31297-130">**Give feedback**: Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="31297-131">將 **參數設定為** 停用會關閉功能，而指派該策略的使用者沒有提供意見回饋的選項。</span><span class="sxs-lookup"><span data-stu-id="31297-131">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>
 - <span data-ttu-id="31297-132">**問卷**：將 **receiveSurveysMode 參數** 設定為 **啟用** ，以允許獲派策略的使用者接收問卷。</span><span class="sxs-lookup"><span data-stu-id="31297-132">**Surveys**: Set the **receiveSurveysMode** parameter to **enabled** to allow users who are assigned the policy to receive the survey.</span></span> <span data-ttu-id="31297-133">若要讓使用者收到問卷並允許他們退出宣告，請設定參數以 **啟用UserOverride**。</span><span class="sxs-lookup"><span data-stu-id="31297-133">To have users receive the survey and allow them to opt out, set the parameter to **enabledUserOverride**.</span></span> <span data-ttu-id="31297-134">在 Teams中，使用者可以前往 設定  >  **隱私權**，並選擇是否要參與問卷。</span><span class="sxs-lookup"><span data-stu-id="31297-134">In Teams, users can then go to **Settings** > **Privacy** and choose whether they want to participate in surveys.</span></span> <span data-ttu-id="31297-135">將參數設定為 **停用** 會關閉功能，而獲派該政策的使用者將不會收到問卷。</span><span class="sxs-lookup"><span data-stu-id="31297-135">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy won't receive the survey.</span></span>
 - <span data-ttu-id="31297-136">**電子郵件**：使用 **AllowEmailCollection 標** 號來新增電子郵件欄位。</span><span class="sxs-lookup"><span data-stu-id="31297-136">**Email**: Use the **AllowEmailCollection** flag to add an email field.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="31297-137">建立自訂的意見回饋政策</span><span class="sxs-lookup"><span data-stu-id="31297-137">Create a custom feedback policy</span></span>

<span data-ttu-id="31297-138">在此範例中，我們建立稱為新進員工意見回饋政策的意見回饋政策，並關閉透過提供意見和問卷 **提供** 意見回饋的能力。</span><span class="sxs-lookup"><span data-stu-id="31297-138">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback through **Give feedback** and the survey.</span></span>

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a><span data-ttu-id="31297-139">指派自訂意見回饋政策給使用者</span><span class="sxs-lookup"><span data-stu-id="31297-139">Assign a custom feedback policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

<span data-ttu-id="31297-140">在此範例中，我們將名為新進員工的意見回饋政策指派給名為 user1 的自訂策略。</span><span class="sxs-lookup"><span data-stu-id="31297-140">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a><span data-ttu-id="31297-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="31297-141">Related topics</span></span>

- [<span data-ttu-id="31297-142">TeamsPowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="31297-142">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="31297-143">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="31297-143">Assign policies to your users in Teams</span></span>](assign-policies.md)
