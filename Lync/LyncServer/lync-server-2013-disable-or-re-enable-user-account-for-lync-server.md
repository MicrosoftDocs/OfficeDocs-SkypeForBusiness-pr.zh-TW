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
ms.openlocfilehash: aea86048fa29e9b6a21aa040093edff3f53ffe27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>停用或重新啟用 Lync Server 2013 的使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-04_

您可以使用下列程式在 Lync Server 2013 中停用先前啟用的使用者帳戶，而不會遺失您為使用者帳戶所設定的 Lync 伺服器設定。 因為您不會遺失 Lync Server 使用者帳戶設定，所以您可以重新啟用先前已啟用的使用者帳戶，而不需重新設定使用者帳戶。

<div>


> [!WARNING]  
> 只要停用 Active Directory 中的使用者帳戶，<STRONG>就不會</STRONG>阻止使用者登入或使用 Lync Server。 這是因為 Lync 使用憑證驗證來優化驗證程式，而這些用戶端憑證在180天內有效。 如果您想要停止停用 Lync 伺服器存取權的 Active Directory 帳戶，您必須使用<STRONG>Disable move-csuser</STRONG> Cmdlet，或使用<STRONG>Lync server [控制台</STRONG>] 做為本文中所述。 使用者在 Lync 中停用，且中央管理儲存體已在使用者將無法再登入的環境中複製。 此外，已登入的使用者也會中斷連線。



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>針對 Lync Server 停用或重新啟用先前啟用的使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5.  在表格中，按一下您要停用或重新啟用的使用者帳戶。

6.  在 [**動作**] 功能表上，執行下列其中一項操作：
    
      - 若要暫時停用 Lync Server 2013 的使用者帳戶，請按一下 [**針對 Lync Server 暫時停**用]。
    
      - 若要啟用 Lync Server 2013 的使用者帳戶，請按一下 [**針對 Lync Server 重新啟用**]。

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>使用 Windows PowerShell 來停用或重新啟用使用者帳戶

使用者帳戶可以暫時停用，稍後再使用**move-csuser** Cmdlet 重新啟用。 您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-disable-a-user-account"></a>停用使用者帳戶

  - 若要暫時停用使用者帳戶，請將 Enabled 屬性的值設為 False （$False）。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>若要重新啟用使用者帳戶

  - 若要重新啟用已停用的使用者帳戶，請將 Enabled 屬性的值設定為 True （$True）。 例如：
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

如需詳細資訊，請參閱[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[新增及啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

