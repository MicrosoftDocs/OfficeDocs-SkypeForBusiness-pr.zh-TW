---
title: Lync Server 2013：設定控制同盟使用者存取的原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1eb03e821615835ea7ce1413100a00740d129647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213269"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定控制同盟使用者存取的原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

當您設定原則以支援與同盟協力廠商的通訊時，這些原則會套用至同盟網域的使用者。 您可以設定一或多個外部使用者存取原則，以控制同盟網域的使用者是否可以與您的 Lync Server 2013 使用者共同作業。 若要控制同盟使用者存取，請在全域、網站與使用者層級設定相關原則。 套用於一個原則層級的 Lync Server 原則設定可以覆寫在另一個原則層級套用的設定。 Lync Server 原則優先順序是：使用者原則 (最大的影響) 覆寫網站原則，然後網站原則會覆寫全域原則 (最小影響) 。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

<div>


> [!NOTE]  
> 即便您並未對所屬組織啟用同盟，仍舊可以設定原則來控制同盟使用者存取。 不過，只有當您為組織啟用同盟時，所設定的原則才會生效。 如需啟用同盟的詳細資訊，請參閱部署檔或作業檔中的<A href="lync-server-2013-enable-or-disable-remote-user-access.md">啟用或停用 Lync Server 2013 中的遠端使用者存取</A>。 此外，如果您指定用來控制同盟使用者存取的使用者原則，此原則只適用于已啟用 Lync Server 2013 的使用者，且設定為使用原則。



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>若要設定原則以支援同盟網域使用者存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，依序按一下 [外部使用者存取]**** 及 [外部存取原則]****。

4.  在 **[外部存取原則]** 頁面中，執行下列其中一項：
    
      - 若要設定全域原則以支援同盟使用者存取，依序按一下全域原則、**[編輯]** 以及 **[顯示詳細資料]**。
    
      - 若要建立新的網站原則，請按一下 **[新增]**，然後按一下 **[站台原則]**。在 **[選取網站]** 的清單中按一下適當網站，然後按一下 **[確定]**。
    
      - 若要建立新的使用者原則，按一下 **[新增]**，再按一下 **[使用者原則]**。在 **[新的外部存取原則]** 中，於 **[名稱]** 欄位中建立唯一名稱以代表使用者原則的涵蓋範圍 (例如，建立 **EnableFederatedUsers** 的使用者原則以啟用同盟網域使用者的通訊功能)。
    
      - 若要變更現有原則，按一下表中所列之適當原則，然後按一下 **[編輯]**，接著按一下 **[顯示詳細資料]**。

5.  (選用) 如果您想要新增或編輯說明，請在 [說明]**** 中指定原則資訊。

6.  執行下列其中一項作業：
    
      - 若要啟用原則的同盟使用者存取功能，請選取 **[啟用與同盟使用者的通訊]** 核取方塊。
    
      - 若要停用原則的同盟使用者存取功能，請清除 **[啟用與同盟使用者的通訊]** 核取方塊。

7.  按一下 **[認可]**。

若要啟用同盟使用者存取，您也必須在組織中啟用同盟支援。 如需詳細資訊，請參閱[Enable or disable federation and PUBLIC IM connectivity In Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。

如果這是使用者原則，則您也必須將該原則套用至您希望能與同盟使用者共同作業的使用者。 如需詳細資訊，請參閱[將外部使用者存取原則指派給 Lync Server 2013 中啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 設定現有原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中輸入下列命令：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    一個命令範例，會將適用於同盟使用者存取的全域原則設定為啟用、將 XMPP 網域存取設定為啟用、將遠端使用者存取設定為啟用、將公用提供者存取設定為啟用，以及為支援它的公用提供者授與使用音訊和視訊的能力：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > 在 Lync Server 控制台中，參數「EnablePublicCloudAudioVideoAccess」沒有對應的選取範圍

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 建立新原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中輸入下列命令：
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    建立新網站原則的範例：
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>使用 Windows PowerShell 刪除或重設原則，以支援同盟網域使用者的存取

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  在 Lync Server 管理命令介面中輸入下列命令
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    重設全域原則的範例 (全域原則只能移除它的設定。無法刪除原則)：
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    若要移除網站原則，請輸入：
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    刪除網站原則 Redmond。 若要刪除名為 UserEAPPolicy 的使用者原則，請輸入：
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[在 Lync Server 2013 中將外部使用者存取原則指派給啟用 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[在 Lync Server 2013 中管理組織的 SIP 同盟網域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理組織的 SIP 同盟提供者](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[新 Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授與 Get-csexternalaccesspolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

