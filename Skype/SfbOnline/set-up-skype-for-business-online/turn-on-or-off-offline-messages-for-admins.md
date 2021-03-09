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
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人未使用 PowerShell 進行登錄也一樣。
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568753"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>開啟或關閉系統管理員的離線訊息

您可以傳送商務用 Skype 立即資訊給連絡人，即使他們未登錄也一樣。 這項功能可讓您的連絡人知道您一直在嘗試聯繫他們。 在傳送訊息給某人之前，您不一樣必須等到某人上線。

對於離線郵件，瞭解這一點非常重要：

- 離線郵件不會在使用者的信箱中存檔。

- 離線訊息會送到使用者的信箱，使用者登入商務用 Skype 時也會收到通知。

- 如果郵件收件者的狀態設定為請勿打擾或展示，他們會收到從收件者的商務用 Skype 用戶端所送出未接的訊息。

詳細資訊請參閱在商務用 [Skype 中使用離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。

## <a name="to-get-you-started"></a>若要開始使用

> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。
1. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示程式，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
如果您需要啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>開啟或關閉離線 IM

> [!NOTE]
> 離線訊息僅適用于最新版的商務用 Skype 用戶端，且使用舊版的即用即用商務用 Skype 或 *.msi 檔案來安裝商務用 Skype 用戶端時，才能使用離線訊息。

若要啟用或停用為貴組織使用者傳送離線訊息的離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 或 `True` `False` 。 根據預設，這會設為 `True` 。

若要關閉，請使用 **Set-CsClientPolicy** Cmdlet 並執行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要啟用或停用使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。 根據預設，這會設為  `True` 。 您可以使用現有政策，或建立類似以下範例的一個。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [為何要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：

  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)
