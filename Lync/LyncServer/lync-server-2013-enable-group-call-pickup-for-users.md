---
title: Lync Server 2013：針對使用者啟用群組呼叫分揀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Group Call Pickup for users
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945620(v=OCS.15)
ms:contentKeyID: 51541457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc2f513960371d0115b63260d35180f319bd923
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a>在 Lync Server 2013 中為使用者啟用群組呼叫挑選

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

使用 SEFAUtil 資源套件工具來為使用者啟用群組呼叫分揀。 使用者必須在 [通話駐留軌道] 表格中，將 [類型 GroupPickup] 指派為「已啟用群組呼叫挑選] 的群組號碼。 您可以指定呼叫挑選群組編號，並在執行 SEFAUtil 時使用/enablegrouppickup 參數同時啟用群組呼叫分揀。

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a>為使用者啟用群組呼叫分揀

1.  以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。

2.  在命令列上執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中將群組呼叫挑選號碼指派給使用者](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[停用 Lync Server 2013 中的使用者的群組呼叫分揀](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

