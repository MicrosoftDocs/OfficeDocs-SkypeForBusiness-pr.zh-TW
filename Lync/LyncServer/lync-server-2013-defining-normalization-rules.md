---
title: Lync Server 2013：定義正常化規則
description: Lync Server 2013：定義正常化規則。
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
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542039"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中定義正常化規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

Lync Server 2013 正規化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉譯為 e.164 格式;換句話說，正規化規則可讓使用者撥打的電話號碼，並將該號碼轉換成 Lync Server 內部所用的格式。 每個撥號對應表都必須被指派一或多個正常化規則。

如需正規化規則的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md) 。

如需如何撰寫正則運算式的詳細資訊，請參閱 .NET Framework 正則運算式 at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。

您可以使用下列其中一種方法來定義或編輯正規化規則：

  - 使用 [ **建立正規化規則** ] 工具來指定起始數位、長度、要移除的數位和要加入的數位的值，然後讓 Lync Server 控制台產生對應的符合模式和轉譯規則。

  - 手動撰寫規則運算式來定義符合模式和轉譯規則。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中使用組建標準化規則來建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立撥號對應表](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

