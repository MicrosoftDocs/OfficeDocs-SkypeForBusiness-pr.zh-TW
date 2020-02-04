---
title: Lync Server 2013：啟用或停用匿名使用者存取
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中啟用或停用匿名使用者存取

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-23_

匿名使用者是在組織的 Active Directory 網域服務或受支援的聯盟網域中沒有使用者帳戶的使用者，但在內部部署會議中可以受邀參與遠端參與。 透過允許匿名參與會議，您可以啟用匿名使用者（也就是僅透過會議或會議金鑰驗證身分識別的使用者）加入會議。 允許匿名參與需要為您的組織啟用。

如果您稍後想要暫時或永久避免匿名使用者的存取權，您可以針對您的組織停用它。 您可以使用本節中的程式來啟用或停用您組織的匿名使用者存取權。

<div>


> [!NOTE]  
> 透過針對您的組織啟用匿名使用者存取，您只會指定執行存取邊緣服務的伺服器支援由匿名使用者進行存取。 匿名使用者無法參與貴組織中的任何會議，除非您也設定了至少一個會議原則，並將它套用至一或多個使用者或使用者群組。 只有指派會議原則且設定為支援匿名使用者的使用者，才能邀請匿名使用者加入會議的使用者。 如需設定會議原則以支援邀請匿名使用者的詳細資料，請參閱<A href="lync-server-2013-conferencing-policies.md">Lync Server 2013 中的會議原則</A>。



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>若要啟用或停用您組織的匿名使用者存取權

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**外部使用者存取**]，然後按一下 [**存取邊緣**設定]。

4.  在 [**存取邊緣**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯存取邊緣**設定] 中，執行下列其中一項操作：
    
      - 若要為您的組織啟用匿名使用者存取，請選取 [**啟用與匿名使用者的通訊**] 核取方塊。
    
      - 若要停用您組織的匿名使用者存取，請清除 [**啟用與匿名使用者的通訊**] 核取方塊。

6.  按一下 [認可]****。

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 來啟用或停用匿名使用者存取

您可以使用 Windows PowerShell 和**CsAccessEdgeConfiguration** Cmdlet 來管理匿名使用者存取。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-anonymous-user-access"></a>啟用匿名使用者存取

  - 若要啟用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 True （$True）：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>若要停用匿名使用者存取

  - 若要停用匿名使用者存取，請將**AllowAnonymousUsers**屬性的值設定為 False （$False）：
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

