---
title: Lync Server 2013：定義正規化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9406e4fa7445242ae3f112ebfb772713d9d2219c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="eb171-102">在 Lync Server 2013 中定義正規化規則</span><span class="sxs-lookup"><span data-stu-id="eb171-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb171-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="eb171-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="eb171-104">Lync Server 2013 正常化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉換為164格式;換句話說，正常化規則會採用使用者所撥的電話號碼，並將該號碼轉換為 Lync Server 在內部使用的格式。</span><span class="sxs-lookup"><span data-stu-id="eb171-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="eb171-105">每個撥號對應表都必須被指派一或多個正規化規則。</span><span class="sxs-lookup"><span data-stu-id="eb171-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="eb171-106">如需正常化規則的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。</span><span class="sxs-lookup"><span data-stu-id="eb171-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="eb171-107">如需如何撰寫正則運算式的詳細資料，請參閱 ".NET Framework 正[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)則運算式"。</span><span class="sxs-lookup"><span data-stu-id="eb171-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="eb171-108">您可以使用下列其中一種方法來定義或編輯正常化規則：</span><span class="sxs-lookup"><span data-stu-id="eb171-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="eb171-109">使用 [**組建正常化規則**] 工具來指定起始位數、長度、要移除的數位和要加上的數位的值，然後讓 Lync Server [控制台] 為您產生對應的相符模式與翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="eb171-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="eb171-110">手動寫入正則運算式，以定義相符的模式與翻譯規則。</span><span class="sxs-lookup"><span data-stu-id="eb171-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eb171-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="eb171-111">In This Section</span></span>

  - [<span data-ttu-id="eb171-112">在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則</span><span class="sxs-lookup"><span data-stu-id="eb171-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="eb171-113">在 Lync Server 2013 中手動建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="eb171-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="eb171-114">請參閱</span><span class="sxs-lookup"><span data-stu-id="eb171-114">See Also</span></span>


[<span data-ttu-id="eb171-115">在 Lync Server 2013 中建立撥號方案</span><span class="sxs-lookup"><span data-stu-id="eb171-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="eb171-116">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="eb171-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

