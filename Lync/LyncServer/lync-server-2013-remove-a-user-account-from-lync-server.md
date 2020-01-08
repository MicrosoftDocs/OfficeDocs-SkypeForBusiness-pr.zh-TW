---
title: Lync Server 2013：從 Lync Server 移除使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9780e19fb608855d9c820285cc87582787ff896d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>從 Lync Server 2013 移除使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您可以使用下列程式在 Lync Server 2013 中移除先前新增的使用者帳戶。

<div>


> [!NOTE]  
> 移除使用者將會導致您遺失任何您為使用者帳戶所設定的設定。 如果您想改為暫時停用使用者帳戶，請參閱停用<A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">或重新啟用 Lync Server 2013 的使用者帳戶</A>主題。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面移除使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您想要停用或重新啟用之使用者帳戶的全部或第一部分的顯示名稱、名字、姓氏、安全帳戶管理員（SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI），然後按一下 [**尋找**]。

5.  在表格中，按一下您要移除的使用者帳戶。

6.  在 [**動作**] 功能表上，選取 [**從 Lync Server 移除**]，隨後便會出現一個對話方塊。

7.  從對話方塊中，選取 **[確定]** 以移除使用者。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除使用者帳戶

您可以使用 Disable Move-csuser Cmdlet 來移除使用者帳戶。 這個 Cmdlet 可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行。 如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-remove-a-user-account"></a>移除使用者帳戶

  - 若要移除使用者帳戶，請使用 Disable-Move-csuser Cmdlet。 例如：
    
        Disable-CsUser -Identity "Ken Myer"
    
    執行此命令之後，就無法重新啟用帳戶及其先前的設定。 相反地，您必須使用 Enable-Move-csuser Cmdlet 來為 Ken Myer 建立全新的帳戶。

</div>

如需詳細資訊，請參閱[Disable move-csuser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) Cmdlet 的說明主題。

</div>

<div>

## <a name="see-also"></a>請參閱


[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

