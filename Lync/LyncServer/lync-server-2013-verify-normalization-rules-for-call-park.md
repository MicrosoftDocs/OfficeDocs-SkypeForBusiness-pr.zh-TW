---
title: Lync Server 2013：驗證通話寄存的正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify normalization rules for Call Park
ms:assetid: deaa170f-041e-45cb-8eab-f02931ab541e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398981(v=OCS.15)
ms:contentKeyID: 48185646
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114c7e035d96217f8cf41e88a87ccfd490fe5754
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="1c7ea-102">在 Lync Server 2013 中驗證通話寄存的正常化規則</span><span class="sxs-lookup"><span data-stu-id="1c7ea-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c7ea-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1c7ea-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1c7ea-104">通話駐留軌道式一定不能正常化。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="1c7ea-105">檢查您的撥號方案，以確定您的軌道編號不會正常化。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="1c7ea-106">如果您必須建立額外的正常化規則來避免您的軌道式出現正常化，請遵循在[Lync Server 2013 中建立撥號計畫中](lync-server-2013-create-a-dial-plan.md)的程式，以定義新的正常化規則，**讓符合的模式可**識別軌道範圍和**翻譯模式**為 **$1**。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="1c7ea-107">例如，如果您的通話公園軌道範圍是7000–7999，則**要符合的模式**為 **^ （\\7{3}d） $** and**轉譯模式**是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1c7ea-108">請確定您的撥號方案中的預設正常化規則不包含<STRONG>^ （\d \*）</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="1c7ea-109">否則，您的通話寄存正常化規則將永遠不會執行。</span><span class="sxs-lookup"><span data-stu-id="1c7ea-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1c7ea-110">請參閱</span><span class="sxs-lookup"><span data-stu-id="1c7ea-110">See Also</span></span>


[<span data-ttu-id="1c7ea-111">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="1c7ea-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

