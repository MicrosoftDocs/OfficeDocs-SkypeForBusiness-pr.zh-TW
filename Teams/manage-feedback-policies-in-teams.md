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
# <a name="manage-feedback-policies-in-microsoft-teams"></a>在 Microsoft Teams 中管理意見回饋政策

[!INCLUDE [preview-feature](includes/preview-feature.md)]

貴組織的使用者可以直接從 Teams 桌面和 Web 用戶端內傳送 Teams 的意見回饋給 Microsoft，讓我們知道我們的執行方式。 我們會持續改善 Teams 體驗，並使用此意見回饋讓 Teams 變得更好。

> [!NOTE]
> GCC、GCC High 或 DOD 部署中無法提供意見回饋政策。

**提供意見回饋功能**

使用者可以在 Teams 中協助提供意見，以傳送 Teams的意見和建議  >  給我們。 根據 Microsoft  365 或 Office 365 協定，透過 「意見回饋」所送出的資料視為「支援資料」，包括否則會被視為「客戶資料」或「個人資料」的資訊。

![Teams 中提供意見回饋選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

**調查**

使用者也可以為 Teams 的體驗評分，並傳送他們給予評等的詳細資訊給我們。 此快顯視窗問卷會于 Teams 中時時向使用者顯示。 當使用者按一下 **通知中提供** 意見回饋時，系統會顯示問卷供他們完成。

![Teams 中問卷通知和表單的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>設定使用者是否可以將 Teams 的意見回饋傳送至 Microsoft

做為系統管理員，您可以控制貴組織的使用者是否可以透過提供意見回饋，傳送 Teams 的意見回饋給 Microsoft，以及他們是否收到問卷。 根據預設，貴組織的所有使用者都會自動指派全域 (全組織的預設) 政策，且系統會在該政策中啟用提供意見回饋功能與問卷。 Teams 教育用除外，其中功能為教師啟用，而學生則停用。

您可以編輯全域原則，或建立及指派自訂策略。 編輯全域原則或指派自訂策略之後，可能需要幾個小時，變更才能生效。

例如，假設您想要允許貴組織的所有使用者透過提供意見回饋傳送意見，並接收問卷，但接受訓練的新進人員除外。 在此情境中，您建立自訂政策以關閉這兩項功能，並將它指派給新員工。 貴組織的所有其他使用者會開啟功能，以取得全域原則。  

您可以使用 PowerShell 管理意見回饋政策。 使用 **New-CsTeamsFeedbackPolicy** Cmdlet *[](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* 來建立自訂策略和 **Grant-CsTeamsFeedbackPolicy** Cmdlet，將其指派給一或多個使用者或使用者群組，例如安全性群組或通訊群組。

若要關閉並開啟功能，請設定下列參數：

 - **提供意見回饋**：將 **UserInitiatedMode 參數** 設定為 **啟用** ，以允許指派策略的使用者提供意見回饋。 將 **參數設定為** 停用會關閉功能，而指派該策略的使用者沒有提供意見回饋的選項。
 - **問卷**：將 **receiveSurveysMode 參數** 設定為 **啟用** ，以允許獲派策略的使用者接收問卷。 若要讓使用者收到問卷並允許他們退出宣告，請設定參數以 **啟用UserOverride**。 在 Teams 中，使用者可以前往設定  >  **隱私權**，並選擇是否要參與問卷。 將參數設定為 **停用** 會關閉功能，而獲派該政策的使用者將不會收到問卷。

## <a name="create-a-custom-feedback-policy"></a>建立自訂的意見回饋政策

在此範例中，我們建立稱為新進員工意見回饋政策的意見回饋政策，並關閉透過提供意見和問卷 **提供** 意見回饋的能力。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>指派自訂意見回饋政策給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

在此範例中，我們將名為新進員工的意見回饋政策指派給名為 user1 的自訂策略。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](assign-policies.md)