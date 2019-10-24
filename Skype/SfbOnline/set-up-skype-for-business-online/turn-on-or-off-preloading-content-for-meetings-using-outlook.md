---
title: 開啟或關閉允許使用 Outlook 預先載入會議內容的功能
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
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
- Setup
description: '瞭解如何在 Outlook 會議邀請中使用檔案或附件，在商務用 Skype 會議中開啟或關閉預先載入的內容。 '
ms.openlocfilehash: 61e57b39954df8931b9612e853fccf1e74e9623f
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642289"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>開啟或關閉允許使用 Outlook 預先載入會議內容的功能

使用者可以將附加至 Outlook 會議邀請的內容、檔案或附件預先載入至商務用 Skype Online 會議，但您可以開啟或關閉。 預設會針對所有使用商務用 Skype Online 的組織開啟此功能。 瞭解如何[預先載入商務用 Skype 會議的附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。
  
> [!NOTE]
> 目前在商務用 Skype Online 中沒有可用來設定或查看_MaxContentStorageMB_和_MaxUploadFileMB_線上值的 Cmdlet。 它們僅適用于內部部署的部署。 如果附加內容超過_MaxUploadFileSizeMB_或達到_MaxContentStorageMB_限制，請務必知道內容不會上傳到會議。
  
## <a name="to-get-you-started"></a>若要入門

### 

 **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
  
1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
  
### 

 **啟動 Windows PowerShell 會話**
  
1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
    
2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：
    
    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="turning-it-on-or-off"></a>開啟或關閉

預設會開啟您在 Outlook 會議邀請中預先載入附加至商務用 Skype Online 會議的內容，但您可能需要防止貴組織中的使用者在會議中預先載入內容。
  
> [!IMPORTANT]
> 此設定只能針對您的整個組織開啟或關閉;您無法針對單一使用者開啟或關閉。 
  
 **若要關閉此功能，請開啟 Windows PowerShell，然後執行下列動作：**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **如果您想要將它重新開啟，請開啟 Windows PowerShell，然後執行下列動作：**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
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

  
 
