---
title: 封鎖點對點檔案傳輸
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
description: 在商務用 Skype Online 中，您可以在現有的會議原則設定中，控制點對點（P2P）檔案傳輸。 不過，這會允許或封鎖使用者傳送檔案給同一個組織中的使用者，或其他組織的聯盟使用者。 遵循下列步驟，您可以封鎖與同盟組織或合作夥伴的 P2P 檔案傳輸。
ms.openlocfilehash: 7983ae72cd3b06a21fd4947883a3043d2506b92e
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887962"
---
# <a name="block-point-to-point-file-transfers"></a>封鎖點對點檔案傳輸

在商務用 Skype Online 中，您可以在現有的會議原則設定中，控制點對點（P2P）檔案傳輸。 不過，這會允許或封鎖使用者傳送檔案給同一個組織中的使用者，或其他組織的聯盟使用者。 遵循下列步驟，您可以封鎖與同盟組織或合作夥伴的 P2P 檔案傳輸。
  
 最常見的情況是，您想允許內部使用者使用 P2P 檔案傳輸，但封鎖與聯盟夥伴的檔案傳輸。 在這種情況下，您必須執行下列動作：
  
- 將已啟用 P2P 檔案傳輸的會議原則（_EnableP2PFileTransfer_設定為_True_）指派給組織中的使用者。
    
- 建立全域外部使用者通訊原則，設定為封鎖外部 P2P 檔案傳輸（_EnableP2PFileTransfer_設為_False_），並將它指派給貴組織中的使用者。 
    
您可以在[這裡](https://technet.microsoft.com/library/mt228132.aspx)找到更多關於這些設定的資訊。
  
如果您組織外部的同盟使用者試圖傳送檔案給已套用原則的使用者，他們會收到**傳送失敗**的錯誤。 而且，如果使用者嘗試傳送檔案，他們會收到檔案**傳輸已關閉**的錯誤訊息。
  
若要執行此工作，使用者必須使用支援版本的2016隨選即用 Skype for Business 應用程式（支援它）。 必須使用下列最低版本的商務用 Skype 2016 隨選即用用戶端：
  
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
        
    3. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱[Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
        
    4. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從[適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
    如果您需要進一步瞭解，請參閱[在單一 Windows PowerShell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)。
    
- **啟動 Windows PowerShell 會話**
    
    1. 從 [**開始] 功能表** > 中的 [**Windows PowerShell**]。
        
    2. 在**Windows PowerShell**視窗中，執行下列動作以連線到您的 Office 365 組織：
    
        > [!NOTE]
        > 您在第一次使用商務用 Skype Online Windows PowerShell 模組時，您只需執行匯**入模組**命令。

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   如果您需要啟動 Windows PowerShell 的詳細資訊，請參閱[在單一 Windows powershell 視窗中連線至所有 Office 365 服務](https://technet.microsoft.com/library/dn568015.aspx)，或[設定您的 windows powershell 電腦](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>停用貴組織的 P2P 檔案傳輸

根據預設，會在組織的全域原則上啟用_EnableP2PFileTransfer_ 。 一旦建立，您的使用者就會獲指派_BposSAllModality_原則。
  
若要允許貴組織內的 P2P 傳輸，但封鎖外部檔案傳輸至另一個組織，您只需在全域層面進行變更。 若要執行此動作，請執行：
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>停用使用者的 P2P 檔案傳輸

您可以建立新的原則並將其授與使用者，將此套用至使用者。 若要執行此動作，請執行： 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要深入瞭解 Windows PowerShell 嗎？

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼需要使用 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 來執行常見的商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議原則](set-up-conferencing-policies-for-your-organization.md)

  
 
