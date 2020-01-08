---
title: Lync Server 2013：翻譯規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Translation rules
ms:assetid: 6e067bd4-4931-4385-81ac-2acae45a16d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398520(v=OCS.15)
ms:contentKeyID: 48184460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22b6fbacf068f6a1a388a968989259afec81d17a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="translation-rules-in-lync-server-2013"></a>Lync Server 2013 中的翻譯規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-05_

Lync Server 2013 企業語音要求將所有撥號字串標準化為 E.i 格式，以執行反向數位查閱（RNL）。 在 Microsoft Lync Server 2010 中，只能針對呼叫的號碼支援翻譯規則。 Microsoft Lync Server 2013 中的新功能在通話編號中也支援翻譯規則。 *幹線對等*（也就是關聯的閘道、私人分支 EXCHANGE （PBX）或 SIP 幹線）可能需要使用本機撥號格式。 若要將數位（164格式）轉換成本機撥號格式，您可以定義一或多個翻譯規則，在將要求 URI 傳送到幹線對等前，先進行處理。 例如，您可以撰寫轉譯規則，從撥號字串的開頭移除 +44 並替換成 0144。

透過在伺服器上執行輸出路由轉換，您可以減少每個個別中繼對等的設定需求，以將電話號碼轉譯為本機撥號格式。 當您規劃哪些閘道以及要與特定的中繼伺服器群集建立關聯的閘道數時，可能會對幹線對等進行類似的本機撥號需求群組有所説明。 這樣可以減少所需翻譯規則的數目，以及撰寫它們所需的時間。

<div>


> [!IMPORTANT]  
> 將一或多個翻譯規則與企業語音幹線設定建立關聯，就應該使用此替代方法，以在幹線對等上設定翻譯規則。 如果您已在幹線對等上設定翻譯規則，請不要將翻譯規則與企業語音幹線配置建立關聯，因為這兩個規則可能會衝突。



</div>

<div>

## <a name="example-translation-rules"></a>翻譯規則範例

下列翻譯規則範例會示範如何在伺服器上開發規則，將數位從 E.i 格式轉譯為幹線對等的本機格式。

如需如何實現翻譯規則的詳細資料，請參閱在部署檔中的[Lync Server 2013 定義翻譯規則](lync-server-2013-defining-translation-rules.md)。


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
<th>描述</th>
<th>起始位數</th>
<th>全長</th>
<th>移除的位數</th>
<th>要新增的位數</th>
<th>相符的模式</th>
<th>翻譯</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>美國的傳統長途電話撥號</p>
<p>（去除 "+"）</p></td>
<td><p>+ 1</p></td>
<td><p>恰好12</p></td>
<td><p>1</p></td>
<td><p>0</p></td>
<td><p>^\+（1 \ d{10}） $</p></td>
<td><p>$1</p></td>
<td><p>+ 14255551010 變成14255551010</p></td>
</tr>
<tr class="even">
<td><p>美國國際長途撥號</p>
<p>（去除 "+" 並加上011）</p></td>
<td><p>+</p></td>
<td><p>至少11</p></td>
<td><p>1</p></td>
<td><p>011</p></td>
<td><p>^\+（\d{9}\d +） $</p></td>
<td><p>011 $ 1</p></td>
<td><p>+ 441235551010 變成011441235551010</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

