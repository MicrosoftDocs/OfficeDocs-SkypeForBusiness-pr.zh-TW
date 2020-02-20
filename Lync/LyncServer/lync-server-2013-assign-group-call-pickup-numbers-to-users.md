---
title: Lync Server 2013： 指派群組通話收取號碼給使用者
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
ms.openlocfilehash: 172a91c1a1417db6ffd938a48360c7d4bce3533c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a>Lync Server 2013 中的使用者指派群組通話收取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-30_

您將群組來電接聽群組號碼新增至通話駐留軌道表之後，您可以將群組指派給使用者。 若要將通話收取群組指派給使用者使用次要分機功能啟用 (SEFAUtil) 資源套件工具。

<div>


> [!NOTE]  
> 在混合式部署中，沒有指派群組來電接聽群組位於線上的使用者。 位於線上的使用者無法參與群組來電接聽。 亦即其通話無法由其他使用者接聽，他們無法接聽來電給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a>若要將群組來電接聽群組指派給使用者

1.  登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>請參閱


[為 Lync Server 2013 中的使用者啟用群組來電接聽](lync-server-2013-enable-group-call-pickup-for-users.md)  
[為 Lync Server 2013 中的使用者停用群組來電接聽](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

