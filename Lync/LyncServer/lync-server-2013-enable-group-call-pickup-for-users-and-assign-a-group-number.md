---
title: Lync Server 2013： 為使用者啟用群組來電接聽與指派群組編號
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users and assign a group number
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945650(v=OCS.15)
ms:contentKeyID: 51541517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e83972d95956a0ed2bd44f08ba8787c46118730
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136260"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>啟用群組來電接聽 Lync Server 2013 中的使用者並指派群組編號

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-30_

您將呼叫收取群組號碼新增至通話駐留軌道表之後，您將群組號碼指派給使用者，並為他們啟用群組來電接聽。 使用次要分機功能啟用 (SEFAUtil) resource kit 工具來指派群組數字，並啟用群組來電接聽。

<div>


> [!NOTE]  
> 在混合式部署中，沒有指派群組來電接聽群組位於線上的使用者。 位於線上的使用者無法參與群組來電接聽。 亦即其通話無法由其他使用者接聽，他們無法接聽來電給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>若要指派的群組數字，並為使用者啟用群組來電接聽

1.  登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如，若要指派給使用者的群組數目 199:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>另請參閱


[為 Lync Server 2013 中的使用者停用群組來電接聽](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

