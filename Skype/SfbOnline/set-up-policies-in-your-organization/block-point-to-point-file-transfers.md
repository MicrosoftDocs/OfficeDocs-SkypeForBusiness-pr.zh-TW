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
description: 在商務用 Skype Online 中，您可以控制點到點 (P2P) 檔案傳輸，做為現有會議策略設定之一部分。 不過，無論使用者是否要將檔案傳輸給同一個組織的使用者，或將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。 按照下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。
ms.openlocfilehash: e2a0bb2f250f89433c09566197df7a56efa7f64f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100619"
---
# <a name="block-point-to-point-file-transfers"></a>封鎖點對點檔案傳輸

在商務用 Skype Online 中，您可以控制點到點 (P2P) 檔案傳輸，做為現有會議策略設定之一部分。 不過，無論使用者是否要將檔案傳輸給同一個組織的使用者，或是將檔案傳輸給另一個組織的聯盟使用者，這都允許或阻止使用者的檔案傳輸。 按照下列步驟，您可以封鎖與聯盟組織或合作夥伴的 P2P 檔案傳輸。
  
 一個很常見的情況是，您想要允許內部使用者使用 P2P 檔案傳輸，但封鎖與聯盟合作夥伴的檔案傳輸。 針對此案例，您必須執行以下工作：
  
- 將啟用 P2P 檔案傳輸的會議 (_EnableP2PFileTransfer_ 設為 _True_) 組織的使用者。
    
- 建立全域外部使用者通訊策略集以封鎖外部 P2P 檔案傳輸 (_EnableP2PFileTransfer_ 設為 False _) 並將_ 它指派給貴組織的使用者。 
    
您可以在這裡進一瞭解這些 [設定](/previous-versions//mt228132(v=technet.10))。
  
如果貴組織外部的聯盟使用者嘗試將檔案傳送給已採用原則的使用者，他們會收到傳輸 **失敗** 錯誤。 如果使用者嘗試傳送檔案，他們會收到檔案傳輸 **已關閉** 的錯誤。
  
若要執行此作業，使用者必須使用支援的 2016 按一下即用商務用 Skype 應用程式支援版本。 需要下列商務用 Skype 2016 隨用隨用用戶端的最低版本：
  
|**類型**|**發行日期**|**版本**|**建立**|
|:-----|:-----|:-----|:-----|
|目前通道的第一次發行  <br/> |11/17/2016  <br/> |16.0.7571.2006  <br/> |版本 1611 (7571.2006)   <br/> |
|目前通道  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |版本 1611 (7571.2072)   <br/> |
|延後通道  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |版本 1609 (7369.2118)   <br/> |
   
> [!CAUTION]
> 使用舊版商務用 Skype Windows App 或 Mac 用戶端的使用者仍可傳輸檔案。 
  
## <a name="start-windows-powershell"></a>啟動 Windows PowerShell

> [!NOTE]
> 商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。 如果您使用的是最新的 Teams PowerShell 公開發行，則不需要安裝商務用 Skype Online 連接器。
1. 安裝 [Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示符，然後執行下列命令： 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   如果您想要啟動 Windows PowerShell 的更多相關資訊，請參閱在單一 Windows PowerShell 視窗中連接到所有 [Microsoft 365 或 Office 365 服務](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ，或設定 [電腦以使用 Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)。
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a>停用貴組織的 P2P 檔案傳輸

根據預設 _，EnableP2PFileTransfer_ 會啟用組織的全域原則。 建立時，系統會指派使用者 _BposSAllModality_ 原則。
  
若要允許組織內部 P2P 傳輸，但封鎖外部檔案傳輸至另一個組織，您只需要在全域層級變更。 若要這麼做，請執行：
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a>停用使用者的 P2P 檔案傳輸

您可以建立新原則並授予該使用者，以將這項原則適用于使用者。 若要這麼做，請執行： 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a>想要進一瞭解 Windows PowerShell 嗎？

- Windows PowerShell 就是管理使用者，以及允許或不允許使用者執行哪些操作。 使用 Windows PowerShell，您可以使用單一系統管理點來管理 Microsoft 365 或 Office 365 和商務用 Skype Online，當您有多個工作需要執行時，可以簡化您的日常工作。 若要開始使用 Windows PowerShell，請參閱以下主題：
    
  - [Windows PowerShell 與 Lync Online 的簡介](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [為什麼您需要使用 Microsoft 365 或 Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell 比使用 Microsoft 365 系統管理中心在速度、簡易性及生產力方面有許多優點，例如當您一次對許多使用者進行設定變更時。 請從下列主題瞭解這些優點：
    
  - [使用 Windows PowerShell 管理 Microsoft 365 或 Office 365 的最佳方法](/previous-versions//dn568025(v=technet.10))
    
  - [使用 Windows PowerShell 管理商務用 Skype Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [使用 Windows PowerShell 執行常見的商務用 Skype Online 管理工作](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>相關主題
[建立自訂外部存取原則](create-custom-external-access-policies.md)

[設定組織的用戶端原則](set-up-client-policies-for-your-organization.md)

[在組織中設定會議策略](set-up-conferencing-policies-for-your-organization.md)

  
