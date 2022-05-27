---
title: 在 Teams 中管理第一線員工的輪班式存取權
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何管理貴組織中第一線員工Teams的班型存取權。
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675215"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>在 Teams 中管理第一線員工的輪班式存取權
## <a name="overview"></a>概觀

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Microsoft Teams中的目前狀態會向其他使用者指出使用者目前的顯示狀態和狀態。 第一線工作人員的顯示狀態通常比其他員工更無法預測，因為他們的工作時間通常不是每天一樣。 身為系統管理員，您可以設定Teams，為組織中的前線員工顯示一組以班次為基礎的目前狀態，以指出他們何時開班或脫班。

這些 Shift 型目前狀態為 &mdash; ![ 實心綠色核取記號，表示 [上班]。](../../media/flw-presence-on-shift.png) **在班次時**， ![ 有 x 的灰色圓圈表示 [班次關閉]。](../../media/flw-presence-off-shift.png) **[班次關閉**]、 ![ [固定紅色] 圓圈表示 [**忙碌中** &mdash; ](../../media/flw-presence-busy.png) ] 與Teams中的 [預設目前狀態組](../../presence-admins.md)是分開的。 使用這兩組目前狀態，您可以根據組織中的人員角色來設定不同的體驗。

透過輪班式存取，您可以管理第一線工作人員休假時Teams的存取權。 例如，您可以設定Teams顯示一則訊息，讓第一線工作人員必須先確認，才能在未安排班次時使用Teams。  

## <a name="scenario"></a>案例

以下是您的組織如何管理 Shift 型存取的範例。

貴組織的第一線員工應只支付其主管排定和核准的輪班時薪。 他們不應該支付在排程班外工作的時間，包括使用Teams應用程式。 您設定了一則自訂訊息，指出「您在Teams休假時的時間不會計入付費時間」，當第一線工作人員在脫班時嘗試存取Teams時會顯示此訊息。 如果他們選擇使用Teams，則按一下 [**我接受**]，並瞭解這次不會支付費用。

貴組織中也有獲得稱呼及不輪班的資訊工作者。 您設定資訊工作者在Teams中使用預設的目前狀態，同時讓第一線工作人員以班次為基礎的目前狀態。

## <a name="shift-based-presence-states"></a>Shift 型目前狀態

以下是 Shift 型目前狀態。

|應用程式設定 |使用者設定  |詳細資訊  |
|---------|---------|---------|
|![實心綠色核取記號，表示 [上班]。](../../media/flw-presence-on-shift.png) 輪班時     |         |在班開始時自動設定         |
|![有 x 的灰色圓圈，表示 [班次關閉]](../../media/flw-presence-off-shift.png) 關閉班次     |         |在班尾自動設定         |
|![紅色實心圓圈，表示忙碌。](../../media/flw-presence-busy.png) 忙碌      | ![紅色實心圓圈，表示忙碌](../../media/flw-presence-busy.png) 忙碌         |[自動設定]。 也可以在第一線員工輪班時手動設定。|

## <a name="off-shift-access-to-teams"></a>關閉移轉存取Teams

這項功能可讓您在前線工作人員休假時管理存取Teams。 您可以設定Teams，讓他們在脫班時存取Teams，向第一線工作人員顯示訊息。 第一線工作人員必須按一下 **[我接受**] 確認訊息，才能使用Teams。

您可以使用預設郵件、從一組預先定義的郵件中選擇，或自訂郵件以顯示任何您想要的文字。 以下是預設訊息：

![預設訊息的螢幕擷取畫面。](../../media/shifts-presence-message.png)

您也可以設定顯示郵件的頻率，以及設定寬限期：從第一個班次開始或最後一個班次結束，以及何時限制存取Teams。

## <a name="manage-shift-based-access"></a>管理 Shift 型存取

身為系統管理員，您可以使用原則來控制組織中第一線員工的輪班狀態。 您可以使用下列 PowerShell Cmdlet 來管理這些原則：

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

使用 New-CsTeamsShiftsPolicy Cmdlet 建立新原則、設定您要的原則設定，然後使用Grant-CsTeamsShiftsPolicy Cmdlet 將原則指派給使用者。

以下是一些範例。 如需每個原則設定和參數的詳細資訊，包括可供您選擇的預先定義的休假郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-1"></a>範例 1

在此範例中，我們建立了名為 [關閉 Shift] 的新原則Teams Access 預設郵件]。 在此原則中，移位式目前狀態會開啟，而且每當獲派此原則的使用者存取Teams關閉班次時，就會顯示預設訊息。 如果使用者接受訊息，可以在休假時使用Teams，以及第一個班次開始或最後一個班次結束與限制存取之間的寬限期為 10 分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 參數來設定您要顯示的郵件。 若要查看您可以為此參數選擇的預先定義郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-2"></a>範例 2 

在此範例中，我們建立了名為 [關閉 Shift] 的新原則Teams Access 自訂郵件]。 在此原則中，移位式目前狀態會開啟，而且每當獲派此原則的使用者在關閉班次時存取Teams，就會顯示自訂訊息。 如果使用者接受訊息，可以在休假時使用Teams，以及第一個班次開始或最後一個班次結束與限制存取之間的寬限期為 15 分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 參數來設定您要顯示的郵件。 若要深入瞭解，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-3"></a>範例 3

在此範例中，我們建立了名為 [關閉 Shift] Teams Access Message1 的新原則。 在此原則中，移位式目前狀態會開啟，而且每當獲派此原則的使用者在關閉班次時存取Teams，就會顯示下列預先定義的訊息。

  「您的雇主不會授權或核准非免除或每小時員工在其非工作時間內使用其網路、應用程式、系統或工具。 一經接受，即表示您同意您在休假時使用Teams未獲得授權，且不會補償您。」 

如果使用者接受訊息，可以在休假時使用Teams，以及第一個班次開始或最後一個班次結束與限制存取之間的寬限期為三分鐘。  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> 使用 **ShiftNoticeMessageType** 參數來設定您要顯示的郵件。 若要查看您可以為此參數選擇的預先定義郵寄清單，請參閱 [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)。

### <a name="example-4"></a>範例 4

在此範例中，我們指派名為 [關閉 Shift] 的原則Teams Access 自訂訊息給名為 remy@contoso.com 的使用者。

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>相關主題

- [在 Teams 中管理貴組織的 Shifts 應用程式](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 概觀](../../teams-powershell-overview.md)