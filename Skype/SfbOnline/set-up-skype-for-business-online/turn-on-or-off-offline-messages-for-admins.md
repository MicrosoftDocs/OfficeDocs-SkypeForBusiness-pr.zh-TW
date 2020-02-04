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
description: 瞭解如何傳送商務用 Skype 立即訊息，即使您的連絡人未使用 PowerShell 登入也一樣。
ms.openlocfilehash: 2b9cea6e7a4bcb3f7fc34bdf67e77353412d9e13
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706308"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>開啟或關閉系統管理員的離線訊息

您可以將商務用 Skype Im 傳送給您的連絡人，即使他們沒有登入。 這項功能可讓您的聯絡人知道您已嘗試達到。 您不需要等到某人線上才能傳送郵件。

若是離線訊息，請務必瞭解：

- 離線郵件不會在使用者的信箱中歸檔。

- [離線郵件] 會傳送到使用者的信箱，當使用者登入商務用 Skype 時，系統會收到通知。

- 如果郵件收件者的狀態設定為 [**請勿打擾**]**或 [** 簡報]，他們會收到從收件者的商務用 Skype 用戶端傳送的未接訊息。

如需詳細資訊，請參閱[在商務用 Skype 中使用離線訊息](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d)。

## <a name="to-get-you-started"></a>若要入門

## #

 **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**

1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。

2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。

3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。

4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。

如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。

## #

 **啟動 Windows PowerShell 會話**

1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。

2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：

    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。

>
  ```PowerShell
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```

如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。

## <a name="turning-on-or-off-offline-im"></a>開啟或關閉離線 IM

> [!NOTE]
> 離線訊息**只能**在最新版的隨選即用 skype 用戶端版本中使用，當您使用較舊的隨選即用 skype 或 * .msi 檔案來安裝商務用 skype 用戶端時，就無法使用。

若要啟用或停用離線訊息針對貴組織中的使用者傳送離線訊息， `True`請`False`將_EnableIMAutoArchiving_設定為或。 根據預設，這會設定為`True`。

若要關閉此功能，請使用**CsClientPolicy** Cmdlet 並執行：

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

若要啟用或停用離線訊息，請為使用者傳送離線訊息， `True`將`False`[ _EnableIMAutoArchiving_ ] 設定為 [或]。 根據預設，這會設定為`True`。 您可以使用現有的原則，或如下例所示建立一個。


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [您可能會想要使用 Windows PowerShell 來管理 Office 365 的六個原因](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：

  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)


