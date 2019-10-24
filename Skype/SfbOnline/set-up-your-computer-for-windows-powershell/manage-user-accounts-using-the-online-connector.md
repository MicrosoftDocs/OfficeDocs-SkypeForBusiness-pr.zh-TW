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
f1keywords: None
ms.custom:
- PowerShell
description: 在 Windows PowerShell 中使用 CsOnlineUser Cmdlet，以取得貴組織商務用 Skype Online 使用者的相關資訊。
ms.openlocfilehash: 02f3aa50f2256cd0d58f4c53cfa607c011bfa565
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "37642862"
---
# <a name="manage-user-accounts-using-the-online-connector"></a>使用線上連接器管理使用者帳戶

## <a name="manage-user-accounts"></a>管理使用者帳戶

本主題包含下列各節：

- [傳回所有 Lync Online 使用者的相關資訊](manage-user-accounts-using-the-online-connector.md#BKAllUsers)

- [在商務用 Skype Online 中針對特定使用者返回資訊](manage-user-accounts-using-the-online-connector.md#BKSpecificUser)

- [針對商務用 Skype Online 中的特定使用者傳回特定資訊](manage-user-accounts-using-the-online-connector.md#BKSpecificUsers)

- [在商務用 Skype Online 中返回篩選的使用者清單](manage-user-accounts-using-the-online-connector.md#BKListofUsers)

> [!NOTE]
> **Move-csuser** Cmdlet 也包含在商務用 Skype Online 系統管理員所提供的一組 Cmdlet 中。 不過， **move-csuser**目前無法用來管理商務用 Skype Online，除非設定_AudioVideoDisabled_參數。 如果您嘗試使用任何其他參數執行 Cmdlet，則會失敗，並出現類似以下的錯誤訊息：無法設定 "SipAddress"。 此參數在遠端租使用者 PowerShell 中受到限制。

### <a name="return-information-about-all-your-skype-for-business-online-users"></a>傳回所有 Lync Online 使用者的相關資訊
<a name="BKAllUsers"> </a>

若要傳回已針對商務用 Skype Online 啟用的所有使用者的相關資訊，請呼叫[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet （不含任何其他參數）。

```
Get-CsOnlineUser
```

若要針對單一、隨機選取的使用者傳回信息（例如，將此帳戶用於測試目的），請呼叫**CsOnlineUser** Cmdlet，並將_ResultSize_參數設定為1。

```
Get-CsOnlineUser -ResultSize 1
```

這會讓**CsOnlineUser** Cmdlet 只傳回一位使用者的資訊，不論貴組織有多少使用者。 若要傳回五個使用者的資訊，請將_ResultSize_參數的值設定為5。

```
Get-CsOnlineUser -ResultSize 5
```

### <a name="return-information-for-a-specific-user-in-skype-for-business-online"></a>在商務用 Skype Online 中針對特定使用者返回資訊
<a name="BKSpecificUser"> </a>

在呼叫[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 時，有多種方式可以參考特定的使用者帳戶。 您可以使用使用者的 Active Directory 網域服務（AD DS）顯示名稱。

```
Get-CsOnlineUser -Identity "Ken Myer"
```

您可以使用使用者的 SIP 位址。

```
Get-CsOnlineUser -Identity "sip:kenmyer@litwareinc.com"
```

您可以使用使用者的使用者主要名稱（UPN）。

```
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

### <a name="return-specific-information-for-specific-users-in-skype-for-business-online"></a>針對商務用 Skype Online 中的特定使用者傳回特定資訊
<a name="BKSpecificUsers"> </a>

根據預設， [CsOnlineUser](https://technet.microsoft.com/library/2bfafd70-a7d9-4308-a353-5ecf44249b53.aspx) Cmdlet 會針對每個商務用 Skype Online 使用者帳戶傳回大量的資訊。 如果您只對該資訊的子集感興趣，請將傳回的資料管道傳送給**Select 物件**Cmdlet。 例如，這個命令會傳回使用者 Ken Myer 的所有資料，然後使用**Select 物件**Cmdlet 來限制在螢幕上顯示的資訊，以便將顯示的資訊限制在與 KEN 的 AD DS 顯示名稱和撥號計畫。

```
Get-CsOnlineUser -Identity "Ken Myer" | Select-Object DisplayName, DialPlan
```

下列命令會傳回所有使用者的顯示名稱和撥號計畫。

```
Get-CsOnlineUser | Select-Object DisplayName, DialPlan
```

若要尋找商務用 Skype Online 使用者帳戶的屬性，請使用下列命令。

```
Get-CsOnlineUser | Get-Member
```

### <a name="return-a-filtered-list-of-users-in-skype-for-business-online"></a>在商務用 Skype Online 中返回篩選的使用者清單
<a name="BKListofUsers"> </a>

透過使用[CsOnlineUser](https://go.microsoft.com/fwlink/p/?linkid=849603) Cmdlet 和_LdapFilter_或_Filter_參數，您可以輕鬆地傳回一組目標使用者的相關資訊。 例如，這個命令會傳回在財務部門中工作的所有使用者。

```
Get-CsOnlineUser -LdapFilter "department=Finance"
```

## <a name="related-topics"></a>相關主題
[使用 Windows PowerShell 設定商務用 skype online 管理電腦](set-up-your-computer-for-windows-powershell.md)


