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
description: 在商務用 Skype Online 中，您可以控制以現有會議 (P2P) 進行檔案傳輸。 不過，無論使用者是否將檔案傳輸給同一個組織內的使用者，或將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。 遵循下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569099"
---
# <a name="block-point-to-point-file-transfers"></a>封鎖點對點檔案傳輸

在商務用 Skype Online 中，您可以控制以現有會議 (P2P) 進行檔案傳輸。 不過，無論使用者是否將檔案傳輸給同一個組織內的使用者，或將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。 遵循下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。
  
 一個很常見的情況是，您想要允許內部使用者使用 P2P 檔案傳輸，但封鎖與聯盟合作夥伴的檔案傳輸。 在此情境中，您必須執行：
  
- 將啟用 P2P 檔案傳輸的會議 (_EnableP2PFileTransfer_ 設為 _True_) 指派給貴組織的使用者。
    
- 建立全域外部使用者通訊策略集以封鎖外部 P2P 檔案傳輸 (_EnableP2PFileTransfer_ 設為 _False_) 並將它指派給貴組織的使用者。 
    
您可以在這裡進一瞭解更多這些 [設定](https://technet.microsoft.com/library/mt228132.aspx)。
  
如果組織外部的聯盟使用者嘗試將檔案傳送給已使用原則的使用者，則會收到傳輸 **失敗** 錯誤。 如果使用者嘗試傳送檔案，他們會收到檔案傳輸 **已關閉** 的錯誤。
  
若要執行此作業，使用者必須使用支援的 2016 即用即用商務用 Skype 應用程式支援版本。 需要下列商務用 Skype 2016 隨用用戶端的最低版本：
  
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
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>停用組織的 P2P 檔案傳輸

根據預設 _，EnableP2PFileTransfer 會_ 啟用組織的全域原則。 建立時，使用者會指派 _BposSAllModality_ 原則。
  
若要允許組織內部進行 P2P 傳輸，但封鎖外部檔案傳輸至另一個組織，您只需要在全域層級進行變更。 若要這麼做，請執行：
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>停用使用者的 P2P 檔案傳輸

您可以建立新原則，並授予該使用者，以將這項原則適用于使用者。 若要這麼做，請執行： 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解更多 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或禁止使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單點系統管理來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個任務作時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell 在速度、簡易性和生產力方面有許多優點，比只使用 Microsoft 365 系統管理中心有許多優點，例如當您一次為許多使用者進行設定變更時。 在下列主題中瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方式](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [使用 Windows PowerShell 執行一般商務用 Skype Online 管理工作](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
 
