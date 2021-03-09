---
title: 建立自訂外部存取原則
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: 商務用 Skype Online 可讓您建立其他外部存取策略。 與用戶端或會議策略不同，您可以有多個組合，而有三個預先定義的外部存取策略可涵蓋大部分案例。
ms.openlocfilehash: 22477a54e0c709aa1c01bcfbd6c3bd6aacbb02e0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569129"
---
# <a name="create-custom-external-access-policies"></a>建立自訂外部存取原則

商務用 Skype Online 可讓您建立其他外部存取策略。 與用戶端或會議策略不同，您可以有多個組合，而有三個預先定義的外部存取策略可涵蓋大部分案例。 這些包括：
  
- 無聯盟或 Skype 消費者存取 (_標記：NoFederationAndPIC_ ) 
    
- 僅將聯合存取 (_標記：FederationOnly )_
    
- _FederationAndPICDefault (/FederationAndPICDefault)_
    
自訂外部策略允許您建立上述設定未涵蓋的其他政策。 建立該策略時，您必須設定所有必要的參數，而且之後無法變更。 建立新的自訂策略可允許您控制 Skype 消費者存取權等功能，或停用公用雲端音訊/視音訊的政策，這是預先定義的設定未涵蓋的內容。 自訂外部存取策略的語法與用戶端、行動性及會議策略相同。 您可以在這裡進一瞭解更多這些 [設定](https://technet.microsoft.com/library/mt228132.aspx)。
  
若要進行這項作業，使用者必須使用支援的 2016 即用即用商務用 Skype 應用程式。 需要下列商務用 Skype 2016 隨用用戶端的最低版本：
  
|**類型**|**發行日期**|**版本**|**建立**|
|:-----|:-----|:-----|:-----|
|目前通道的首次發行  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (建立 7571.2006)   <br/> |
|目前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (建立 7571.2072)   <br/> |
|延期通道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (7369.2118)   <br/> |
   
> [!CAUTION]
> 使用舊版商務用 Skype Windows App 或 Mac 用戶端的使用者仍然可以傳輸檔案。 
  
## <a name="start-windows-powershell"></a>啟動 Windows PowerShell

> [!NOTE]
> 商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online Connector。
1. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示程式，然後執行下列命令： 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   如果您想要有關啟動 Windows PowerShell 的資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有[Microsoft 365 或 Office 365](https://technet.microsoft.com/library/dn568015.aspx)服務，或設定[您的電腦以使用 Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>為使用者建立自訂的外部存取策略

若要這麼做，請執行：
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[封鎖點對點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
 
