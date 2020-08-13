---
title: Lync Server 2013：停用或重新啟用 Lync Server 的使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1e8203d7ca76ed6bb6e9caab33d633af97c21ec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>停用或重新啟用 Lync Server 2013 的使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-04_

您可以使用下列程式停用 Lync Server 2013 中先前啟用的使用者帳戶，而不會遺失您為使用者帳戶所設定的 Lync Server 設定。 因為您不會遺失 Lync Server 使用者帳戶設定，所以您可以重新啟用先前啟用的使用者帳戶，而不需要重新設定使用者帳戶。

<div>


> [!WARNING]  
> 只停用 Active Directory 中的使用者帳戶，<STRONG>不會</STRONG>停止使用者登入或使用 Lync Server。 這是因為 Lync 使用憑證驗證來簡化驗證程式，而這些用戶端憑證在180天內有效。 若要停止停用 Lync 伺服器存取的 Active Directory 帳戶，您必須使用<STRONG>get-csuser 指令程式</STRONG>，或使用<STRONG>lync server 控制台</STRONG>（如本文所述）。 當使用者在 Lync 中停用，且中央管理存放區已在環境中複寫之後，使用者就無法再登入。 而且，已登入的使用者將會中斷連線。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>停用或重新啟用 Lync Server 先前啟用的使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 **[搜尋使用者]** 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 **[尋找]**。

5.  按一下表中您想要停用或重新啟用的使用者帳戶。

6.  在 **[動作]** 功能表上，執行下列其中一項：
    
      - 若要暫時停用 Lync Server 2013 的使用者帳戶，請按一下 [**暫時停用 Lync server**]。
    
      - 若要啟用 Lync Server 2013 的使用者帳戶，請按一下 [**重新啟用 Lync server**]。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows PowerShell 停用或重新啟用使用者帳戶

您可以暫時停用使用者帳戶，然後再使用**Set-CsUser** Cmdlet 重新啟用使用者帳戶。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-disable-a-user-account"></a>停用使用者帳戶

  - 若要暫時停用使用者帳戶，請將 Enabled 內容值設為 False ($False)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>重新啟用使用者帳戶

  - 若要重新啟用已停用的使用者帳戶，請將 Enabled 內容值設為 True ($True)。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

如需詳細資訊，請參閱[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[新增及啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

