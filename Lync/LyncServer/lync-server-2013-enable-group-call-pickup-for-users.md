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

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="f054e-102">在 Lync Server 2013 中為使用者啟用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="f054e-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f054e-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f054e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f054e-104">使用 SEFAUtil 資源套件工具來為使用者啟用群組呼叫分揀。</span><span class="sxs-lookup"><span data-stu-id="f054e-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="f054e-105">使用者必須在 [通話駐留軌道] 表格中，將 [類型 GroupPickup] 指派為「已啟用群組呼叫挑選] 的群組號碼。</span><span class="sxs-lookup"><span data-stu-id="f054e-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="f054e-106">您可以指定呼叫挑選群組編號，並在執行 SEFAUtil 時使用/enablegrouppickup 參數同時啟用群組呼叫分揀。</span><span class="sxs-lookup"><span data-stu-id="f054e-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="f054e-107">為使用者啟用群組呼叫分揀</span><span class="sxs-lookup"><span data-stu-id="f054e-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="f054e-108">以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="f054e-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="f054e-109">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="f054e-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="f054e-110">例如：</span><span class="sxs-lookup"><span data-stu-id="f054e-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f054e-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="f054e-111">See Also</span></span>


[<span data-ttu-id="f054e-112">在 Lync Server 2013 中將群組呼叫挑選號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f054e-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="f054e-113">停用 Lync Server 2013 中的使用者的群組呼叫分揀</span><span class="sxs-lookup"><span data-stu-id="f054e-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

