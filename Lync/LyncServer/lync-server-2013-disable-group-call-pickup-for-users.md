---
title: Lync Server 2013：停用使用者的群組呼叫分揀
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
ms.openlocfilehash: f7e47b5c3b12997bd05f3721555a5dfdfe692bbc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="f06a8-102">停用 Lync Server 2013 中的使用者的群組呼叫分揀</span><span class="sxs-lookup"><span data-stu-id="f06a8-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f06a8-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f06a8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f06a8-104">使用下列程式來停用使用者的 [群組呼叫挑選]。</span><span class="sxs-lookup"><span data-stu-id="f06a8-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f06a8-105">當您停用使用者的 [群組呼叫挑選] 時，指派給使用者的呼叫挑選群組號碼就不會保留。</span><span class="sxs-lookup"><span data-stu-id="f06a8-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="f06a8-106">如果您隨後想要重新啟用該使用者的群組呼叫分揀，您必須使用/enablegrouppickup 參數再次指派呼叫挑選群組號碼。</span><span class="sxs-lookup"><span data-stu-id="f06a8-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="f06a8-107">若要停用使用者的群組通話分揀</span><span class="sxs-lookup"><span data-stu-id="f06a8-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="f06a8-108">以系統管理員許可權登入您安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="f06a8-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="f06a8-109">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="f06a8-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="f06a8-110">例如：</span><span class="sxs-lookup"><span data-stu-id="f06a8-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f06a8-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="f06a8-111">See Also</span></span>


[<span data-ttu-id="f06a8-112">在 Lync Server 2013 中將群組呼叫挑選號碼指派給使用者</span><span class="sxs-lookup"><span data-stu-id="f06a8-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="f06a8-113">在 Lync Server 2013 中為使用者啟用群組呼叫挑選</span><span class="sxs-lookup"><span data-stu-id="f06a8-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

