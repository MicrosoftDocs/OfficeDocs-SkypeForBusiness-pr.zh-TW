---
title: Lync Server 2013：撥號對應表和正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6195baf2cdff30cad74dfddc31337d9d429c5d8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520016"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 的撥號對應表和正常化規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

撥號對應表是一個具名的正規化規則集，可將具名位置、個別使用者或連絡人物件的電話號碼轉譯成單一標準 (E.164) 格式，以便進行電話授權和電話路由傳送。

正規化規則會針對每個指定位置、使用者或連絡人物件，定義要如何路由傳送以各種格式表達的電話號碼。 視其撥號位置和進行通話的人員或連絡人物件而定，相同的撥號字串可能會以不同的方式轉譯和轉譯。

<div>

## <a name="dial-plan-scope"></a>撥號對應表範圍

撥號對應表的 *範圍* 決定可以套用撥號對應表的階層層級。 在 Lync Server 中，使用者可以指派特定的每一使用者撥號對應表。 若未指派使用者撥號對應表，則會套用註冊機構集區撥號對應表。 如果沒有註冊機構集區撥號對應表，則會套用網站撥號對應表。 最後，如果沒有其他適用于使用者的撥號對應表，則會套用全域撥號對應表。

用戶端透過在使用者登入 Lync Server 時所提供的頻帶內布建設定，取得撥號對應表的範圍層級。 身為系統管理員，您可以使用 Lync Server 控制台管理及指派撥號對應表的範圍層級。

<div>


> [!NOTE]  
> 服務層級公用交換電話網路 (PSTN) 閘道撥號對應表會套用至特定閘道上的來電。



</div>

撥號對應表範圍層級的定義如下：

  - **使用者撥號** 對應表：可以指派給個別的使用者、群組或連絡人物件。 當接到電話內容設定為使用者預設值時，語音應用程式可以查閱個別使用者撥號對應表。 出於指派撥號對應表的目的，連絡人物件會被視為個別使用者。

  - **集區撥號** 對應表：可在拓撲中的任何 PSTN 閘道或註冊機構的服務層級建立。 若要定義集區撥號對應表，您必須指定撥號對應表所套用的特定服務 (PSTN 閘道或註冊機集區) 。

  - **網站撥號** 對應表：可以針對整個網站建立，但對於指派集區撥號對應表或使用者撥號對應表的任何使用者、群組或連絡人物件除外。 若要定義網站撥號對應表，您必須指定要套用撥號對應表的網站。

  - **全域撥號** 對應表：隨產品安裝的預設撥號對應表。 您可以編輯全域撥號對應表，但無法加以刪除。 此撥號對應表適用于部署中的所有 Enterprise Voice 使用者、群組和連絡人物件，除非您設定和指派具有更特定範圍的撥號對應表。

</div>

<div>

## <a name="planning-for-dial-plans"></a>規劃撥號對應表

若要規劃撥號對應表，請遵循下列步驟：

  - 列出您的組織擁有 office 的所有地區設定。
    
    清單必須是最新和完整的。 當公司組織演變時，將需要進行修訂。 在具有眾多小型分公司的大型跨國公司中，這可能是一項耗時的工作。

  - 識別每個網站的有效號碼模式。
    
    規劃撥號對應表的最費時的部分是識別每個網站的有效號碼模式。 在某些情況下，您可以將您為一個撥號對應表編寫的正規化規則複製到其他撥號對應表，尤其是在對應的網站位於相同的國家/地區或大陸時。 在其他情況下，對一個撥號對應表中的數位所做的小變更，可能足以在其他撥號對應表中使用它們。

  - 開發用於命名撥號對應表的全組織模式。
    
    採用標準命名架構可確保整個組織的一致性，並使維護和更新變得更容易。

  - 決定單一位置是否需要多個撥號對應表。
    
    如果您的組織跨多個位置維護單一撥號對應表，您可能仍然需要針對從專用交換機 (PBX) 進行遷移的 Enterprise Voice 使用者建立個別的撥號對應表，且必須保留現有的副檔名。

  - 決定是否需要每個使用者的撥號對應表。 例如，如果您在分支網站上有使用者向中央網站註冊，或是您有在 Survivable Branch 裝置上註冊的使用者，則可以針對使用個別使用者撥號對應表及正規化規則的使用者考慮特殊的撥號案例。 如需詳細資訊，請參閱 [Lync Server 2013 的分支網站恢復需求](lync-server-2013-branch-site-resiliency-requirements.md)。

  - 依照本主題先前所述，確定撥號對應表範圍 () 。

若要建立撥號對應表，您可以在必要時使用 Lync Server 控制台或 Lync Server 管理命令介面來指定下欄欄位中的值。

<div>

## <a name="name-and-simple-name"></a>名稱和簡易名稱

針對使用者撥號對應表，您應該指定識別撥號對應表所指派之使用者、群組或連絡人物件的描述性名稱。 針對網站撥號對應表，[名稱] 欄位會預先填入網站名稱，而且無法變更。 針對集區撥號對應表，[名稱] 欄位會預先填入 PSTN 閘道或前端集區完整功能變數名稱 (FQDN) 且無法變更。

撥號對應表的 *簡易名稱* 會預先填入一個衍生自撥號對應表名稱的字串。 [簡易名稱] 欄位是可編輯的，可讓您為撥號對應表建立更具描述性的命名慣例。 [ *簡易名稱* ] 值不能是空的，而且必須是唯一的。 最佳作法是針對整個組織制定命名慣例，然後在所有網站和使用者中統一使用此慣例。

