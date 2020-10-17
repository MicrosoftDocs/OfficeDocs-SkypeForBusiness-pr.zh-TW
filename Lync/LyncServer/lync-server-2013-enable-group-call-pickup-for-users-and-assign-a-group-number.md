---
title: Lync Server 2013：針對使用者啟用群組呼叫收取及指派群組號碼
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
ms.openlocfilehash: edba55fcfdedc04eb2d8a8356c3d295c381d7c70
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528740"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

在您將呼叫收取群組號碼新增至通話駐留軌道表格之後，您可以將群組號碼指派給使用者，並為其啟用群組呼叫收取。 使用 [次要擴充功能啟動] (SEFAUtil) 資源套件工具指派群組號碼，並啟用群組呼叫收取。

<div>


> [!NOTE]  
> 在混合式部署中，請勿將群組呼叫收取群組指派給位於線上的使用者。 線上中的使用者無法參與「群組呼叫收取」。 也就是說，其他使用者無法接聽他們的來電，也無法接聽來電給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>若要指派群組號碼，並為使用者啟用群組呼叫收取功能

1.  使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。

2.  在命令列中執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如，若要將群組號碼199指派給使用者：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中停用使用者的群組呼叫收取功能](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

