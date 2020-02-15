---
title: Lync Server 2013： 停用使用者的群組來電接聽
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
ms.openlocfilehash: c03242cf0b3521dada944ccaba30946306c1ff24
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a>為 Lync Server 2013 中的使用者停用群組來電接聽

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-30_

使用下列程序來停用使用者的群組來電接聽。

<div>


> [!NOTE]  
> 當您停用使用者的群組來電接聽時，不會保留已指派給使用者的通話收取群組編號。 如果您之後想要重新啟用使用者群組來電接聽，您必須呼叫收取群組號碼指派一次使用 /enablegrouppickup 參數。



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a>若要停用使用者的群組來電接聽

1.  登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的使用者指派群組通話收取號碼](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[為 Lync Server 2013 中的使用者啟用群組來電接聽](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

