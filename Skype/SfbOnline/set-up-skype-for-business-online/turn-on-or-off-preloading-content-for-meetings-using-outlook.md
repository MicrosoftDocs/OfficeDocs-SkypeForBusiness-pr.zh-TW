---
title: 開啟或關閉允許使用 Outlook 預先載入會議內容
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
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '瞭解如何使用 Outlook 會議邀請上的檔案或附件，開啟或關閉商務用 Skype 會議預先載入的內容。 '
ms.openlocfilehash: ff0603ca68f4e828fc3b6977065ac9ec3ca6a33d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103799"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>開啟或關閉允許使用 Outlook 預先載入會議內容

使用者可以預先載入附加至商務用 Skype Online 會議之 Outlook 會議邀請的內容、檔案或附件，但您可以開啟或關閉。 它預設為所有使用商務用 Skype Online 的組織開啟。 瞭解如何預先 [載入商務用 Skype 會議附件](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251)。
  
> [!NOTE]
> 目前，商務用 Skype Online 中沒有任何 Cmdlet 可用於設定或檢視  _MaxContentStorageMB_ 和 _MaxUploadFileMB_ 的線上值。 它們僅適用于內部部署。 請注意，如果附加內容超過  _MaxUploadFileSizeMB_ 或已達到 _MaxContentStorageMB_ 限制，內容不會上傳到會議。
  
## <a name="to-get-you-started"></a>若要開始使用

## <a name="start-windows-powershell"></a>啟動 Windows PowerShell

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

如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 服務，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
  
## <a name="turning-it-on-or-off"></a>開啟或關閉

根據預設，可以預先載入附加至商務用 Skype Online 會議之 Outlook 會議邀請的內容，但您可能需要防止貴組織的使用者預先載入其會議內容。
  
> [!IMPORTANT]
> 此設定只能為整個組織開啟或關閉;無法為單一使用者開啟或關閉。 
  
 **若要關閉它，請開啟 Windows PowerShell，然後執行下列操作：**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **如果您想要重新開啟，請開啟 Windows PowerShell，然後執行下列操作：**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
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

  
