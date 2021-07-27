---
title: 管理公司中前線員工以班為基礎的Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在組織中管理前線工作人員Teams班式存取權。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9c1d8ed8e964d1ffeda8e862992335560c9a6aab
ms.sourcegitcommit: 330b5c3e299ddad5168958e4722d1e0b987372e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/23/2021
ms.locfileid: "53536839"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>管理公司中前線員工以班為基礎的Teams

> [!IMPORTANT]
> 自 2020 年 6 月 30 起，已終止對 Microsoft StaffHub 的支援。 我們正在將 StaffHub 功能建在 Microsoft Teams。 今天，Teams 包含用於排程管理的班次應用程式，並且會陸續推出其他功能。 所有使用者自 2020 年 6 月 30 日起皆無法再使用 StaffHub。 任何嘗試開啟 StaffHub 的人，都會看到一則訊息，指示他們下載 Teams。 如需深入了解，請參閱[已終止對 Microsoft StaffHub 的支援](microsoft-staffhub-to-be-retired.md)。  

## <a name="overview"></a>概觀

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

目前Microsoft Teams表示使用者目前的可用性和狀態給其他使用者。 前線員工的存在通常不如其他員工預測，因為每天的工作時間通常不同。 做為系統管理員，您可以設定Teams，為貴組織的前線員工顯示一組以班為基礎的目前狀態，以指出他們何時上班和下班。

這些以班為基礎的目前狀態 實心綠色核取方塊，表示在班次上，灰色圓圈與 x，表示關閉班次關閉班次，實心紅色圓圈，表示忙碌狀態與 Teams 的預設目前狀態 &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; 集不同[](../../presence-admins.md)。 有了這兩組目前狀態，您可以根據組織人員的角色來設定不同的體驗。

使用以班為基礎的存取，您可以在前線員工Teams管理存取權。 例如，您可以設定Teams，以顯示前線員工必須先確認的訊息，才能Teams排班時才能使用。  

## <a name="scenario"></a>案例

以下是貴組織如何管理班次式存取的範例。

貴組織的前線員工只能在主管排程和核准的班上工作時數獲得報酬。 他們不應支付在排程班以外工作的時間，包括使用 Teams 應用程式。 您設定了一則自訂訊息，指出「您的 Teams 非班時間不會計入應付時數」，當前線工作人員嘗試在輪班時存取Teams會顯示該訊息。 如果他們選擇使用Teams，請按一下 [我接受，瞭解這次不會支付他們費用。

您組織中也有有薪資且沒有輪班的資訊工作者。 您將資訊工作者設定為在 Teams中使用預設目前狀態，同時提供前線員工以班為基礎的目前狀態。

## <a name="shift-based-presence-states"></a>以班次為基礎的目前狀態

以下是以班次為基礎的目前狀態。

|應用程式設定 |使用者設定  |詳細資訊  |
|---------|---------|---------|
|![實心綠色核取方塊，表示正在上班](../../media/flw-presence-on-shift.png) 輪班     |         |在班次開始時自動設定         |
|![使用 x 的灰色圓圈，表示關閉班次](../../media/flw-presence-off-shift.png) 關閉班次     |         |在班次結束時自動設定         |
|![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌      | ![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |自動設定。 您也可以手動設定前線工作人員輪班時。|

## <a name="off-shift-access-to-teams"></a>關閉班次存取Teams

此功能可讓您在前線員工Teams時管理存取權。 您可以設定Teams，讓前線員工在輪班時存取Teams訊息。 前線工作人員必須先按一下 **[我接受** 並認可郵件後，才能使用Teams。

您可以使用預設郵件、從一組預先定義的郵件中選擇，或自訂郵件以顯示您想要的任何文字。 以下是預設訊息：

![預設訊息的螢幕擷取畫面](../../media/shifts-presence-message.png)

您也可以設定顯示郵件的頻率，並設定寬限期，介於第一個班次開始或最後一個班次結束，以及限制存取Teams期間。

## <a name="manage-shift-based-access"></a>管理輪班式存取

做為系統管理員，您可以使用策略來控制組織中前線員工以班為基礎的目前狀態。 您可以使用下列 PowerShell Cmdlet 管理這些策略：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy Cmdlet 來建立新策略、設定您想要的策略設定，然後使用 Grant-CsTeamsShiftsPolicy Cmdlet 將策略指派給使用者。

以下是一些範例。 請參閱 [New-CsTeamsShiftsPolicy，](/powershell/module/teams/new-csteamsshiftspolicy)瞭解每個策略設定和參數的詳細資訊，包括您可選擇之預先定義的班次外訊息清單。

### <a name="example-1"></a>範例 1

在此範例中，我們建立名為 Off Shift 的新Teams Access 預設訊息。 在此政策中，以班為基礎的目前狀態會開啟，且每當指派此策略的使用者在輪班時存取Teams會顯示預設訊息。 如果使用者接受Teams，可以在輪班時使用通知，而第一個班次開始或最後一個班結束時，以及限制存取權之間的寬限期為 10 分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。 若要查看您可以為此參數選擇之預先定義的郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>範例 2 

在此範例中，我們建立名為 Off Shift 的新Teams Access 自訂訊息。 在此政策中，會開啟以班次為基礎的目前狀態，且每當指派此策略的使用者在輪班時存取Teams時，都會顯示自訂訊息。 如果使用者接受Teams，可以在輪班時使用此程式，而第一個班次開始或最後一個班次結束時，以及限制存取權之間的寬限期為 15 分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。 若要深入瞭解，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>範例 3

在此範例中，我們建立名為 Off Shift Teams Access Message1 的新策略。 在此政策中，會開啟以班為基礎的目前狀態，且每次指派此策略的使用者在輪班時存取Teams預先定義的訊息。

  「您的雇主不會授權或核准非免稅或小時制員工在其非工作時間使用其網路、應用程式、系統或工具。 接受時，即表示您Teams非授權且您不會獲得補償。 

如果使用者接受Teams，可以在輪班時使用，而第一個班次開始或最後一個班結束時，以及限制存取權之間的寬限期為三分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType 參數** 來設定您想要顯示的郵件。 若要查看您可以為此參數選擇之預先定義的郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>範例 4

在此範例中，我們會將名為 Off Shift Teams Access 自訂訊息的一個 remy@contoso.com。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相關主題

- [在 Teams 中管理貴組織的 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概觀](../../teams-powershell-overview.md)