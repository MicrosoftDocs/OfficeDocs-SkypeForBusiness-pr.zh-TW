---
title: 啟用 Skype 會議廣播
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
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
- SMB
description: 在貴組織的人員可以使用 Skype 會議廣播之前，您需要啟用 Skype 會議廣播。 若要這麼做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮雇用 Microsoft 合作夥伴來執行此步驟。
ms.openlocfilehash: fed56c850d1d909bdd72bda0eb8c1dcd24df0f10
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568889"
---
# <a name="enable-skype-meeting-broadcast"></a>啟用 Skype 會議廣播

> [!IMPORTANT]
> 商務用 Skype Online 將于 2021 年 7 月 31 日終止服務存取權。 我們鼓勵客戶開始升級至 Microsoft 365 中通訊和團隊合作的核心用戶端 Microsoft Teams。

在貴組織的人員可以使用 Skype 會議廣播之前，您需要啟用 Skype 會議廣播。 若要這麼做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮雇用 Microsoft [合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。



> [!NOTE]
> Microsoft Teams 系統管理中心已取代商務用 Skype 系統管理中心 (舊版) 。 管理商務用 Skype 的所有設定現在都位於 Teams 系統管理中心。 您必須被指派全域系統管理員或商務用 Skype 系統管理員 [的 Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) 系統管理員角色，才能在 Teams 系統管理中心管理商務用 Skype 功能。 若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>使用商務用 Skype 系統管理中心啟用 Skype 會議廣播

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 使用全域系統管理員帳戶或商務用 Skype 系統管理員帳戶在 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .
    
2. 在系統管理中心，請前往 **系統管理中心**  >  **Teams。**
    
3. 在 **Teams 系統管理中心**，前往 **舊版入口網站**  >  **Online 會議**  >  **廣播會議**，然後選取 **啟用 Skype 會議廣播**。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>使用 PowerShell 啟用 Skype 會議廣播

1. 安裝 [Teams PowerShell 模組](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。
    
2. 開啟 Windows PowerShell 命令提示程式，然後執行下列命令： 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. 請確認您目前的 Skype 會議廣播設置，請進行：
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    確認參數  _EnableBroadcastMeeting 已_ 設為 `False` 。
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 為貴組織啟用 Skype 會議廣播，請進行：
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    您可以再次進行，確認已啟用  `Get-CsBroadcastMeetingConfiguration` 該設定。
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 進行變更之後，最多可能需要一小時，Skype 會議廣播入口網站才生效。 
  
10. 您的使用者現在可以與公司中的其他使用者召開廣播會議。 若要開始使用，請將它們指向什麼是 [Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>設定您的網路以廣播與外部出席者的會議

如果您有防火牆，而且想要與公司外部人員 (非聯盟企業) 一起保留廣播，您需要使用以下指示設定您的網路：設定 Skype 會議廣播 [的網路](set-up-your-network-for-skype-meeting-broadcast.md)。 
  
如果您還沒有防火牆的安裝經驗，請考慮雇用 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 合作夥伴來執行此步驟。
  
若要略過此步驟，改為將另一個企業新增到您的聯盟，請參閱允許使用者 [與外部商務用 Skype 使用者聯繫](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>相關主題

[Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
