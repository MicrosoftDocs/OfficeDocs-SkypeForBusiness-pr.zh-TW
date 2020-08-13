---
title: Lync Server 2013：從 Lync Server 移除使用者帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db45682fd130aba378cab0f9894537ff4c23c28b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-user-account-from-lync-server-2013"></a>從 Lync Server 2013 移除使用者帳戶

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-22_

您可以使用下列程式，在 Lync Server 2013 中移除之前新增的使用者帳戶。

<div>


> [!NOTE]  
> 移除使用者會造成您遺失該使用者的所有設定。 如果您想要暫時停用使用者帳戶，請參閱主題停用<A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">或重新啟用 Lync Server 2013 的使用者帳戶</A>。



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>使用 Lync Server 管理命令介面移除使用者帳戶

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 [搜尋使用者]**** 方塊中，輸入全部或部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或您想要停用或重新啟用的使用者帳戶之線路統一資源識別元 (URI)，然後按一下 [尋找]****。

5.  在表中按一下您想要移除的使用者帳戶。

6.  選取 [動作]**** 功能表中的 [從 Lync Server 移除]****，隨即顯示對話方塊。

7.  選取對話方塊中的 [確定]**** 以移除使用者。

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 移除使用者帳戶

您可以使用 Get-csuser Cmdlet 移除使用者帳戶。 您可以從 Lync Server 2013 管理命令介面或從遠端會話 Windows PowerShell 執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-remove-a-user-account"></a>移除使用者帳戶

  - 若要移除使用者帳戶，請使用 Disable-CsUser Cmdlet。例如：
    
        Disable-CsUser -Identity "Ken Myer"
    
    執行此命令之後，將無法再重新啟用帳戶及其設定。所以請使用 Enable-CsUser Cmdlet 為 Ken Myer 建立新帳戶。

</div>

如需詳細資訊，請參閱[get-csuser 指令程式](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser)的 [說明] 主題。

</div>

<div>

## <a name="see-also"></a>另請參閱


[停用或重新啟用 Lync Server 2013 的使用者帳戶](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[啟用和停用 Lync Server 2013 的使用者](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

