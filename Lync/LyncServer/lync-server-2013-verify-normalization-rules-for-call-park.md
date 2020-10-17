---
title: Lync Server 2013：驗證通話駐留的正規化規則
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
ms.openlocfilehash: 627832870de3a8306912d07134bb92caeee3076e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518620"
---
# <a name="verify-normalization-rules-for-call-park-in-lync-server-2013"></a>在 Lync Server 2013 中驗證通話駐留的正規化規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-11_

通話駐留軌道不得正規化。 請檢查您的撥號對應表，確定您的軌道編號不會正規化。 如果您必須建立額外的正規化規則，以防止您的軌道正規化，請遵循在 [Lync Server 2013 中建立撥號](lync-server-2013-create-a-dial-plan.md) 對應表中的程式來定義新的正規化規則，如此一來 **相符模式** ，就能識別軌道範圍和 **轉譯模式** 為 **$1**。 例如，如果您的通話駐留軌道範圍是7000–7999， **要比對的模式** 是 **^ (7 \\ d {3}) $** 和 **轉譯模式** 是 **$1**。

<div>


> [!IMPORTANT]  
> 請確定撥號對應表中的預設正規化規則不包含 <STRONG>^ ( \d * ) </STRONG>。 否則，您的通話駐留正規化規則永不會執行。



</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中建立撥號對應表](lync-server-2013-create-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

