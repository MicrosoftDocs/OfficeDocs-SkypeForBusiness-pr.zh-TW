---
title: Lync Server 2013： 轉譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1576b9c0c7286150c62f1491960bf9beef5d700
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 中的轉譯規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-05_

Lync Server 2013 Enterprise Voice 需要所有撥號對應表字串被正規化為 E.164 格式目的執行反向號碼查閱 (RNL)。 在 Microsoft Lync Server 2010 中，只會支援受話號碼轉譯規則。 新增 Microsoft Lync Server 2013 中，在轉譯規則也支援呼叫數字。 *「主幹對等」*(亦即相關聯的閘道、專用交換機 (PBX) 或 SIP 主幹) 可能要求號碼必須為本地撥號格式。 若要將號碼從 E.164 格式轉譯為本地撥號格式，則可以先定義一或多個轉譯規則來操作要求 URI，再將其路由傳送至主幹對等。 例如，您可以撰寫轉譯規則，移除撥號字串開頭的 +44，並改為 0144。

在伺服器上執行輸出路由轉譯，則可以減少在每個個別主幹對等上的設定需求，以將電話號碼轉譯為區域撥號格式。 當您規劃的閘道]，以及多少閘道、 要關聯的特定的中繼伺服器叢集，它可能會很有用群組主幹對等類似區域撥號需求。 如此，可減少所需的轉譯規則數目以及寫入它們所需的時間。

<div>


> [!IMPORTANT]  
> 建立一或多個轉譯規則關聯與 Enterprise Voice 主幹組態應改成主幹對等上設定轉譯規則。 不會關聯轉譯規則與 Enterprise Voice 主幹組態如果您已在主幹對等上設定轉譯規則因為這兩個規則可能會產生衝突。



</div>

<div>

## <a name="example-translation-rules"></a>範例轉譯規則

下列轉譯規則範例顯示如何在伺服器上開發規則，以將號碼從 E.164 格式轉譯為主幹對等的區域格式。

如需如何實作轉譯規則的詳細資訊，請參閱部署文件中的[Lync Server 2013 中的定義轉譯規則](lync-server-2013-defining-translation-rules.md)。


<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>開頭數字</th>
<th>長度</th>
<th>要移除的數字</th>
<th>要加入的數字</th>
<th>比對模式</th>
<th>Translation</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>美國的傳統長途撥號</p>
<p>(除去 ‘+’)</p></td>
<td><p>+ 1</p></td>
<td><p>剛好 12 個</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+(1\d{10}) $</p></td>
<td><p>$ 1</p></td>
<td><p>+14255551010 變成 14255551010</p></td>
</tr>
<tr class="even">
<td><p>美國國際長途撥號</p>
<p>(除去 ‘+’ 並加上 011)</p></td>
<td><p>+</p></td>
<td><p>至少 11 個</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+(\d{9}\d+)$</p></td>
<td><p>011$ 1</p></td>
<td><p>+441235551010 變成 011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

