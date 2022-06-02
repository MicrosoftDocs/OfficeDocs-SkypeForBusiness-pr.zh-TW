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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: 查看原則名稱中含有特殊字元的問題，以及修正問題的方法。
ms.openlocfilehash: c304e292aa10508e7c8b02fe2825b83897f22e38
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860076"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a>Teams原則中的特殊字元限制為何？

**您無法建立或編輯 (Microsoft Teams系統管理中心名稱中具有特殊字元的傳訊、會議等)** 原則。 

如果原則名稱包含特殊字元，您在管理Microsoft Teams系統管理中心時將受限於管理這些原則。 **因此，我們強烈建議原則名稱不要包含特殊字元**。 

在 Teams 中使用 PowerShell 建立會議和傳訊的原則名稱可以具有特殊字元，例如 @，#，$。 不過，如果您想要變更Microsoft Teams系統管理中心的原則，您將無法進行變更。 

如果您有具有特殊字元的原則，您將需要使用Windows PowerShell (永久) 編輯原則，或在Microsoft Teams系統管理中心建立與舊原則相同的設定的新原則，並將它指派給同一組使用者。

## <a name="to-remove-special-characters"></a>移除特殊字元

**步驟 1 - 使用 PowerShell 進行遠端連線。**
> [!NOTE]
> 商務用 Skype Online Connector 目前是最新Teams PowerShell 模組的一部分。
>
> 如果您使用的是最新[Teams PowerShell 公開發行](https://www.powershellgallery.com/packages/MicrosoftTeams/)版，則不需要安裝商務用 Skype Online Connector。

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


**步驟 2 - 取得舊原則的設定並擷取輸出。**

> [!NOTE]
> 此範例適用于 [訊息中心](/powershell/module/skype/get-csteamsmessagingpolicy) 原則。  其他原則類型的步驟會相同，但您必須使用正確的 Cmdlet。 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


**步驟 3 - 建立新原則。**

您可以使用Microsoft Teams系統管理中心或 PowerShell，以相同的設定來建立新原則。

執行此動作會為您建立新原則，但您必須查看 [Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy) 並執行它來新增正確的設定：

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
**步驟 4 - 指派原則。**
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
如需此 Cmdlet 的詳細資訊，請參閱 [Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy) 。

**步驟 5 - 刪除舊原則。**

這會刪除含有特殊字元的舊原則。
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
如需此 Cmdlet 的詳細資訊，請參閱 [Remove-CsTeamsMessagingPolicy](/powershell/module/skype/remove-csteamsmessagingpolicy) 。

如果此命令成功，表示您已完成。 如果上述命令傳回錯誤，這是因為舊的原則已指派給使用者，因此您必須執行以從原則中移除所有指派的使用者：

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a>想知道如何使用Windows PowerShell管理嗎？

Windows PowerShell是管理使用者，以及允許或不允許使用者執行的動作。 透過Windows PowerShell，您可以使用單點系統管理來管理Microsoft 365或Office 365，以簡化當您有多個工作要執行的日常工作。 若要開始使用Windows PowerShell，請參閱下列主題：
    
  - [為什麼您需要使用 powerShell Office 365？](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [使用 Windows PowerShell 管理Microsoft 365或Office 365的最佳方式](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell在速度、簡易性和生產力方面有許多優點，而非只使用Microsoft 365 系統管理中心，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    [使用 Windows PowerShell 管理 商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype線上管理工作](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > 商務用 Skype Online 的Windows PowerShell模組可讓您建立連線到 商務用 Skype Online 和 Microsoft Teams 的遠端Windows PowerShell會話。 只有 64 位電腦才支援此模組，可從 Microsoft 下載中心下載[，網Windows PowerShell Module for 商務用 Skype Online。](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)
