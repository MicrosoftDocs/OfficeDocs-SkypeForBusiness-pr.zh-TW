---
title: 設定控制同盟使用者存取的原則
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: '當您設定原則以支援與同盟協力廠商的通訊時，這些原則會套用至同盟網域的使用者。 '
ms.openlocfilehash: 86d3988df429b3bc9ef2972aa27e0a6ed03ceb72
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588585"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>在商務用 Skype Server 中設定控制同盟使用者存取的原則

當您設定原則以支援與同盟協力廠商的通訊時，這些原則會套用至同盟網域的使用者。 您可以設定一或多個外部使用者存取原則，以控制同盟網域的使用者是否可以與您的商務用 Skype Server 使用者共同作業。 若要控制同盟使用者存取，請在全域、網站與使用者層級設定相關原則。 商務用 Skype Server 于一個原則層級套用的原則設定，會覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。


> [!NOTE]  
> 即便您並未對所屬組織啟用同盟，仍舊可以設定原則來控制同盟使用者存取。 不過，只有當您為組織啟用同盟時，所設定的原則才會生效。 如需啟用同盟的詳細資訊，請參閱 [啟用或停用遠端使用者存取](../access-edge/enable-or-disable-remote-user-access.md)。  此外，如果您指定用來控制同盟使用者存取的使用者原則，此原則只會套用至已啟用商務用 Skype Server 和設定為使用原則的使用者。


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>若要設定原則以支援同盟網域使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。

3.  在左導覽列中，依序按一下 [外部使用者存取] 及 [外部存取原則]。

4.  在 **[外部存取原則]** 頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援同盟使用者存取，依序按一下全域原則、**[編輯]** 以及 **[顯示詳細資料]**。
    
      - 若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取網站]** 的清單中按一下適當網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。在 **[新的外部存取原則]** 中，於 **[名稱]** 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnableFederatedUsers** 的使用者原則以啟用同盟網域使用者的通訊功能)。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 **[編輯]**，接著按一下 **[顯示詳細資料]**。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明] 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的同盟使用者存取功能，請選取 **[啟用與同盟使用者的通訊]** 核取方塊。
    
      - 若要停用原則的同盟使用者存取功能，請清除 **[啟用與同盟使用者的通訊]** 核取方塊。

7.  按一下 **[認可]**。

若要啟用同盟使用者存取，您也必須在組織中啟用同盟支援。 如需詳細資訊，請參閱 [Enable or disable federation and PUBLIC IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)。

如果這是使用者原則，則您也必須將該原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱 [指派外部使用者存取原則](assign-an-external-user-access-policy.md)。

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 設定現有原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Busines Server 管理命令介面的 Skype：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3.  在商務用 Skype Server 管理命令介面中輸入下列命令：
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > 參數「EnablePublicCloudAudioVideoAccess」在商務用 Skype Server 控制台中沒有對應的選取範圍


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 建立新原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft 商務用 Skype Server**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。

3.  在商務用 Skype Server 管理命令介面中輸入下列命令：
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    建立新網站原則的範例：
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>若要使用 Windows PowerShell 刪除或重設原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  在商務用 Skype Server 管理命令介面中輸入下列命令
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    重設全域原則的範例 (全域原則只能移除它的設定。無法刪除原則)：
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    若要移除網站原則，請輸入：
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    刪除網站原則 Redmond。 若要刪除名為 UserEAPPolicy 的使用者原則，請輸入：
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>另請參閱


[啟用或停用同盟和公用 IM 連線](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[指派外部使用者存取原則](assign-an-external-user-access-policy.md)

[管理貴組織的 SIP 同盟網域](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[管理貴組織的 SIP 同盟提供者](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Get-csexternalaccesspolicy](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新 Get-csexternalaccesspolicy](/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-Get-csexternalaccesspolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授與 Get-csexternalaccesspolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
