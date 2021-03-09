---
title: Teams 原則中的特殊字元限制
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 查看在系統名稱中特殊字元的問題，以及您可以採取什麼措施修正問題。
ms.openlocfilehash: bc5a2fbb28e37602b21e6c519ea3b3b7cb9a0325
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569405"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams 政策中的特殊字元限制是什麼？

在 Microsoft Teams 系統管理中心的名稱中 (訊息、會議等 ) ，您無法建立或編輯具有特殊字元 **的訊息、會議等相關政策**。 

如果策略名稱包含特殊字元，您將受限於在 Microsoft Teams 系統管理中心管理這些策略。 **因此，我們強烈建議您不要包含特殊字元。** 

在 Teams 中為會議和傳訊使用 PowerShell 建立的策略名稱可以具有 @、#、$等特殊字元。 不過，如果您想要在 Microsoft Teams 系統管理中心變更該政策，您將無法變更。 

如果您有具有特殊字元的政策，您必須永遠使用 Windows PowerShell (編輯該政策) 或在 Microsoft Teams 系統管理中心中建立一個新政策，其設定與舊策略相同，並將它指派給同一組使用者。

## <a name="to-remove-special-characters"></a>移除特殊字元

**步驟 1 - 使用 PowerShell 進行遠端連線。**
> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**步驟 2 - 取得舊策略的設定並捕獲輸出。**

> [!NOTE]
> 此範例適用于 [訊息策略](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 。  其他策略類型的步驟會相同，但您必須使用正確的 Cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步驟 3 - 建立新策略。**

您可以使用 Microsoft Teams 系統管理中心或 PowerShell，以相同的設定建立新政策。

執行此程式會建立新策略，但您必須看到 [Set-CsTeamsMessagingPolicy，](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 然後執行它，以新增正確的設定：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步驟 4 - 指派策略。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
請參閱 [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的資訊。

**步驟 5 - 刪除舊策略。**

這會刪除具有特殊字元的舊策略。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
請參閱 [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的資訊。

如果此命令成功，即表示您已完成。 如果上述命令會返回錯誤，這是因為舊策略已指派給使用者，因此您必須執行以從該策略移除所有已指派的使用者：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell 進行管理嗎？

Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365，以簡化多項日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 Office 365 PowerShell？](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 與只使用 Microsoft 365 系統管理中心相比，Windows PowerShell 在速度、簡化和生產力方面有許多優點，例如當您一次為許多使用者變更設定時。 在下列主題中瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > 商務用 Skype Online 的 Windows PowerShell 模組可讓您建立連線至商務用 Skype Online 和 Microsoft Teams 的遠端 Windows PowerShell 會話。 此模組僅支援 64 位電腦，可從商務用 Skype Online Windows PowerShell 模組的 Microsoft 下載 [中心下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
  

