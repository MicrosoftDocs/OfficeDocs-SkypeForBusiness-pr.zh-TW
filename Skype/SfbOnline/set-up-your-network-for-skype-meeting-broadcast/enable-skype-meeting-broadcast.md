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
description: 在貴組織中的人員可以使用 Skype 會議廣播之前，您必須先啟用它。 若要這樣做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮聘用 Microsoft 合作夥伴來為您執行此步驟。
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753428"
---
# <a name="enable-skype-meeting-broadcast"></a>啟用 Skype 會議廣播

> [!IMPORTANT]
> Microsoft 團隊系統管理中心已將商務用 Skype 系統管理中心 (舊版入口網站) 。 管理商務用 Skype 的所有設定現在都是在團隊系統管理中心。 您必須獲指派全域系統管理員或商務用 Skype 系統管理員的 [AZURE AD 管理員角色](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ，才能管理團隊系統管理中心的商務用 skype 功能。 若要深入了解，請參閱[在 Microsoft Teams 系統管理中心中管理商務用 Skype 設定](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)。

在貴組織中的人員可以使用 Skype 會議廣播之前，您必須先啟用它。 若要這樣做，您必須知道如何使用 Windows PowerShell。 如果您不知道 Windows PowerShell，請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來為您執行此步驟。

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a>使用商務用 Skype 系統管理中心啟用 Skype 會議廣播

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**

1. 使用您的全域系統管理員帳戶或商務用 Skype 系統管理中心帳戶登入 [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) 。
    
2. 在系統管理中心中，移至 [系統**管理中心**]  >  **小組**。
    
3. 在**團隊系統管理中心**中，移至**舊版入口網站**  >  **線上會議**  >  **廣播會議**，然後選取 [**啟用 Skype 會議廣播**]。
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a>使用 PowerShell 啟用 Skype 會議廣播

1. 確認您執行的是 Windows PowerShell 版本3.0 或更高版本。
    
2. 若要確認您執行的是版本3.0 或更高版本： [**開始] 功能表**  >  **Windows PowerShell**。
    
3. 在**Windows PowerShell**視窗中輸入 [_取得主機_]，以檢查版本。
    
4. 如果您沒有版本3.0 或更高版本，您需要下載並安裝 Windows PowerShell 更新。 請參閱 [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) ，以下載並更新 Windows PowerShell 至版本4.0。 出現提示時，請重新開機電腦。
    
5. 您也需要安裝適用于商務用 Skype Online 的 Windows PowerShell 模組，這可讓您建立連線到商務用 Skype Online 的遠端 Windows PowerShell 會話。 此模組只受64位電腦支援，可從 [適用于商務用 Skype Online 的 Windows PowerShell 模組](https://go.microsoft.com/fwlink/?LinkId=294688)上的 Microsoft 下載中心下載。 如果出現提示，請重新開機電腦。
    
6. 從 [ **開始] 功能表**中，選擇 [ **Windows PowerShell**]。
    
7. 在 **Windows PowerShell** 視窗中，執行下列動作以連線至您的 Microsoft 365 或 Office 365：
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. 執行下列動作，以確認您目前的 Skype 會議廣播設定：
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    確認 [參數  _EnableBroadcastMeeting_ ] 已設定為 `False` 。
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. 執行下列動作，為您的組織啟用 Skype 會議廣播：
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    您可以再次執行，確認已啟用該設定  `Get-CsBroadcastMeetingConfiguration` 。
    
     ![Skype 會議廣播啟用組織 Cmdlet。](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > 進行變更之後，可能需要長達一小時的時間，才能在 Skype 會議廣播入口網站中生效。 
  
10. 您的使用者現在可以在您的企業中與其他使用者一起舉行廣播會議。 若要開始使用，請將其指向 [什麼是 Skype 會議廣播？](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a>將您的網路設定為與外部出席者進行廣播會議

如果您有防火牆，而您想要在不是聯盟商務) 的 (企業以外的人員中，進行廣播，您必須使用下列指示來設定您的網路： [為您的 Skype 會議廣播設定您的網路](set-up-your-network-for-skype-meeting-broadcast.md)。 
  
如果您不熟悉如何設定防火牆，請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來為您執行此步驟。
  
若要略過此步驟，而改為將其他公司新增到您的同盟，請參閱 [允許使用者聯繫外部商務用 Skype 使用者](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。 
  
## <a name="related-topics"></a>相關主題

[Windows PowerShell 與 Lync Online 的簡介](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
