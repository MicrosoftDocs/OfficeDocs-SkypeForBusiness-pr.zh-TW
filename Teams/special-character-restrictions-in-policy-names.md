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
description: 查看在策略名稱中特殊字元有什麼問題，以及您可以採取什麼措施修正此問題。
ms.openlocfilehash: b8a628ee261ba813b50d58531ab1255a2f121dc4e4719ff4249de70517215cc3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292970"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>在特殊字元限制中，Teams限制？

**您無法建立或編輯** 郵件 (會議等) 系統管理中心名稱中具有特殊字元Microsoft Teams策略。 

如果策略名稱包含特殊字元，您將受限於在系統管理中心管理Microsoft Teams。 **因此，我們強烈建議策略名稱不要包含特殊字元**。 

已使用 PowerShell 在 Teams 中建立用於會議和傳訊的策略名稱可以有特殊字元，例如 @，#，$。 不過，如果您想要在系統管理中心變更Microsoft Teams，將無法進行。 

如果您有具有特殊字元的政策，您必須使用 Windows PowerShell (永久) 編輯該策略，或在 Microsoft Teams 系統管理中心建立新策略，其設定與舊策略相同，並指派給同一組使用者。

## <a name="to-remove-special-characters"></a>若要移除特殊字元

**步驟 1 - 使用 PowerShell 進行遠端連線。**
> [!NOTE]
> 商務用 Skype線上連接器是目前最新版 PowerShell 模組Teams一部分。
>
> 如果您使用的是最新版[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams版本，則不需要安裝 商務用 Skype 連線連接器。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**步驟 2 - 取得舊策略的設定並捕獲輸出。**

> [!NOTE]
> 此範例適用于 [訊息策略](/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) 。  其他策略類型的步驟會相同，但您必須使用正確的 Cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步驟 3 - 建立新策略。**

您可以使用系統管理中心或 PowerShell，以相同的設定Microsoft Teams新策略。

執行這項操作會為您的建立新策略，但您必須看到 [Set-CsTeamsMessagingPolicy，](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) 然後執行它，以新增正確的設定：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步驟 4 - 指派策略。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
請參閱 [Grant-CsTeamsMessagingPolicy，](/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的更多資訊。

**步驟 5 - 刪除舊策略。**

這會刪除具有特殊字元的舊策略。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
請參閱 [Remove-CsTeamsMessagingPolicy，](/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) 以瞭解有關此 Cmdlet 的更多資訊。

如果此命令成功，即表示您已完成。 如果上述命令會返回錯誤，這是因為舊策略已指派給使用者，因此您必須執行以從該策略移除所有指派的使用者：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想要瞭解如何使用 Windows PowerShell？

Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 您可以使用Windows PowerShell管理Microsoft 365或Office 365管理點，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [為什麼您需要使用 PowerShell Office 365 PowerShell？](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell比使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如一次對許多使用者進行設定變更。 請從下列主題瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 執行常見的線上商務用 Skype管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > Windows PowerShell Online 商務用 Skype模組可讓您建立連線至 Windows PowerShell Online 和 商務用 Skype 的遠端Microsoft Teams。 此模組僅支援在 64 位電腦上，可從 Microsoft 下載中心下載，Windows PowerShell Online 模組商務用 Skype[下載。](https://go.microsoft.com/fwlink/?LinkId=294688)
