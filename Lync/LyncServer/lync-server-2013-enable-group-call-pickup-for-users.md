---
title: Lync Server 2013：針對使用者啟用群組呼叫收取功能
description: Lync Server 2013：針對使用者啟用群組呼叫收取功能。
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
ms.openlocfilehash: 27951e9000fd17aac90339cf2a507757ae96a397
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559619"
---
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="02f27-103">在 Lync Server 2013 中為使用者啟用群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="02f27-103">Enable Group Call Pickup for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02f27-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="02f27-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="02f27-105">使用 SEFAUtil 資源工具組工具，為使用者啟用群組呼叫收取功能。</span><span class="sxs-lookup"><span data-stu-id="02f27-105">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="02f27-106">使用者必須被指派「通話駐留軌道」表格中類型為 GroupPickup 的組號，才能啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="02f27-106">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="02f27-107">當您執行 SEFAUtil.exe 時，您可以指派呼叫收取群組號碼，並使用/enablegrouppickup 參數，同時啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="02f27-107">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="02f27-108">為使用者啟用群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="02f27-108">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="02f27-109">使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="02f27-109">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="02f27-110">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="02f27-110">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="02f27-111">例如：</span><span class="sxs-lookup"><span data-stu-id="02f27-111">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="02f27-112">請參閱</span><span class="sxs-lookup"><span data-stu-id="02f27-112">See Also</span></span>


[<span data-ttu-id="02f27-113">將群組呼叫收取號碼指派給 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="02f27-113">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="02f27-114">在 Lync Server 2013 中停用使用者的群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="02f27-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

