---
title: Lync Server 2013：針對使用者啟用群組呼叫挑選並指派群組號碼
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
ms.openlocfilehash: a5ad9bbc6f5505e5778872a568bdbc80b3f7bf91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a>在 Lync Server 2013 中為使用者啟用群組呼叫挑選，並指派群組號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

在您將呼叫挑選群組編號新增至 [通話駐留軌道] 表格之後，您可以將群組號碼指派給使用者，並為他們啟用群組呼叫分揀。 使用次要延伸功能啟用（SEFAUtil）資源套件工具來指派群組號碼，並啟用群組呼叫分揀。

<div>


> [!NOTE]  
> 在混合式部署中，請勿將群組呼叫挑選群組指派給駐留在線上的使用者。 以線上為宿主的使用者無法參與群組通話挑選。 也就是說，其他使用者無法接聽其來電，也無法將來電應答給其他使用者。



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a>指派群組號碼並為使用者啟用群組呼叫分揀

1.  以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。

2.  在命令列上執行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如，若要將群組號碼199指派給使用者：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a>請參閱


[停用 Lync Server 2013 中的使用者的群組呼叫分揀](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

