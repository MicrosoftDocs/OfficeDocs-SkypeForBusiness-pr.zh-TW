---
title: Lync Server 2013：定義正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 935df08bd1ede124b048427de21594aa6e727e7c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504510"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="8b86e-102">在 Lync Server 2013 中定義正常化規則</span><span class="sxs-lookup"><span data-stu-id="8b86e-102">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b86e-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="8b86e-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="8b86e-104">Lync Server 2013 正規化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉譯為 e.164 格式;換句話說，正規化規則可讓使用者撥打的電話號碼，並將該號碼轉換成 Lync Server 內部所用的格式。</span><span class="sxs-lookup"><span data-stu-id="8b86e-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="8b86e-105">每個撥號對應表都必須被指派一或多個正常化規則。</span><span class="sxs-lookup"><span data-stu-id="8b86e-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="8b86e-106">如需正規化規則的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="8b86e-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="8b86e-107">如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。</span><span class="sxs-lookup"><span data-stu-id="8b86e-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="8b86e-108">您可以使用下列其中一種方法來定義或編輯正規化規則：</span><span class="sxs-lookup"><span data-stu-id="8b86e-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="8b86e-109">使用 [ **建立正規化規則** ] 工具來指定起始數位、長度、要移除的數位和要加入的數位的值，然後讓 Lync Server 控制台產生對應的符合模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="8b86e-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="8b86e-110">手動撰寫規則運算式來定義符合模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="8b86e-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b86e-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8b86e-111">In This Section</span></span>

  - [<span data-ttu-id="8b86e-112">在 Lync Server 2013 中使用組建標準化規則來建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="8b86e-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="8b86e-113">在 Lync Server 2013 中手動建立或修改正規化規則</span><span class="sxs-lookup"><span data-stu-id="8b86e-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b86e-114">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8b86e-114">See Also</span></span>


[<span data-ttu-id="8b86e-115">在 Lync Server 2013 中建立撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8b86e-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="8b86e-116">在 Lync Server 2013 中修改撥號對應表</span><span class="sxs-lookup"><span data-stu-id="8b86e-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

