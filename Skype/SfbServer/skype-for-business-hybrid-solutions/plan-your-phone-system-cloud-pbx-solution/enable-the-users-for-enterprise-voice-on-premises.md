---
title: 啟用企業內部部署的使用者
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 若要讓使用者在 Office 365 （雲端 PBX）中使用電話系統，您必須先啟用企業語音，然後將電話號碼指派給他們。 您可以使用內部部署的部署來執行此動作，而使用者仍在內部部署的部署中。
ms.openlocfilehash: 8bf8720896aa8115cb24d3b632b4ae576f466bcc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003473"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>啟用企業內部部署的使用者
 
若要讓使用者在 Office 365 （雲端 PBX）中使用電話系統，您必須先啟用企業語音，然後將電話號碼指派給他們。 您可以使用內部部署的部署來執行此動作，而使用者仍在內部部署的部署中。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>讓使用者使用企業語音內部部署並指派電話號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2. 使用 [開始] 功能表或 [桌面] 快捷方式來開啟商務用 Skype Server 的 [控制台]。
    
    您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL 來開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**使用者**]。
    
4. 在 [**搜尋使用者**] 方塊中，輸入您要啟用的使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。
    
5. 在表格中，按一下您想要為企業語音啟用的商務用 Skype Online 使用者帳戶。
    
6. 按一下 [**編輯**] 功能表上的 [**顯示詳細資料**]。
    
7. 按一下 [**電話**] 底下的 [**企業語音**]。
    
8. 按一下 [**行 URI**]，然後輸入唯一的、標準化的電話號碼（例如電話： + 14255550200）。 然後按一下 [**確認**]。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>針對企業內部部署啟用使用者時的特殊考慮

在某些情況下，您可能需要修改使用者使用企業語音的方式，以確保他們能夠成功撥打及接聽通話。 如果您的部署中有符合下列條件的使用者，請執行包含以允許使用者使用企業語音的步驟。
  
- 如果使用者是在您的內部部署廣告版中建立，然後與商務用 skype Online 進行同步處理，而不是商務用 skype 或企業語音，且沒有 LineURI 集，請針對您的環境執行下列 Cmdlet，以實際值取代\< \>您的環境中的值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果使用者已在內部部署啟用商務用 Skype，但在移至商務用 Skype Online 前，沒有啟用企業語音或指派 LineURI，請針對每個使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果使用者已在內部部署商務用 Skype 中啟用，但尚未啟用企業語音（即使已指派 LineURI），請針對每個受影響的使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


