---
title: Lync Server 2013：停用使用者的群組呼叫收取
description: Lync Server 2013：停用使用者的群組呼叫收取。
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
ms.openlocfilehash: b3f5b4542cf7bb8ea5be524d2695701979ec2987
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568189"
---
# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中停用使用者的群組呼叫收取功能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

請使用下列程式來停用使用者的群組呼叫收取。

<div>


> [!NOTE]  
> 當您停用使用者的群組呼叫收取時，指派給使用者的呼叫收取群組號碼不會保留。 如果您後來想要為該使用者重新啟用群組呼叫收取，您必須使用/enablegrouppickup 參數再次指派呼叫收取群組號碼。



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>停用使用者的群組呼叫收取

1.  使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>請參閱


[將群組呼叫收取號碼指派給 Lync Server 2013 中的使用者](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[在 Lync Server 2013 中為使用者啟用群組呼叫收取](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

