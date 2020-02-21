---
title: Lync Server 2013： 確認通話駐留的正規化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fcde0adac292b8773a81c759c72765f832ce745
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="ed389-102">確認 Lync Server 2013 中的通話駐留的正規化規則</span><span class="sxs-lookup"><span data-stu-id="ed389-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed389-103">_**主題上次修改日期：** 2012年-09-11_</span><span class="sxs-lookup"><span data-stu-id="ed389-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="ed389-104">通話駐留軌道必須不會被正規化。</span><span class="sxs-lookup"><span data-stu-id="ed389-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="ed389-105">請檢查您的撥號對應表計劃，以確定您的軌道號碼不正規化。</span><span class="sxs-lookup"><span data-stu-id="ed389-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="ed389-106">如果您必須建立額外的正規化規則，以防止您軌道要正規化，請依照下列程序中[建立撥號對應表 Lync Server 2013 中的](lync-server-2013-create-a-dial-plan.md)用來定義新的正規化規則，以便**來比對**識別軌道範圍和**翻譯模式**是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="ed389-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="ed389-107">例如，如果您的通話駐留軌道範圍是 7000 – 7999，**來比對**是 **^ (7\\d{3}) $** 和**翻譯模式**是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="ed389-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ed389-108">請務必在撥號對應表計劃中的預設正規化規則不包含<STRONG>^(\d\*)</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="ed389-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="ed389-109">否則，永遠不會執行您的通話駐留正規化規則。</span><span class="sxs-lookup"><span data-stu-id="ed389-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ed389-110">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ed389-110">See Also</span></span>


[<span data-ttu-id="ed389-111">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="ed389-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

