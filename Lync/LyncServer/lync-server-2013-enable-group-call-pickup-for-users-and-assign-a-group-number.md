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
# <a name="enable-group-call-pickup-for-users-in-lync-server-2013-and-assign-a-group-number"></a><span data-ttu-id="025a4-102">為 Lync Server 2013 中的使用者啟用群組呼叫收取，並指派群組號碼</span><span class="sxs-lookup"><span data-stu-id="025a4-102">Enable Group Call Pickup for users in Lync Server 2013 and assign a group number</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="025a4-103">_**主題上次修改日期：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="025a4-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="025a4-104">在您將呼叫收取群組號碼新增至通話駐留軌道表格之後，您可以將群組號碼指派給使用者，並為其啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="025a4-104">After you add call pickup group numbers to the call park orbit table, you assign the group numbers to users and enable Group Call Pickup for them.</span></span> <span data-ttu-id="025a4-105">使用 [次要擴充功能啟動] (SEFAUtil) 資源套件工具指派群組號碼，並啟用群組呼叫收取。</span><span class="sxs-lookup"><span data-stu-id="025a4-105">Use the secondary extension feature activation (SEFAUtil) resource kit tool to assign group numbers and enable Group Call Pickup.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="025a4-106">在混合式部署中，請勿將群組呼叫收取群組指派給位於線上的使用者。</span><span class="sxs-lookup"><span data-stu-id="025a4-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="025a4-107">線上中的使用者無法參與「群組呼叫收取」。</span><span class="sxs-lookup"><span data-stu-id="025a4-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="025a4-108">也就是說，其他使用者無法接聽他們的來電，也無法接聽來電給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="025a4-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-number-and-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="025a4-109">若要指派群組號碼，並為使用者啟用群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="025a4-109">To assign a group number and enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="025a4-110">使用系統管理員權力，登入安裝 SEFAUtil 工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="025a4-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="025a4-111">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="025a4-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="025a4-112">例如，若要將群組號碼199指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="025a4-112">For example, to assign group number 199 to a user:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="025a4-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="025a4-113">See Also</span></span>


[<span data-ttu-id="025a4-114">在 Lync Server 2013 中停用使用者的群組呼叫收取功能</span><span class="sxs-lookup"><span data-stu-id="025a4-114">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

