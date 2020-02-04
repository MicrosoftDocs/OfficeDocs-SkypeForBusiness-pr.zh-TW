---
title: Lync Server 2013：停用使用者的群組呼叫分揀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable Group Call Pickup for users
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945638(v=OCS.15)
ms:contentKeyID: 51541492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>停用 Lync Server 2013 中的使用者的群組呼叫分揀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

使用下列程式來停用使用者的 [群組呼叫挑選]。

<div>


> [!NOTE]  
> 當您停用使用者的 [群組呼叫挑選] 時，指派給使用者的呼叫挑選群組號碼就不會保留。 如果您隨後想要重新啟用該使用者的群組呼叫分揀，您必須使用/enablegrouppickup 參數再次指派呼叫挑選群組號碼。



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>若要停用使用者的群組通話分揀

1.  以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。

2.  在命令列上執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中將群組呼叫挑選號碼指派給使用者](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[在 Lync Server 2013 中為使用者啟用群組呼叫挑選](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

