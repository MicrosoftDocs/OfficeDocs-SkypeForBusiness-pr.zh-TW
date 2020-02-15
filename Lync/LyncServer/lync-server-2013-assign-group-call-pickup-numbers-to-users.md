---
title: Lync Server 2013： 指派群組通話收取號碼給使用者
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
ms.openlocfilehash: 5a27746909a5a4baa5ea6c3c6d050393e66dab05
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-group-call-pickup-numbers-to-users-in-lync-server-2013"></a><span data-ttu-id="81d28-102">Lync Server 2013 中的使用者指派群組通話收取號碼</span><span class="sxs-lookup"><span data-stu-id="81d28-102">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d28-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="81d28-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="81d28-104">您將群組來電接聽群組號碼新增至通話駐留軌道表之後，您可以將群組指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="81d28-104">After you add Group Call Pickup group numbers to the call park orbit table, you can assign the groups to users.</span></span> <span data-ttu-id="81d28-105">若要將通話收取群組指派給使用者使用次要分機功能啟用 (SEFAUtil) 資源套件工具。</span><span class="sxs-lookup"><span data-stu-id="81d28-105">Use the secondary extension feature activation (SEFAUtil ) resource kit tool to assign call pickup groups to users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="81d28-106">在混合式部署中，沒有指派群組來電接聽群組位於線上的使用者。</span><span class="sxs-lookup"><span data-stu-id="81d28-106">In a hybrid deployment, do not assign a Group Call Pickup group to users who are homed online.</span></span> <span data-ttu-id="81d28-107">位於線上的使用者無法參與群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="81d28-107">Users who are homed online cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="81d28-108">亦即其通話無法由其他使用者接聽，他們無法接聽來電給其他使用者。</span><span class="sxs-lookup"><span data-stu-id="81d28-108">That is, their calls cannot be answered by other users, and they cannot answer calls to other users.</span></span>



</div>

<div>

## <a name="to-assign-a-group-call-pickup-group-to-a-user"></a><span data-ttu-id="81d28-109">若要將群組來電接聽群組指派給使用者</span><span class="sxs-lookup"><span data-stu-id="81d28-109">To assign a Group Call Pickup group to a user</span></span>

1.  <span data-ttu-id="81d28-110">登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="81d28-110">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="81d28-111">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="81d28-111">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="81d28-112">例如：</span><span class="sxs-lookup"><span data-stu-id="81d28-112">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81d28-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="81d28-113">See Also</span></span>


[<span data-ttu-id="81d28-114">為 Lync Server 2013 中的使用者啟用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="81d28-114">Enable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-enable-group-call-pickup-for-users.md)  
[<span data-ttu-id="81d28-115">為 Lync Server 2013 中的使用者停用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="81d28-115">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

