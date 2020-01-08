---
title: Lync Server 2013：稱為 ID 簡報
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>在 Lync Server 2013 中呼叫 ID 簡報

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

使用 Lync Server 2010 時，呼叫方的電話號碼（也就是呼叫的電話號碼）可以從164格式翻譯成幹線對等（也就是相關閘道、私人分支 exchange （PBX）或 SIP 主幹）所需的本機撥號格式。 若要這樣做，您必須先定義一或多個翻譯規則，才能轉換要求 URI，然後再將它傳送到幹線對等。

<div>


> [!IMPORTANT]  
> 將一或多個翻譯規則與企業語音幹線設定關聯的能力，旨在代替在幹線對等上設定翻譯規則的<EM>替代方案</EM>。 如果您已在中繼對等上設定翻譯規則，則不要將翻譯規則與企業語音幹線配置建立關聯，因為這兩個規則可能會衝突。



</div>

您可以使用下列其中一種方法來建立或修改翻譯規則：

  - 使用 [**組建翻譯規則**] 工具來指定起始位數、長度、要移除的數位和要加上的數位的值，然後讓 Lync Server [控制台] 為您產生對應的相符模式與翻譯規則。

  - 手動寫入正則運算式，以定義相符的模式與翻譯規則。

<div>


> [!NOTE]  
> 如需如何撰寫正則運算式的相關資訊，請參閱 ".NET Framework 正<A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>則運算式"。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [使用 Lync Server 2013 中的 [建立翻譯規則] 工具來建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [在 Lync Server 2013 中手動建立或修改翻譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的本機號碼簡報](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

