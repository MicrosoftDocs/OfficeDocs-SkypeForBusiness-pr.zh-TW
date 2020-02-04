---
title: Lync Server 2013：定義正規化規則
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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a>在 Lync Server 2013 中定義正規化規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-04-22_

Lync Server 2013 正常化規則使用 .NET Framework 正則運算式，將撥打的電話號碼轉換為164格式;換句話說，正常化規則會採用使用者所撥的電話號碼，並將該號碼轉換為 Lync Server 在內部使用的格式。 每個撥號對應表都必須被指派一或多個正規化規則。

如需正常化規則的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。

如需如何撰寫正則運算式的詳細資料，請參閱 ".NET Framework 正[http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)則運算式"。

您可以使用下列其中一種方法來定義或編輯正常化規則：

  - 使用 [**組建正常化規則**] 工具來指定起始位數、長度、要移除的數位和要加上的數位的值，然後讓 Lync Server [控制台] 為您產生對應的相符模式與翻譯規則。

  - 手動寫入正則運算式，以定義相符的模式與翻譯規則。

<div>

## <a name="in-this-section"></a>本節內容

  - [在 Lync Server 2013 中使用組建正常化規則來建立或修改正常化規則](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [在 Lync Server 2013 中手動建立或修改正規化規則](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中建立撥號方案](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改撥號對應表](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

