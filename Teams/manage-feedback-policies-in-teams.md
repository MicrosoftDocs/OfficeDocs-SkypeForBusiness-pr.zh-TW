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
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的意見反應原則

[!INCLUDE [preview-feature](includes/preview-feature.md)]

貴組織中的使用者可以將團隊的意見反應傳送給 Microsoft，讓我們知道我們是如何直接從小組的桌面和 web 用戶端中進行。 我們會持續改善團隊體驗，並利用這種意見來改善團隊。

> [!NOTE]
> 在 GCC、GCC 高或 DOD 部署中，意見反應原則無法使用。

**[提供意見反應] 功能**

使用者可以移至 **協助**  >  **提供小組意見** 反應，以傳送有關團隊的意見反應與建議給我們。 透過 [ **提供意見** 反應] 傳送的資料在您的 Microsoft 365 或 Office 365 協定下會被視為「支援資料」，包括其他會被視為「客戶資料」或「個人資料」的資訊。

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

**勘察**

使用者也可以為團隊評分並傳送其所提供評級的詳細資料。 您可以在小組中的時間，向使用者顯示此彈出問卷。 當使用者按一下通知中的 [ **提供意見** 反應] 時，就會顯示該調查完成。

![小組中的「調查通知」和「表單」的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft

如果您是系統管理員，您可以控制貴組織中的使用者是否能透過 **提供意見** 反應，以及他們是否會收到問卷來傳送關於團隊的意見反應給 Microsoft。 根據預設，貴組織中的所有使用者都會自動獲指派 [全域 (組織範圍的預設) 原則，並在原則中啟用 [ **提供意見** 反應] 功能和問卷。 例外狀況是適用于教師的功能，以及學生已停用的功能。

您可以編輯全域原則，或建立並指派自訂原則。 在您編輯全域原則或指派自訂原則後，可能需要幾個小時的時間，變更才會生效。

例如，您想要允許貴組織中的所有使用者傳送意見反應，在訓練中的新員工以外， **提供意見** 反應並接收問卷。 在這種情況下，您會建立自訂原則來關閉兩個功能，並將它指派給新的招聘。 貴組織中的所有其他使用者都會在已開啟功能的情況下，取得全域原則。  

您可以使用 PowerShell 來管理意見反應原則。 使用 *可在 [此找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)* 的 **新-CsTeamsFeedbackPolicy** Cmdlet 來建立自訂原則，以及 **授與 CsTeamsFeedbackPolicy** Cmdlet，以將它指派給一或多個使用者或群組（例如安全群組或通訊群組）。

若要關閉並開啟這些功能，請設定下列參數：

 - **提供意見** 反應：將 **userInitiatedMode** 參數設定為 [ **啟用** ]，以允許獲指派該原則的使用者提供意見反應。 將參數設定為 [ **已停用** ] 會關閉該功能，而且指派給該原則的使用者沒有提供意見反應的選項。
 - **問卷**：將 **receiveSurveysMode** 參數設定為 [ **啟用** ]，以允許獲指派該原則的使用者接收問卷。 若要讓使用者收到問卷並允許他們退出宣告，請將參數設定為 [ **enabledUserOverride**]。 在團隊中，使用者可以移至 [**設定**  >  **隱私權**]，並選擇是否要參與問卷。 將參數設定為 [ **已停用** ] 會關閉該功能，而且指派該原則的使用者將不會收到問卷。

## <a name="create-a-custom-feedback-policy"></a>建立自訂的意見反應原則

在這個範例中，我們會建立名為「新員工意見反應」原則的意見反應原則，然後關閉 **提供意見反應和問卷** 的功能。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy-to-users"></a>將自訂意見反應原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

在這個範例中，我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)
- [指派策略給小組中的使用者](assign-policies.md)