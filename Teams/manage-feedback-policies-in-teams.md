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
# <a name="manage-feedback-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的意見反應原則

[!INCLUDE [preview-feature](includes/preview-feature.md)]

使用者可以移至**協助** > **提供**小組客戶的意見反應, 以傳送關於團隊的意見及建議給 Microsoft。 我們會持續改善團隊體驗, 並利用這種意見來改善團隊。

![小組中的 [提供意見反應] 選項的螢幕擷取畫面](media/manage-feedback-policies-in-teams-give-feedback.png)

透過 [**提供意見**反應] 傳送的資料在您的 Office 365 協定下被視為「支援資料」, 包括其他會視為「客戶資料」或「個人資料」的資訊。

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a>設定使用者是否可以將關於團隊的意見反應傳送給 Microsoft

做為管理員, 您可以控制貴組織中的使用者是否可以將團隊的意見反應傳送給 Microsoft。 根據預設, 貴組織中的所有使用者都會自動獲指派全域 (組織範圍預設值) 原則, 並在原則中啟用該功能。 例外狀況是適用于教師的功能, 以及學生已停用的功能。

您可以編輯全域原則, 或建立並指派自訂原則。 如果指派給使用者的是自訂原則, 該原則會套用給使用者。 如果使用者未獲指派自訂原則, 則全域原則會套用至使用者。 在您編輯全域原則或指派原則之後, 變更才會生效24小時。

例如, 您想要允許貴組織中的所有使用者傳送意見反應, 除了訓練中的新員工外。 在這種情況下, 您會建立自訂原則來關閉此功能, 並將它指派給新的招聘。 貴組織中的所有其他使用者都會在已開啟此功能的情況下, 取得全域原則。  

您使用**CsTeamsFeedbackPolicy** Cmdlet 來建立自訂原則, 以及**授與 CsTeamsFeedbackPolicy** Cmdlet, 以將它指派給一或多個使用者或使用者群組, 例如安全群組或通訊群組。 

將**userInitiatedMode**參數設定為 [**啟用**], 以允許獲指派該原則的使用者提供意見反應。 將參數設定為 [**已停用**] 會關閉該功能, 而且指派給該原則的使用者沒有提供意見反應的選項。

## <a name="create-a-custom-feedback-policy"></a>建立自訂的意見反應原則

在這個範例中, 我們會建立名為「新員工意見反應」原則的意見反應原則, 並關閉提供意見反應的功能。

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a>指派自訂意見反應原則

### <a name="assign-a-custom-feedback-policy-to-a-user"></a>將自訂意見反應原則指派給使用者

在這個範例中, 我們會將名為「新增員工意見反應」原則的自訂原則指派給名為 user1 的使用者。

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a>將自訂意見反應原則指派給群組中的使用者

您可能會想要將自訂意見反應原則指派給已識別的多位使用者。 例如, 您可能會想要將原則指派給安全性群組中的所有使用者。

在這個範例中, 我們會將名為「新增員工意見反應」原則的自訂意見反應原則指派給 Contoso 新員工群組中的所有使用者。  

取得特定群組的 GroupObjectId。
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
取得指定群組的成員。
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
將群組中的所有使用者指派給特定的意見反應原則。 在這個範例中, 它是新的雇用意見反應原則。
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
根據群組中的成員數目而定, 此命令可能需要幾分鐘的時間執行。

## <a name="related-topics"></a>相關主題

- [團隊 PowerShell 概覽](teams-powershell-overview.md)