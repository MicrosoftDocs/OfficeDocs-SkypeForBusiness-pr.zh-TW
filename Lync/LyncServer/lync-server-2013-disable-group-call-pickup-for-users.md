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
ms.openlocfilehash: e3e015fd7fc3be36439fb240e2f3f50ed7bc8ec1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="8a3a9-102">為 Lync Server 2013 中的使用者停用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="8a3a9-102">Disable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a3a9-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="8a3a9-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="8a3a9-104">使用下列程序來停用使用者的群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="8a3a9-104">Use the following procedure to disable Group Call Pickup for a user.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a3a9-105">當您停用使用者的群組來電接聽時，不會保留已指派給使用者的通話收取群組編號。</span><span class="sxs-lookup"><span data-stu-id="8a3a9-105">When you disable Group Call Pickup for a user, the call pickup group number that was assigned to the user is not retained.</span></span> <span data-ttu-id="8a3a9-106">如果您之後想要重新啟用使用者群組來電接聽，您必須呼叫收取群組號碼指派一次使用 /enablegrouppickup 參數。</span><span class="sxs-lookup"><span data-stu-id="8a3a9-106">If you subsequently want to re-enable Group Call Pickup for that user, you must assign the call pickup group number again with the /enablegrouppickup parameter.</span></span>



</div>

<div>

## <a name="to-disable-group-call-pickup-for-a-user"></a><span data-ttu-id="8a3a9-107">若要停用使用者的群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="8a3a9-107">To disable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="8a3a9-108">登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="8a3a9-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="8a3a9-109">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="8a3a9-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    <span data-ttu-id="8a3a9-110">例如：</span><span class="sxs-lookup"><span data-stu-id="8a3a9-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a3a9-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="8a3a9-111">See Also</span></span>


[<span data-ttu-id="8a3a9-112">Lync Server 2013 中的使用者指派群組通話收取號碼</span><span class="sxs-lookup"><span data-stu-id="8a3a9-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="8a3a9-113">為 Lync Server 2013 中的使用者啟用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="8a3a9-113">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

