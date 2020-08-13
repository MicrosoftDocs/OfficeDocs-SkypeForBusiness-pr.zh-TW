---
title: Lync Server 2013：稱為識別碼簡報
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea49c91269c0a9c4f74a1a226462fbda26aa2af4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="88e95-102">Lync Server 2013 中稱為「識別碼簡報」</span><span class="sxs-lookup"><span data-stu-id="88e95-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88e95-103">_**主題上次修改日期：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="88e95-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="88e95-104">使用 Lync Server 2010 時，所叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成主幹對等 (（即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) ）所需的本機撥號格式。</span><span class="sxs-lookup"><span data-stu-id="88e95-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="88e95-105">若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。</span><span class="sxs-lookup"><span data-stu-id="88e95-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="88e95-p102">將一個或多個轉譯規則與企業語音主幹組態建立關聯的功能，主要是作為在主幹對等上設定轉譯規則的<EM>「替代方法」</EM>。如果您已在主幹對等上設定了轉譯規則，請不要將轉譯規則與企業語音主幹設定相關聯，因為兩種規則可能會衝突。</span><span class="sxs-lookup"><span data-stu-id="88e95-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="88e95-108">您可以使用下列任何一種方法建立或修改轉譯規則：</span><span class="sxs-lookup"><span data-stu-id="88e95-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="88e95-109">您可以使用**組建轉譯規則**工具，指定起始位數、長度、要移除的位數和要加入的數位的值，然後讓 Lync Server 控制台產生對應的符合模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="88e95-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="88e95-110">手動撰寫規則運算式來定義符合模式和轉譯規則。</span><span class="sxs-lookup"><span data-stu-id="88e95-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88e95-111">如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> 。</span><span class="sxs-lookup"><span data-stu-id="88e95-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="88e95-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="88e95-112">In This Section</span></span>

  - [<span data-ttu-id="88e95-113">在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="88e95-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="88e95-114">在 Lync Server 2013 中手動建立或修改轉譯規則</span><span class="sxs-lookup"><span data-stu-id="88e95-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88e95-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="88e95-115">See Also</span></span>


[<span data-ttu-id="88e95-116">Lync Server 2013 中的呼叫者識別碼簡報</span><span class="sxs-lookup"><span data-stu-id="88e95-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

