---
title: Lync Server 2013：將群組呼叫收取號碼指派給使用者
description: Lync Server 2013：將群組呼叫收取號碼指派給使用者。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign Group Call Pickup numbers to users
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945647(v=OCS.15)
ms:contentKeyID: 51541508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566129"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>將群組呼叫收取號碼指派給 Lync Server 2013 中的使用者

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

在您將群組呼叫收取群組號碼新增至通話駐留軌道表格之後，您可以將群組指派給使用者。 使用 [次要擴充功能啟動] (SEFAUtil ) 資源套件工具，將來電收取群組指派給使用者。

<div>


> [!NOTE]  
> 在混合式部署中，請勿將群組呼叫收取群組指派給位於線上的使用者。 線上中的使用者無法參與「群組呼叫收取」。 也就是說，其他使用者無法接聽他們的來電，也無法接聽來電給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>將群組呼叫收取群組指派給使用者

1.  使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中為使用者啟用群組呼叫收取](lync-server-2013-enable-group-call-pickup-for-users.md)  
[在 Lync Server 2013 中停用使用者的群組呼叫收取功能](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

