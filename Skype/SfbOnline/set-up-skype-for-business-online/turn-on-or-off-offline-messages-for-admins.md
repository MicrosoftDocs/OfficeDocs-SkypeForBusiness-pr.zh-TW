---
title: 開啟或關閉系統管理員的離線訊息
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
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
- Setup
description: 瞭解如何傳送商務用 Skype立即訊息，即使您的連絡人沒有使用 PowerShell 進行登錄。
ms.openlocfilehash: 7c579e947383c9165035c7cd6a5baee6f2012a1f5bba063dd433f40b95faa164
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326660"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>開啟或關閉系統管理員的離線訊息

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

即使連絡人商務用 Skype，您也可將 IM 傳送至您的連絡人。 這項功能可讓您的連絡人知道您一直嘗試聯繫他們。 在傳送訊息給他們之前，您不需要等到某人在線上。

對於離線郵件，請瞭解：

- 離線郵件不會在使用者的信箱中存檔。

- 離線郵件會送到使用者的信箱，使用者登入時會收到商務用 Skype。

- 如果郵件收件者的狀態設定為請勿打擾或展示，他們會收到從收件者的用戶端所商務用 Skype的郵件。

詳細資訊，請參閱在 商務用 Skype[中使用離線商務用 Skype。](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)

## <a name="to-get-you-started"></a>若要開始使用

> [!NOTE]
> 商務用 Skype Online 連接器目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行版本，則不需要安裝商務用 Skype Online 連接器。
1. 安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell命令提示符，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
若要進一Windows PowerShell，請參閱連線視窗中Office 365所有 Windows PowerShell[](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>開啟或關閉離線 IM

> [!NOTE]
> 離線 **訊息僅適用于** 最新版的 [即用即用 商務用 Skype 用戶端.msi，且在使用舊版的即用即用 商務用 Skype 或 *.msi 檔案安裝 商務用 Skype 用戶端時，則無法使用。

若要啟用或停用組織中使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。 根據預設，此設定為 `True` 。

若要關閉它，請使用 **Set-CsClientPolicy** Cmdlet 並執行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要啟用或停用使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。 根據預設，此設定為  `True` 。 您可以使用現有的策略，或建立如下範例。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [您可能會想要使用 Windows PowerShell 管理Microsoft 365或Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell相比于僅使用 Microsoft 365 系統管理中心，在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)
