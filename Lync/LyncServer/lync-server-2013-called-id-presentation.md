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
ms.openlocfilehash: dddb1902422cb3efc52f4f0b3271976ab9b9950e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508220"
---
# <a name="called-id-presentation-in-lync-server-2013"></a>Lync Server 2013 中稱為「識別碼簡報」

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

使用 Lync Server 2010 時，所叫方的電話號碼 (也就是說，稱為) 的電話號碼可以從 e.164 格式轉譯成主幹對等 (（即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) ）所需的本機撥號格式。 若要執行此項作業，您必須定義一或多個轉譯規則，以在將其路由傳送至主幹對等之前轉譯要求 URI。

<div>


> [!IMPORTANT]  
> 將一個或多個轉譯規則與企業語音主幹組態建立關聯的功能，主要是作為在主幹對等上設定轉譯規則的<EM>「替代方法」</EM>。如果您已在主幹對等上設定了轉譯規則，請不要將轉譯規則與企業語音主幹設定相關聯，因為兩種規則可能會衝突。



</div>

您可以使用下列任何一種方法建立或修改轉譯規則：

  - 您可以使用 **組建轉譯規則** 工具，指定起始位數、長度、要移除的位數和要加入的數位的值，然後讓 Lync Server 控制台產生對應的符合模式和轉譯規則。

  - 手動撰寫規則運算式來定義符合模式和轉譯規則。

<div>


> [!NOTE]  
> 如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> 。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中使用組建轉譯規則工具建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [在 Lync Server 2013 中手動建立或修改轉譯規則](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的呼叫者識別碼簡報](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

