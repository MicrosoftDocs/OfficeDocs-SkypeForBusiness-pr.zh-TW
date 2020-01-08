---
title: Lync Server 2013：將群組呼叫挑選號碼指派給使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e919b1fb4ee225eba1c5317ff1f3049791075bcc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>在 Lync Server 2013 中將群組呼叫挑選號碼指派給使用者

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

在您將群組呼叫挑選群組編號新增至 [通話駐留軌道] 表格之後，您就可以將群組指派給使用者。 使用次要延伸功能啟用（SEFAUtil）資源套件工具，將呼叫挑選群組指派給使用者。

<div>


> [!NOTE]  
> 在混合式部署中，請勿將群組呼叫挑選群組指派給駐留在線上的使用者。 以線上為宿主的使用者無法參與群組通話挑選。 也就是說，其他使用者無法接聽其來電，也無法將來電應答給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>將 [群組呼叫] 群組指派給使用者

1.  以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。

2.  在命令列上執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中為使用者啟用群組呼叫挑選](lync-server-2013-enable-group-call-pickup-for-users.md)  
[停用 Lync Server 2013 中的使用者的群組呼叫分揀](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

