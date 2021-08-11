---
title: 在內部部署上啟用使用者企業語音
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
description: 若要讓使用者在 (雲端 PBX) 上使用電話系統，您必須先將它們啟用企業語音並為其指派電話號碼。 您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。
ms.openlocfilehash: aef74877d1a12d136bddc7eedc2a414dfad100830a88bb9a21695004be91d1a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289081"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>在內部部署上啟用使用者企業語音
 
若要讓使用者在 (雲端 PBX) 上使用電話系統，您必須先將它們啟用企業語音並為其指派電話號碼。 您可以使用內部部署來執行這項作業，而使用者仍會駐留在內部部署中。

> [!Important]
> 商務用 Skype線上將于2021年7月31日停用，在此之後將無法再存取服務。  此外，您的內部部署環境之間的 PSTN 連線是否會有商務用 Skype Server 或雲端連接器 Edition 和商務用 Skype 線上，都不再支援。  瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線至 Teams。
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>讓使用者在內部部署企業語音並指派電話號碼

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2. 使用 [[開始] 功能表] 或 [桌面] 快捷方式，開啟 [商務用 Skype Server 控制台]。
    
    您也可以開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 [商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 **[使用者]**。
    
4. 在 [ **搜尋使用者** ] 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI) 的使用者帳戶，然後按一下 [ **尋找**]。
    
5. 在表格中，按一下要針對企業語音啟用的商務用 Skype Online 使用者帳戶。
    
6. 在 [ **編輯** ] 功能表上，按一下 [ **顯示詳細資料**]。
    
7. 在 [**電話語音**] 下，按一下 [**企業語音**]。
    
8. 按一下 [ **行 URI**]，然後輸入唯一的標準化電話號碼 (例如電話： + 14255550200) 。 然後按一下 [ **認可**]。
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>在內部部署企業語音啟用使用者時的特殊考慮

在某些情況下，您可能需要修改讓使用者企業語音的方式，以確保他們可以成功撥打和接聽電話。 如果您的部署中有符合下列條件的使用者，請執行所包含的步驟，為使用者啟用企業語音。
  
- 如果使用者是在您的內部部署 AD 中建立，然後與商務用 Skype Online 進行同步處理，但未啟用商務用 Skype 或企業語音，而且沒有 LineURI 集，請針對每個受影響的使用者執行下列 Cmdlet，並以 \< \> 實際值取代您環境的值：
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 若使用者已在內部部署上啟用商務用 Skype，但尚未啟用企業語音或在將 LineURI 移至商務用 Skype 線上之前將其指派給使用者，請對每個使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 如果已在內部部署商務用 Skype 啟用使用者，但未啟用企業語音，即使已指派 LineURI，也會針對每個受影響的使用者執行下列 Cmdlet：
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```