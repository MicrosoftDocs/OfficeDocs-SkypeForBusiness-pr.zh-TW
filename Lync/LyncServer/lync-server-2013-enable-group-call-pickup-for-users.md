---
title: Lync Server 2013： 為使用者啟用群組來電接聽
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
ms.openlocfilehash: a7e744f42368cd02b197533b84352f8f0477d848
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-group-call-pickup-for-users-in-lync-server-2013"></a><span data-ttu-id="b5e1e-102">為 Lync Server 2013 中的使用者啟用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="b5e1e-102">Enable Group Call Pickup for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5e1e-103">_**上次修改主題：** 2013年-01-30_</span><span class="sxs-lookup"><span data-stu-id="b5e1e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b5e1e-104">使用 SEFAUtil 資源套件工具來為使用者啟用群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-104">Use the SEFAUtil resource kit tool to enable Group Call Pickup for users.</span></span> <span data-ttu-id="b5e1e-105">使用者必須被指派群組編號的類型 GroupPickup 通話駐留軌道表中已啟用的群組來電接聽。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-105">Users must be assigned a group number with type GroupPickup in the call park orbit table to have Group Call Pickup enabled.</span></span> <span data-ttu-id="b5e1e-106">您指派呼叫收取群組數字，並同時啟用群組來電接聽，當您執行 SEFAUtil.exe 使用 /enablegrouppickup 參數。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-106">You assign a call pickup group number and enable Group Call Pickup at the same time by using the /enablegrouppickup parameter when you run SEFAUtil.exe.</span></span>

<div>

## <a name="to-enable-group-call-pickup-for-a-user"></a><span data-ttu-id="b5e1e-107">若要為使用者啟用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="b5e1e-107">To enable Group Call Pickup for a user</span></span>

1.  <span data-ttu-id="b5e1e-108">登入系統管理員權限安裝 SEFAUtil 工具所在的電腦。</span><span class="sxs-lookup"><span data-stu-id="b5e1e-108">Log on to the computer where you installed the SEFAUtil tool with administrator rights.</span></span>

2.  <span data-ttu-id="b5e1e-109">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="b5e1e-109">At the command line, run:</span></span>
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    <span data-ttu-id="b5e1e-110">例如：</span><span class="sxs-lookup"><span data-stu-id="b5e1e-110">For example:</span></span>
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5e1e-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="b5e1e-111">See Also</span></span>


[<span data-ttu-id="b5e1e-112">Lync Server 2013 中的使用者指派群組通話收取號碼</span><span class="sxs-lookup"><span data-stu-id="b5e1e-112">Assign Group Call Pickup numbers to users in Lync Server 2013</span></span>](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[<span data-ttu-id="b5e1e-113">為 Lync Server 2013 中的使用者停用群組來電接聽</span><span class="sxs-lookup"><span data-stu-id="b5e1e-113">Disable Group Call Pickup for users in Lync Server 2013</span></span>](lync-server-2013-disable-group-call-pickup-for-users.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

