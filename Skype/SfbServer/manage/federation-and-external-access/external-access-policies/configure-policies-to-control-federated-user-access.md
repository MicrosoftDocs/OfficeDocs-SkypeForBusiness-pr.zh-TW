---
title: 設定控制同盟使用者存取的原則
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: '當您將原則設定為支援與同盟夥伴的通訊時，這些原則會套用至同盟網域的使用者。 '
ms.openlocfilehash: 2e9385436427fd73f90e308d7747cf304bf37501
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818314"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定控制聯盟使用者存取權的原則

當您將原則設定為支援與同盟夥伴的通訊時，這些原則會套用至同盟網域的使用者。 您可以設定一或多個外部使用者存取原則，以控制聯盟網域的使用者是否可與您的商務用 Skype 伺服器使用者共同作業。 若要控制同盟使用者存取權，您可以在全域、網站和使用者層級設定原則。 在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。


> [!NOTE]  
> 您可以設定控制聯盟使用者存取的原則，即使您的組織未啟用同盟也一樣。 不過，您設定的原則只會在您的組織啟用同盟時生效。 如需啟用同盟的詳細資料，請參閱[啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。  此外，如果您指定要控制同盟使用者存取權的使用者原則，原則只適用于已啟用商務用 Skype Server 且設定為使用原則的使用者。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>若要設定受同盟網域使用者支援存取的原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，執行下列其中一項操作：
    
      - 若要設定全域原則以支援同盟使用者存取，請按一下全域原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
      - 若要建立新的網站原則，請按一下 [**新增**]，然後按一下 [**網站原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，請按一下 [**新增**]，然後按一下 [**使用者原則**]。 在**新的外部存取原則**中，在 [name] （**名稱**）欄位中建立唯一的名稱，以指出使用者原則所涵蓋的內容（例如，為聯盟網域使用者啟用通訊的使用者原則**EnableFederatedUsers** ）。
    
      - 若要變更現有的原則，請按一下表格中所列的適當原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  可選如果您想要新增或編輯描述，請在 [**描述**] 中指定原則的資訊。

6.  請執行下列其中一項操作：
    
      - 若要針對原則啟用聯盟使用者存取，請選取 [**啟用與同盟使用者的通訊**] 核取方塊。
    
      - 若要停用同盟使用者對原則的存取權，請清除 [**啟用與聯盟使用者的通訊**] 核取方塊。

7.  按一下 [認可]****。

若要啟用聯盟使用者存取，您也必須在組織中啟用同盟的支援。 如需詳細資訊，請參閱[啟用或停用同盟與公用 IM](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線。

如果這是使用者原則，您也必須將原則套用到您想要能夠與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[指派外部使用者存取原則](assign-an-external-user-access-policy.md)。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 設定現有的原則以支援由聯盟網域的使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動名片伺服器管理命令介面的 Skype：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype**Server]，然後按一下 [商務用**skype server 管理命令**介面]。

3.  在商務用 Skype Server Management 命令介面中輸入下列專案：
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > [商務用 Skype 伺服器] 控制台中的參數 "EnablePublicCloudAudioVideoAccess" 沒有對應的選取專案


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 建立新原則以支援由聯盟網域的使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 商務用 skype server**]，然後按一下 [**商務用 skype server management Shell**]。

3.  在商務用 Skype Server Management 命令介面中輸入下列專案：
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    建立新網站原則的範例：
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 刪除或重設原則，以支援由聯盟網域的使用者存取

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  在商務用 Skype Server Management 命令介面中輸入以下命令
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    重設全域原則（全域原則只能移除其設定）的範例。 無法刪除原則）：
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    若要移除網站原則，請輸入：
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    刪除網站原則雷德蒙。 若要刪除名為 UserEAPPolicy 的使用者原則，請輸入：
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>請參閱


[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[指派外部使用者存取原則](assign-an-external-user-access-policy.md)

[管理貴組織的 SIP 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授與 CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

