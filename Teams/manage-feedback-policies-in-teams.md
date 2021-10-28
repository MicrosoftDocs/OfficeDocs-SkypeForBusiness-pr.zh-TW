---
title: 管理意見Microsoft Teams
author: serdarsoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何使用意見回饋政策來控制貴Teams的使用者是否可以將關於Teams的意見回饋提交給 Microsoft。
ms.openlocfilehash: 4cb8914a793ddb6342b047caada087006da8f670
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605769"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理意見Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

貴組織的使用者可以傳送有關Microsoft Teams的意見，讓我們知道我們直接從電腦、web 用戶端Teams行動版中執行的工作。 我們會持續改善Teams體驗，並使用此意見Teams改善。

> [!NOTE]
> 意見回饋政策不適用於GCC、GCC高或 DOD 部署。

**提供 **意見回饋** 功能**

使用者可以在桌面和 web 上Teams提供意見Teams留言  >  和建議給我們。


![在中提供意見Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

在行動版 **上存取意見** 設定  >  **協助&**  >  **傳送意見。**

![在行動Teams中提供意見Teams選項](media/feedback3.jpg)

 根據 **您的** Microsoft 365 或Office 365 協定，透過提供意見回饋和傳送意見回饋傳送的資料視為「支援資料」，包括否則會被視為「客戶資料」或「個人資料」的資訊。



**調查**

使用者也可以評等他們Teams，並傳送他們給予評等的詳細資訊給我們。 此快顯視窗問卷會以即時方式顯示在 Teams。 當使用者在 **通知中選取** 提供意見回饋時，系統會顯示問卷供他們完成。

![問卷通知和表單Teams。](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>設定使用者是否可以傳送有關Teams Microsoft 的意見

做為系統管理員，您可以控制貴組織的使用者是否可以傳送有關Teams的意見回饋給 Microsoft，以及他們是否收到問卷。 根據預設，貴組織中的所有使用者都會自動指派全域 (全組織的預設) 政策，且系統會在該政策中啟用意見回饋功能與問卷。 例外是Teams 教育版，其中功能為教師啟用，學生則停用。

您可以編輯全域原則，或建立及指派自訂策略。 編輯全域原則或指派自訂策略之後，可能需要數小時的時間，變更才能生效。

例如，假設您想要允許貴組織的所有使用者傳送意見，並接收問卷，但訓練中的新員工除外。 在此情境中，您建立自訂策略以關閉這兩項功能，並將它指派給新員工。 貴組織的所有其他使用者會開啟功能，以取得全域原則。  

您可以使用 PowerShell 管理意見回饋政策。 使用 [**New-CsTeamsFeedbackPolicy** Cmdlet](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell) 建立自訂策略。 使用 **Grant-CsTeamsFeedbackPolicy** Cmdlet 將其指派給一或多個使用者或使用者群組，例如安全性群組或通訊群組。 使用 **Set-CsTeamsFeedbackPolicy** 來設定特定標標。

若要關閉並開啟功能，請設定下列參數：

 - **提供意見回饋**：將 **UserInitiatedMode 參數** 設定為 **啟用** ，以允許指派該策略的使用者提供意見回饋。 將 **參數設定為** 停用會關閉功能，而指派該策略的使用者沒有提供意見回饋的選項。

 - **問卷**：將 **receiveSurveysMode 參數** 設定為 **啟用** ，以允許獲派策略的使用者接收問卷。 若要讓使用者收到問卷並讓他們退出宣告，請設定參數以 **啟用UserOverride**。 在 Teams中，使用者可以前往 設定  >  **隱私權**，並選擇是否要參與問卷。 將參數設定為 **停用** 會關閉功能，而獲派該政策的使用者將不會收到問卷。

 - **電子郵件**：使用 **AllowEmailCollection 標** 號來新增電子郵件欄位。
 - **記錄集合**：使用 **AllowLogCollection 標** 號為使用者新增記錄集合加入宣告。 記錄集合目前僅在行動版上啟用。 如需有關哪些資料透過記錄共用的詳細資訊， [請深入瞭解](https://go.microsoft.com/fwlink/?linkid=2168178)。

## <a name="create-a-custom-feedback-policy"></a>建立自訂的意見回饋政策

在此範例中，我們建立稱為新進員工意見回饋政策的意見回饋政策，並關閉透過提供意見和問卷 **提供** 意見意見的能力。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>指派自訂意見回饋政策給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

在此範例中，我們將名為新進員工的意見回饋政策指派給名為 user1 的使用者。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>相關主題

- [TeamsPowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](policy-assignment-overview.md)
