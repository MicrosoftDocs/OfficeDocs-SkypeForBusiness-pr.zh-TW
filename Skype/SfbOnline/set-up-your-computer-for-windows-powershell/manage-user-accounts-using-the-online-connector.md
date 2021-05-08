---
title: 使用線上連接器管理使用者帳戶
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a226b0d4-6359-42b8-808d-4b8ab3736d3b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 Get-CsOnlineUser 中的 Windows PowerShell Cmdlet 來取得貴組織的線上使用者商務用 Skype相關資訊。
ms.openlocfilehash: fa647a7ba80fc649146e2278fb2041343354dead
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238538"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>使用線上連接器管理使用者帳戶

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="manage-user-accounts"></a>管理使用者帳戶

本主題包含下列各節：

- [傳回所有 Lync Online 使用者的相關資訊](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [在 商務用 Skype 中商務用 Skype資訊](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [在 商務用 Skype Online 中商務用 Skype特定資訊](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [在 商務用 Skype 中商務用 Skype清單](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Set-CsUser** Cmdlet 也包含在一組可供線上系統管理員商務用 Skype Cmdlet。 不過，除了設定 _AudioVideoDisabled_ 參數之外 **，Set-CsUser** 目前無法用來管理 商務用 Skype Online。 如果您嘗試使用任何其他參數執行 Cmdlet，它會失敗，出現錯誤訊息，類似：無法設定「SipAddress」。 此參數在遠端租使用者 PowerShell 中受到限制。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>傳回所有 Lync Online 使用者的相關資訊
<a name="BKAllUsers"> </a>

若要返回已啟用 商務用 Skype Online 的所有使用者相關資訊，請撥打[Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet，而不需要任何其他參數。

```PowerShell
Get-CsOnlineUser
```

若要返回單一隨機選取使用者 (的資訊，例如，若要使用此帳戶做為測試用途) ，請撥打 **Get-CsOnlineUser** Cmdlet，將 _ResultSize_ 參數設為 1。

```PowerShell
Get-CsOnlineUser -ResultSize 1
```

這會使 **Get-CsOnlineUser** Cmdlet 只針對一個使用者返回資訊，無論您組織中有多少使用者。 若要返回五個使用者的資訊，請設定 _ResultSize 參數_ 的值為 5。

```PowerShell
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>在 商務用 Skype 中商務用 Skype資訊
<a name="BKSpecificUser"> </a>

在呼叫 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet 時，有多種方式可參照特定使用者帳戶。 您可以使用使用者的 Active Directory 網域服務 (AD DS) 顯示名稱。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用使用者的 SIP 位址。

```PowerShell
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

您可以使用使用者的使用者主體名稱 (UPN) 。

```PowerShell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>在 商務用 Skype Online 中商務用 Skype特定資訊
<a name="BKSpecificUsers"> </a>

根據預設[，Get-CsOnlineUser Cmdlet](/powershell/module/skype/Get-CsOnlineUser)會針對每個線上使用者帳戶商務用 Skype大量的資訊。 如果您只對該資訊的子集感興趣，請用管道將返回的資料傳輸至 **Select-Object** Cmdlet。 例如，此命令會為使用者 Ken Myer 返回所有資料，然後使用 **Select-Object** Cmdlet 將螢幕上顯示的資訊限制為 Ken 的 AD DS 顯示名稱和撥號方案。

```PowerShell
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

下列命令會針對所有使用者返回顯示名稱和撥號方案。

```PowerShell
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要尋找 商務用 Skype Online 使用者帳戶的屬性，請使用下列命令。

```PowerShell
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>在 商務用 Skype 中商務用 Skype清單
<a name="BKListofUsers"> </a>

使用 [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser) Cmdlet 和 _LdapFilter_ 或 _Filter_ 參數，您可以輕鬆地返回一組目標使用者的資訊。 例如，此命令會返回在財務部門工作的所有使用者。

```PowerShell
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相關主題
[使用電腦設定商務用 skype 線上管理Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
