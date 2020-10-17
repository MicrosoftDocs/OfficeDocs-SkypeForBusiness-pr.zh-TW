---
title: Lync Server 2013：針對使用者啟用群組呼叫收取功能
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
ms.openlocfilehash: 89d512eea147039a5766193f9ec2a20cf45caaa0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528720"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="b02c8-102">在 Lync Server 2013 中為使用者啟用群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="b02c8-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b02c8-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b02c8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b02c8-104">使用 SEFAUtil 資源工具組工具，為使用者啟用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="b02c8-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="b02c8-105">使用者必須被指派「通話駐留軌道」表格中類型為 GroupPickup 的組號，才能啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b02c8-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="b02c8-106">當您執行 SEFAUtil.exe 時，您可以指派呼叫收取群組號碼，並使用/enablegrouppickup 參數，同時啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="b02c8-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="b02c8-107">為使用者啟用群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="b02c8-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="b02c8-108">使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="b02c8-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="b02c8-109">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="b02c8-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="b02c8-110">例如：</span><span class="sxs-lookup"><span data-stu-id="b02c8-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b02c8-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="b02c8-111">See Also</span></span>


[<span data-ttu-id="b02c8-112">將群組呼叫收取號碼指派給 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="b02c8-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="b02c8-113">在 Lync Server 2013 中停用使用者的群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="b02c8-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

