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
description: 商務用 Skype線上可讓您建立其他外部存取策略。 與用戶端或會議策略不同，您可以有多個組合，而有三種預先定義的外部存取策略可以涵蓋大部分的情況。
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240142"
---
# <a name="create-custom-external-access-policies"></a>建立自訂外部存取原則

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

商務用 Skype線上可讓您建立其他外部存取策略。 與用戶端或會議策略不同，您可以有多個組合，而有三種預先定義的外部存取策略可以涵蓋大部分的情況。 這些為：
  
- 沒有聯合或Skype消費者 (_標記：NoFederationAndPIC_ ) 
    
- 僅將聯合存取 (_標記：FederationOnly )_
    
- Federation And Consumer Access (_FederationAndPICDefault)_
    
自訂外部策略允許您建立上述設定未涵蓋的其他策略。 當建立策略時，您必須設定所有所需的參數，而且之後無法變更。 建立新的自訂策略可讓您控制功能，例如Skype使用者存取權或停用公用雲端音訊/視像的政策，這是預先定義的設定未涵蓋的內容。 自訂外部存取策略遵循與用戶端、行動和會議策略相同的語法。 您可以在這裡進一瞭解這些 [設定](/previous-versions//mt228132(v=technet.10))。
  
若要執行此作業，使用者必須使用支援的 2016 即用即商務用 Skype應用程式。 需要下列 2016 商務用 Skype隨用用戶端的最低版本：
  
|**類型**|**發行日期**|**版本**|**建立**|
|:-----|:-----|:-----|:-----|
|目前通道的第一次發行  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (7571.2006)   <br/> |
|目前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (7571.2072)   <br/> |
|延後通道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (7369.2118)   <br/> |
   
> [!CAUTION]
> 使用繼承應用程式或 Mac 用戶端商務用 Skype Windows仍可傳輸檔案。 
  
## <a name="start-windows-powershell"></a>開始Windows PowerShell

> [!NOTE]
> 商務用 Skype線上連接器是目前 PowerShell 模組Teams的一部分。 如果您使用的是最新版 PowerShell Teams版本，則不需要安裝 商務用 Skype連接器。
1. 安裝[powerShell Teams模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell命令提示符，然後執行下列命令： 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   如果您想要啟動 Windows PowerShell 功能連線，請參閱在單一 Microsoft 365 視窗中Office 365 [Windows PowerShell](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)所有 Microsoft 365 或 Office 365 服務，或設定您的電腦[Windows PowerShell。](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a>為使用者建立自訂的外部存取策略

若要這麼做，請執行：
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一Windows PowerShell？

- Windows PowerShell管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點管理 Microsoft 365 或 Office 365 和 商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [為什麼您需要使用 powerShell Microsoft 365 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell使用系統管理中心時，Microsoft 365在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Microsoft 365 管理Microsoft 365或Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理 商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用Windows PowerShell執行線上商務用 Skype管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題
[封鎖點到點檔案傳輸](block-point-to-point-file-transfers.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
