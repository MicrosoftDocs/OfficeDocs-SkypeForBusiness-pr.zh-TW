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
ms.openlocfilehash: 22e254cb2db6dc63e01c9c8ef5628fb97cfa0e16
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637952"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的意見反應原則

[!INCLUDE [preview-feature](includes/preview-feature.md)]

貴組織中的使用者可以將團隊的意見反應傳送給 Microsoft，讓我們知道我們是如何直接從小組的桌面和 web 用戶端中進行。 我們會持續改善團隊體驗，並利用這種意見來改善團隊。

**[提供意見反應] 功能**

使用者可以移至**協助**  >  **提供小組意見**反應，以傳送有關團隊的意見反應與建議給我們。 透過 [**提供意見**反應] 傳送的資料在您的 Microsoft 365 或 Office 365 協定下會被視為「支援資料」，包括其他會被視為「客戶資料」或「個人資料」的資訊。

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

**勘察**

使用者也可以為團隊評分並傳送其所提供評級的詳細資料。 您可以在小組中的時間，向使用者顯示此彈出問卷。 當使用者按一下通知中的 [**提供意見**反應] 時，就會顯示該調查完成。

![小組中的「調查通知」和「表單」的螢幕擷取畫面](media/manage-feedback-policies-in-teams-survey.png)

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft

如果您是系統管理員，您可以控制貴組織中的使用者是否能透過**提供意見**反應，以及他們是否會收到問卷來傳送關於團隊的意見反應給 Microsoft。 根據預設，貴組織中的所有使用者都會自動獲指派全域（組織範圍預設值）原則，並在原則中啟用 [**提供意見**反應] 功能和問卷。 例外狀況是適用于教師的功能，以及學生已停用的功能。

您可以編輯全域原則，或建立並指派自訂原則。 如果指派給使用者的是自訂原則，該原則會套用給使用者。 如果使用者未獲指派自訂原則，則全域原則會套用至使用者。 在您編輯全域原則或指派原則後，可能需要幾個小時的時間，變更才會生效。

例如，您想要允許貴組織中的所有使用者傳送意見反應，在訓練中的新員工以外，**提供意見**反應並接收問卷。 在這種情況下，您會建立自訂原則來關閉兩個功能，並將它指派給新的招聘。 貴組織中的所有其他使用者都會在已開啟功能的情況下，取得全域原則。  

您*可以在[這裡找到](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)***新的 CsTeamsFeedbackPolicy** Cmdlet，以建立自訂原則與**授與 CsTeamsFeedbackPolicy** Cmdlet，以將它指派給一或多個使用者或使用者群組（例如安全群組或通訊群組）。

若要關閉並開啟這些功能，請設定下列參數：

 - **提供意見**反應：將**userInitiatedMode**參數設定為 [**啟用**]，以允許獲指派該原則的使用者提供意見反應。 將參數設定為 [**已停用**] 會關閉該功能，而且指派給該原則的使用者沒有提供意見反應的選項。
 - **問卷**：將**receiveSurveysMode**參數設定為 [**啟用**]，以允許獲指派該原則的使用者接收問卷。 若要讓使用者收到問卷並允許他們退出宣告，請將參數設定為 [ **enabledUserOverride**]。 在團隊中，使用者可以移至 [**設定**  >  **隱私權**]，並選擇是否要參與問卷。 將參數設定為 [**已停用**] 會關閉該功能，而且指派該原則的使用者將不會收到問卷。

## <a name="create-a-custom-feedback-policy"></a>建立自訂的意見反應原則

在這個範例中，我們會建立名為「新員工意見反應」原則的意見反應原則，然後關閉**提供意見反應和問卷**的功能。

```PowerShell
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled -receiveSurveysMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>指派自訂意見反應原則

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>將自訂意見反應原則指派給使用者

在這個範例中，我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。

```PowerShell
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>將自訂意見反應原則指派給群組中的使用者

您可能會想要將自訂意見反應原則指派給已識別的多位使用者。 例如，您可能會想要將原則指派給安全性群組中的所有使用者。

在這個範例中，我們會將名為「新增員工意見反應」原則的自訂意見反應原則指派給 Contoso 新員工群組中的所有使用者。  

取得特定群組的 GroupObjectId。
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
取得指定群組的成員。
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的意見反應原則。 在這個範例中，它是新的雇用意見反應原則。
```PowerShell
$members | ForEach-Object {Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.UserPrincipalName}
``` 
根據群組中的成員數目而定，此命令可能需要幾分鐘的時間執行。

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)