</div>

<div>

## <a name="description"></a>描述

建議您輸入適用于對應撥號對應表之地理位置的一般識別名稱。 例如，如果撥號對應表名稱是 London.Contoso.com，則建議的描述將是倫敦。

</div>

<div>

## <a name="dial-in-conferencing-region"></a>電話撥入式會議區域

若要部署電話撥入式會議，您必須指定電話撥入式會議區域，以將電話撥入式會議存取號碼與撥號對應表產生關聯。

</div>

<div>

## <a name="external-access-prefix"></a>外部存取前置詞

您可以指定最多四個字元的外部存取前置詞 (\# 、 \* 和 0-9) 如果使用者需要撥打一或多個其他前導數位 (例如，9) 以取得外部行。

<div>


> [!NOTE]  
> 如果您指定了外部存取前置詞，則不需要建立額外的正規化規則來容納前置詞。



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>正規化規則

正規化規則會定義以不同格式表示的電話號碼如何路由傳送至指定的位置。 您可以根據撥號的地區設定，以不同方式轉譯和轉譯相同的數位字串。 您可以使用正規化規則進行呼叫路由，因為使用者在其連絡人清單中輸入電話號碼時可以使用各種格式。

將使用者提供的電話號碼正常化，可提供一致的格式，可協助下列工作：

  - 將撥打的號碼與預定收件者的 SIP-URI 相符。

  - 將撥號授權規則套用至呼叫方。

下列號碼欄位是您的正規化規則可能需要考慮的欄位：

  - 撥號對應表

  - 國碼

  - 區功能變數代碼

  - 延伸長度

  - 網站前置詞

<div>

## <a name="creating-normalization-rules"></a>建立正常化規則

正規化規則使用 .NET Framework 正則運算式，指定伺服器用以將撥號字串轉譯為 e.164 格式，以執行反向號碼查閱的數位匹配模式。 您可以在 Lync Server 控制台中建立正規化規則，方法是手動輸入運算式，或輸入要比對的撥號字串的開始位數和長度，並讓 Lync Server 控制台為您產生對應的正則運算式。 無論是哪一種方式，當您完成時，您都可以輸入測試號碼，以驗證正規化規則如預期的方式運作。

如需使用 .NET Framework 正則運算式的詳細資訊，請參閱 at .NET Framework 正則運算式 [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) 。

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>正常化規則範例

下表顯示以 .NET Framework 正則運算式形式寫入的範例正常化規則。 範例只是範例，並不是建立您自己的正規化規則的規範性參考。

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>表 1. 使用 .NET Framework 正則運算式的正常化規則

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>規則名稱</th>
<th>描述</th>
<th>號碼模式</th>
<th>Translation</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>轉譯4位數的分機號碼</p></td>
<td><p>^ ( \d {4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>0100會轉譯成 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>轉譯5位數的分機號碼</p></td>
<td><p>^ 5 ( \d {4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>50100會轉譯成 + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>將7位數號碼轉譯為 Redmond 當地號碼</p></td>
<td><p>^ ( \d {7}) $</p></td>
<td><p>+ 1425 $ 1</p></td>
<td><p>5550100會轉譯成 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>將7位數號碼轉譯為達拉斯當地號碼</p></td>
<td><p>^ ( \d {7}) $</p></td>
<td><p>+ 1972 $ 1</p></td>
<td><p>5550100會轉譯成 + 19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>翻譯美國的10位數數位</p></td>
<td><p>^ ( \d {10}) $</p></td>
<td><p>+ 1 $ 1</p></td>
<td><p>2065550100會轉譯成 + 12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>轉譯美國具有長途首碼的號碼</p></td>
<td><p>^ 1 ( \d {10}) $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100會轉譯成 + 2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>轉譯美國國際首碼的號碼</p></td>
<td><p>^ 011 ( \d * ) $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100會轉譯成 + 91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>轉譯0到 Redmond 運算子</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0會轉譯成 + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>轉譯具有) 網路首碼 (6 和 Redmond 網站碼 (222 的數位) </p></td>
<td><p>^ 6222 ( \d {4}) $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>62220100會轉譯成 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>轉譯具有) 網路首碼的號碼 (6 和 NY 網站碼 (333) </p></td>
<td><p>^ 6333 ( \d {4}) $</p></td>
<td><p>+ 1202555 $ 1</p></td>
<td><p>63330100會轉譯成 + 12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>轉譯具有) 網路首碼 (6 和達拉斯 site code (444 的數位) </p></td>
<td><p>^ 6444 ( \d {4}) $</p></td>
<td><p>+ 1972555 $ 1</p></td>
<td><p>64440100會轉譯成 + 19725550100</p></td>
</tr>
</tbody>
</table>


下表根據上表所示的正規化規則，顯示 Redmond （華盛頓）州的範例撥號對應表。

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>表 2. 以表1顯示的正規化規則為依據的 Redmond 撥號對應表

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>Redmond forestFQDN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtension</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingRedmond</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
</tr>
<tr class="even">
<td><p>IntlCallingUS</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 上表所顯示的正規化規則名稱不會包含空格，但這是選擇性的考慮。 例如，表格中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數擴充"，而且仍然有效。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

