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
f1keywords: None
ms.custom:
- Setup
description: 商務用 Skype Online 可讓您建立其他外部存取原則。 與用戶端或會議原則不同（您可以使用多個組合），有三個預先定義的外部存取原則可涵蓋大部分案例。
ms.openlocfilehash: 7f3edac77af8d9948ef7118c0f94b1ec9c3ae6c1
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642728"
---
# <a name="create-custom-external-access-policies"></a>建立自訂外部存取原則

商務用 Skype Online 可讓您建立其他外部存取原則。 與用戶端或會議原則不同（您可以使用多個組合），有三個預先定義的外部存取原則可涵蓋大部分案例。 這些是：
  
- 沒有聯盟或 Skype 消費者存取權（_標記： NoFederationAndPIC_ ）
    
- 僅限聯盟存取（_Tag： FederationOnly_ ）
    
- 同盟與消費者存取（_FederationAndPICDefault_）
    
自訂外部原則可讓您建立上述設定未涵蓋的其他原則。 建立原則時，您必須設定所有必要的參數，且稍後無法變更。 建立新的自訂原則可讓您控制諸如 Skype 消費者存取的功能，或用來停用公用雲端音訊/視頻的原則，這是預先定義的設定所涵蓋的內容。 自訂外部存取原則遵循與用戶端、行動性與會議原則相同的語法。 您可以在[這裡](https://technet.microsoft.com/en-us/library/mt228132.aspx)找到更多關於這些設定的資訊。
  
若要執行此工作，使用者必須使用受支援版本的2016隨選即用 Skype for business 應用程式（支援它）。 必須使用下列最低版本的商務用 Skype 2016 隨選即用用戶端：
  
|**類型**|**發行日期**|**版本**|**Build**|
|:-----|:-----|:-----|:-----|
|目前通道的初次發行  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本1611（組建7571.2006）  <br/> |
|目前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本1611（組建7571.2072）  <br/> |
|延遲頻道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本1609（組建7369.2118）  <br/> |
   
> [!CAUTION]
> 使用較舊版本商務用 Skype Windows 應用程式或 Mac 用戶端的使用者，仍能傳輸檔案。 
  
## <a name="verify-and-start-windows-powershell"></a>驗證並啟動 Windows PowerShell

- **檢查您執行的是 Windows PowerShell 版本3.0 或更高版本**
    
1. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表** > **Windows PowerShell**。
    
2. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
    如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)。
    
- **啟動 Windows PowerShell 會話**
    
1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
    
2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：
    
    > [!NOTE]
    > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。

   ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/EN-US/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>為使用者建立自訂外部存取原則

若要這樣做，請執行：
  
> 
>   ```
>   New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
>   ```
> 
> 
>   ```
>   Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
>   ```

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[封鎖點對端檔案傳輸](block-point-to-point-file-transfers.md)

[為您的組織設定用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議原則](set-up-conferencing-policies-for-your-organization.md)

  
 
