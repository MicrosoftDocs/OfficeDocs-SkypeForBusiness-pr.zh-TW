---
title: 為使用者啟用企業語音-內部部署
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 若要讓使用者 (Cloud PBX) ，您必須先啟用企業語音，並為其指定電話號碼。 您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359189"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>為使用者啟用企業語音-內部部署
 
若要讓使用者 (Cloud PBX) ，您必須先啟用企業語音，並為其指定電話號碼。 您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。

> [!Important]
> 在2021年7月31日之後，商務用 Skype Online 將會停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線，不論是透過商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype Online，都將不再支援。  瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>為使用者啟用企業語音內部部署和指派電話號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 使用「開始」功能表或桌面快捷方式，開啟商務用 Skype Server 控制台。
    
    您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。
    
5. 在表格中，按一下您要啟用 Enterprise Voice 的商務用 Skype Online 使用者帳戶。
    
6. 在 [ **編輯** ] 功能表上，按一下 [ **顯示詳細資料**]。
    
7. 在 [ **電話**語音] 下，按一下 [ **Enterprise Voice**]。
    
8. 按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如電話： + 14255550200) 。 然後按一下 [ **認可**]。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>讓使用者在內部部署企業語音時的特殊考慮

在某些情況下，您可能需要修改讓使用者使用 Enterprise Voice 的方式，以確保他們能夠成功撥打和接聽電話。 如果您的部署中有符合下列條件的使用者，請執行所包含的步驟，以啟用使用者的 Enterprise Voice。
  
- 如果使用者是在您的內部部署 AD 中建立，然後與商務用 skype Online 同步處理，且未啟用商務用 Skype 或 Enterprise Voice，而且沒有 LineURI 集，請針對每個受影響的使用者執行下列 Cmdlet，以 \< \> 實際值取代您環境的值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果使用者已啟用商務用 Skype 內部部署，但尚未啟用 Enterprise Voice 或已被指派 LineURI 的使用者移至商務用 Skype Online，請為每個使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果使用者已啟用商務用 Skype 內部部署，但未啟用 Enterprise Voice，即使已指派 LineURI，也請為每個受影響的使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


