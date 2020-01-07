---
title: 團隊原則中的特殊字元限制是什麼？
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.teamsadmincenter.policies.naming.error
description: 查看原則名稱中有哪些特殊字元，以及您可以執行哪些動作來修正這些問題。
ms.openlocfilehash: a3e7bccc78641a07b7e2f2b02e12b6fe501f2405
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952756"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>團隊原則中的特殊字元限制是什麼？

**您無法建立或編輯在 Microsoft 團隊系統管理中心的名稱中有特殊字元的原則（適用于訊息、會議等）。** 

如果原則名稱包含特殊字元，您將會受到在 Microsoft 團隊系統管理中心管理這些原則的限制。 **如此一來，我們強烈建議您不要在原則名稱中包含特殊字元**。 

在小組中使用 PowerShell 針對會議和訊息建立的原則名稱，可以有特殊字元（例如 @、#、$）。 不過，如果您想要變更 Microsoft 團隊系統管理中心的原則，您將無法進行。 

如果您擁有含特殊字元的原則，您必須使用 Windows PowerShell （永久）編輯原則，或在 Microsoft 團隊系統管理中心建立新原則，並將與舊版原則相同的設定，並將其指派給相同的使用者群組。

## <a name="to-remove-special-characters"></a>移除特殊字元

**步驟 1-使用 PowerShell 進行遠端連線。**
如果您尚未[設定您的 Windows PowerShell 電腦，請進行設定](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。
```PowerShell
 Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
 $credential = Get-Credential
 $session = New-CsOnlineSession -Credential $credential
 Import-PSSession $session
```


**步驟 2-取得舊版原則的設定並捕獲輸出。**

> [!NOTE]
> 這個範例是針對[訊息](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps)原則。  這些步驟對於其他原則類型是相同的，但您必須使用正確的 Cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步驟 3-建立新原則。**

您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell]，以相同的設定來建立新原則。

執行此操作會為您建立新的原則，但您必須透過 [[設定] CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) ，然後執行才能新增正確的設定：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步驟 4-指派原則。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
如需此 Cmdlet 的詳細資訊，請參閱[授權 CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 。

**步驟 5-刪除舊原則。**

這將會刪除含有特殊字元的舊原則。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
如需此 Cmdlet 的詳細資訊，請參閱[CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 。

如果這個命令成功，您就大功告成了。 如果上述命令傳回錯誤，這是因為舊原則已指派給使用者，因此您需要執行才能從原則中移除所有指派的使用者：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用 Windows PowerShell 進行管理嗎？

Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點來管理 Office 365，以便在有多項工作需要執行時簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼需要使用 Office 365 PowerShell？](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell 的速度、簡潔性和生產率都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者進行設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線到商務用 Skype Online 和 Microsoft 團隊的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。
  

