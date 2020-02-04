---
title: Lync Server 2013：驗證通話寄存的正常化規則
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
ms.openlocfilehash: 2041b807ad16f1e91a83da39739d0ea058a5fba5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f55e2-102">在 Lync Server 2013 中驗證通話寄存的正常化規則</span><span class="sxs-lookup"><span data-stu-id="f55e2-102">Verify normalization rules for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55e2-103">_**主題上次修改日期：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="f55e2-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="f55e2-104">通話駐留軌道式一定不能正常化。</span><span class="sxs-lookup"><span data-stu-id="f55e2-104">Call Park orbits must not be normalized.</span></span> <span data-ttu-id="f55e2-105">檢查您的撥號方案，以確定您的軌道編號不會正常化。</span><span class="sxs-lookup"><span data-stu-id="f55e2-105">Check your dial plans to be sure that your orbit numbers are not normalized.</span></span> <span data-ttu-id="f55e2-106">如果您必須建立額外的正常化規則來避免您的軌道式出現正常化，請遵循在[Lync Server 2013 中建立撥號計畫中](lync-server-2013-create-a-dial-plan.md)的程式，以定義新的正常化規則，**讓符合的模式可**識別軌道範圍和**翻譯模式**為 **$1**。</span><span class="sxs-lookup"><span data-stu-id="f55e2-106">If you must create an additional normalization rule to prevent your orbits from being normalized, follow the procedure in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) to define a new normalization rule, so that **Pattern to match** identifies the orbit range and **Translation pattern** is **$1**.</span></span> <span data-ttu-id="f55e2-107">例如，如果您的通話公園軌道範圍是7000–7999，則**要符合的模式**為 **^ （\\7{3}d） $** and**轉譯模式**是 **$1**。</span><span class="sxs-lookup"><span data-stu-id="f55e2-107">For example, if your Call Park orbit range is 7000 – 7999, the **Pattern to match** is **^(7\\d{3})$** and **Translation pattern** is **$1**.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f55e2-108">請確定您的撥號方案中的預設正常化規則不包含<STRONG>^ （\d \*）</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f55e2-108">Be sure that the default normalization rule in your dial plans does not contain <STRONG>^(\d\*)</STRONG>.</span></span> <span data-ttu-id="f55e2-109">否則，您的通話寄存正常化規則將永遠不會執行。</span><span class="sxs-lookup"><span data-stu-id="f55e2-109">Otherwise, your Call Park normalization rule will never run.</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f55e2-110">請參閱</span><span class="sxs-lookup"><span data-stu-id="f55e2-110">See Also</span></span>


[<span data-ttu-id="f55e2-111">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="f55e2-111">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

