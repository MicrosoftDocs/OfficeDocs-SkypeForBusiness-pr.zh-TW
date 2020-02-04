---
title: Lync Server 2013：設定原則以控制 XMPP 同盟使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中設定原則以控制 XMPP 同盟使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

這是初步檔，可能會變更。 空白主題是以預留位置形式提供。

當您針對可擴展訊息和目前狀態通訊協定（XMPP）同盟合作夥伴支援策略時，這些原則會套用至 XMPP 聯盟網域的使用者，但不會套用至會話初始通訊協定（SIP）立即訊息（IM）服務提供者的使用者（例如，Windows Live）或 SIP 聯盟網域。 您可以針對每個 XMPP 聯盟網域設定**XMPP 聯盟夥伴**，以允許使用者新增連絡人並與之通訊。 XMPP 聯盟夥伴原則只能在單一範圍內提供，但不是定義為全域原則，充當全域原則。 若要為 XMPP 同盟夥伴定義全域、網站或使用者原則，您必須先建立及設定您所需範圍的外部存取原則，以設定原則範圍。 如需有關您可以針對外部存取與同盟設定的原則類型的詳細資訊，請參閱在作業檔中[管理 Lync Server 2013 的同盟和外部存取](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。

<div>


> [!NOTE]  
> 所有<STRONG>同盟和外部存取</STRONG>原則都是透過頻帶內配來套用。 在登入期間，適用于使用者、屬於網站或全域在範圍內的原則會傳遞給用戶端。 您可以設定原則來控制 XMPP 聯盟夥伴的存取權，即使您的組織未啟用 XMPP 聯盟也一樣。 不過，您設定的原則只有在您的組織部署、啟用並設定 XMPP 合作夥伴同盟時才會生效。 如需有關部署和設定 XMPP 合作夥伴同盟的詳細資訊，請參閱部署檔中的 Lync Server 2013 中的 [設定<A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">SIP 同盟]、[XMPP 聯盟] 和 [公用立即訊息</A>]。 此外，如果您在外部存取原則中指定使用者原則來控制 XMPP 聯盟夥伴，則原則只適用于已啟用 Lync Server 2013 且設定為使用原則的使用者。



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>編輯 XMPP 聯盟合作夥伴的全域原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**外部存取原則**]。

4.  在 [**外部存取原則**] 頁面上，針對全域原則執行下列動作：

5.  按一下全域原則，按一下 [**編輯**]，然後按一下 [顯示詳細資料]。

6.  提供全域原則的描述（選用）。

7.  選取 [**啟用與聯盟使用者的通訊**]。

8.  選取 [**啟用與 XMPP 聯盟使用者的通訊**]。

9.  按一下 [**認可**]，儲存您對全域原則所做的變更。

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>若要為 XMPP 聯盟合作夥伴建立網站或使用者原則

1.  按一下 [**新增**]，然後按一下 [**網站原則**] 或 [**使用者原則**]。 在 [**選取網站**] 中，從清單中按一下適當的網站，然後按一下 **[確定]**。

2.  提供網站原則的描述（選用）。

3.  在網站或使用者原則中，選取 [**啟用與聯盟使用者的通訊**]。

4.  選取 [**啟用與 XMPP 聯盟使用者的通訊**]。

5.  按一下 [**認可**]，儲存您對網站或使用者原則所做的變更。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>編輯 XMPP 聯盟合作夥伴的現有原則

1.  若要變更現有的原則，請在清單中選取適當的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

2.  變更或更新原則的描述（選用）。

3.  選取或取消選取 [**啟用與聯盟使用者的通訊**]。

4.  選取或取消選取 [**啟用與 XMPP 聯盟使用者的通訊**]。

5.  按一下 [**認可**]，儲存您對原則所做的變更。

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 編輯 XMPP 聯盟夥伴的現有原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中輸入下列專案：
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    將同盟使用者存取權設定為 True （啟用），並將網域存取 XMPP 為 True （啟用）的全域原則的範例命令：
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>使用 Windows PowerShell 建立 XMPP 聯盟夥伴的網站或使用者原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中輸入下列專案：
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    將同盟使用者存取權的 [雷德蒙] 網站的網站原則設定為 [已啟用] 並 XMPP [網域存取] 的範例命令：
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>使用 Windows PowerShell 刪除 XMPP 聯盟夥伴的現有原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在 Lync Server 管理命令介面中輸入下列專案：
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    將會刪除使用者原則的範例命令：
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  將全域原則重設為預設值的範例命令：
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中將外部使用者存取原則指派給擁有 Lync 功能的使用者](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[在 Lync Server 2013 中啟用或停用同盟與公用 IM 連線](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[在 Lync Server 2013 中管理 XMPP 同盟夥伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[授與 CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

