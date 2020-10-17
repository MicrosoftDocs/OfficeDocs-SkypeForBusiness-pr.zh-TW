---
title: Lync Server 2013：將群組呼叫收取號碼指派給使用者
description: Lync Server 2013：將群組呼叫收取號碼指派給使用者。
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
ms.openlocfilehash: d550b4556af427e11e99ffb26fb2a6c34d019490
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566129"
---
# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="d5d57-103">將群組呼叫收取號碼指派給 Lync Server 2013 中的使用者</span><span class="sxs-lookup"><span data-stu-id="d5d57-103">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5d57-104">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="d5d57-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="d5d57-105">在您將群組呼叫收取群組號碼新增至通話駐留軌道表格之後，您可以將群組指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d57-105">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="d5d57-106">使用 [次要擴充功能啟動] (SEFAUtil ) 資源套件工具，將來電收取群組指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d57-106">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d5d57-107">在混合式部署中，請勿將群組呼叫收取群組指派給位於線上的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d57-107">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="d5d57-108">線上中的使用者無法參與「群組呼叫收取」。</span><span class="sxs-lookup"><span data-stu-id="d5d57-108">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="d5d57-109">也就是說，其他使用者無法接聽他們的來電，也無法接聽來電給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="d5d57-109">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="d5d57-110">將群組呼叫收取群組指派給使用者</span><span class="sxs-lookup"><span data-stu-id="d5d57-110">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="d5d57-111">使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="d5d57-111">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="d5d57-112">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="d5d57-112">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="d5d57-113">例如：</span><span class="sxs-lookup"><span data-stu-id="d5d57-113">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d5d57-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="d5d57-114">See Also</span></span>


[<span data-ttu-id="d5d57-115">在 Lync Server 2013 中為使用者啟用群組呼叫收取</span><span class="sxs-lookup"><span data-stu-id="d5d57-115">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="d5d57-116">在 Lync Server 2013 中停用使用者的群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="d5d57-116">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

