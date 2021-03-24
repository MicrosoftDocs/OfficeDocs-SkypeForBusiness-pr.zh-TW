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
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人沒有使用 PowerShell 進行登錄。
ms.openlocfilehash: 82b6b6c70e129d152d716cdc2567a9776b9d0302
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103819"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>開啟或關閉系統管理員的離線訊息

即使連絡人未登錄，您也可以傳送商務用 Skype IM 給連絡人。 這項功能可讓您的連絡人知道您一直嘗試聯繫他們。 在傳送訊息給某人之前，您不需要等到某人在線上。

對於離線郵件，必須知道：

- 離線郵件不會在使用者的信箱中存檔。

- 離線郵件會送到使用者的信箱，使用者登入商務用 Skype 時就會收到通知。

- 如果郵件收件者的狀態設定為請勿打擾或進行展示，他們會收到從收件者的商務用 Skype 用戶端所寄的未接郵件。

詳細資訊，請參閱在商務用 Skype 中使用 [離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。

## <a name="to-get-you-started"></a>若要開始使用

> [!NOTE]
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。
1. 安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示符，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="turning-on-or-off-offline-im"></a>開啟或關閉離線 IM

> [!NOTE]
> 離線 **訊息僅適用于** 最新版的商務用 Skype 用戶端，且使用舊版的隨選即用商務用 Skype，或是使用 *.msi 檔案安裝商務用 Skype 用戶端時，才能使用離線訊息。

若要啟用或停用組織中使用者的離線訊息傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。 根據預設，此設定為 `True` 。

若要關閉它，請使用 **Set-CsClientPolicy** Cmdlet 並執行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要啟用或停用使用者的離線郵件傳送離線訊息，請將  _EnableIMAutoArchiving 設定_ 為 `True` 或 `False` 。 根據預設，此設定為  `True` 。 您可以使用現有的策略，或建立如下範例。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [您可能會想要使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的六個原因](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：

  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))

  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)