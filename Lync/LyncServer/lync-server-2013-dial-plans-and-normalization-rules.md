---
title: Lync Server 2013：撥號方案與正常化規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a>Lync Server 2013 中的撥號方案和正常化規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-21_

撥號方案是一組命名的正常化規則，可將命名位置、個別使用者或連絡人物件的電話號碼轉換成單一標準（e. 164）格式，以用於手機授權及呼叫路由。

正常化規則定義以各種格式表示的電話號碼如何針對每一個指定的位置、使用者或連絡人物件進行路由。 根據撥號位置，以及進行呼叫的人員或連絡人物件，可能會以不同方式來轉譯和翻譯相同的撥號字串。

<div>

## <a name="dial-plan-scope"></a>撥號計畫範圍

撥號計畫的*範圍*決定您可以套用撥號方案的階層等級。 在 Lync Server 中，使用者可以指派特定的每個使用者撥號方案。 如果未指派使用者撥號方案，則會套用註冊機構池撥號方案。 如果沒有註冊機構池撥號方案，則會套用網站撥號計畫。 最後，如果沒有任何其他適用于使用者的撥號方案，就會套用全域撥號對應方案。

用戶端透過在使用者登入 Lync Server 時所提供的頻帶內提供設定來取得撥號方案範圍層級。 就像管理員一樣，您可以使用 Lync Server [控制台] 管理及指派撥號方案範圍階層。

<div>


> [!NOTE]  
> 服務層級的公用交換電話網絡（PSTN）閘道撥號方案會套用至來自特定閘道的撥入通話。



</div>

撥號規劃範圍階層定義如下：

  - **使用者撥號方案：** 可以指派給個別的使用者、群組或連絡人物件。 當您收到來電時，語音應用程式可以查詢每個使用者的撥號方案，並將手機內容設定為 [使用者預設值]。 出於指派撥號方案的目的，連絡人物件會被視為個別使用者。

  - **池撥號方案：** 可在您拓撲中的任何 PSTN 閘道或註冊機構的服務層級建立。 若要定義池子撥號方案，您必須指定要套用撥號方案之特定服務（PSTN 閘道或註冊機構池）。

  - **網站撥號方案：** 可以針對整個網站建立，除了指派了 [泳池撥號方案] 或 [使用者撥號方案] 的任何使用者、群組或連絡人物件之外。 若要定義網站撥號計畫，您必須指定要套用撥號計畫的網站。

  - **全域撥號方案：** 與產品一起安裝的預設撥號方案。 您可以編輯全域撥號方案，但無法將其刪除。 除非您使用更具體的範圍設定並指派撥號方案，否則此撥號方案會套用至您部署中的所有企業語音使用者、群組和連絡人物件。

</div>

<div>

## <a name="planning-for-dial-plans"></a>規劃撥號方案

若要規劃撥號方案，請遵循下列步驟：

  - 列出貴組織擁有 office 的所有地區設定。
    
    清單必須是最新的，而且是完整的。 隨著公司組織的演變，必須進行修改。 在有眾多小型分支機搆的大型跨國公司公司中，這可能是一個非常耗時的工作。

  - 找出每個網站的有效數字模式。
    
    規劃撥號方案最耗時的部分是識別每個網站的有效數字模式。 在某些情況下，您可以將您針對某個撥號方案所撰寫的正常化規則複製到其他撥號方案，尤其是對應的網站在相同的國家/地區或偶洲中。 在其他情況下，單一撥號方案中的數位變更較小，可能就足以在其他撥號方案中使用它們。

  - 為命名撥號方案開發組織範圍的配置。
    
    採用標準命名配置，可確保整個組織的一致性，並讓維護與更新變得更容易。

  - 決定單一位置是否需要多個撥號方案。
    
    如果您的組織在多個位置維持單一撥號方案，您可能仍需要為從私人分支 exchange （PBX）遷移且需要保留其現有副檔名的企業語音使用者建立一個單獨的撥號方案。

  - 決定是否需要每個使用者的撥號方案。 例如，如果您在已向中央網站註冊的分支網站上有使用者，或者如果您擁有在 Survivable 分支裝置上註冊的使用者，您可以考慮使用每個使用者的撥號方案和正常化規則來進行這類使用者的特殊撥號案例. 如需詳細資訊，請參閱[Lync Server 2013 的分支網站復原需求](lync-server-2013-branch-site-resiliency-requirements.md)。

  - 決定撥號方案範圍（如本主題前面所述）。

若要建立撥號方案，請根據需要使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來指定下欄欄位中的值。

<div>

## <a name="name-and-simple-name"></a>名稱與簡單名稱

針對使用者撥號方案，您應該指定識別撥號計畫將指派之使用者、群組或連絡人物件的描述性名稱。 針對網站撥號方案，[名稱] 欄位會預先填入網站名稱，且無法變更。 針對池撥號方案，[名稱] 欄位會預先填入 PSTN 閘道或前端池的完整功能變數名稱（FQDN），而且無法變更。

使用從撥號方案名稱衍生的字串預先填入撥號計畫*簡單名稱*。 [簡易名稱] 欄位為 [可編輯]，可讓您為撥號方案建立更具描述性的命名慣例。 [*簡易名稱*] 值不能為空白，且必須是唯一的。 最佳做法是為您的整個組織開發一個命名慣例，然後在所有網站和使用者中統一使用這個慣例。

</div>

<div>

## <a name="description"></a>描述

我們建議您輸入所要套用之對應撥號方案之地理位置的通用、可識別名稱。 例如，如果撥號方案名稱是 London.Contoso.com，則建議使用倫敦的描述。

</div>

<div>

## <a name="dial-in-conferencing-region"></a>電話撥入式會議區域

如果您要部署電話撥入式會議，您將需要指定電話撥入式會議區域，以將電話撥入式會議存取號碼與撥號方案建立關聯。

</div>

<div>

## <a name="external-access-prefix"></a>外部存取首碼

如果使用者需要撥一或多個額外的前導數位（\#例如\*，9）來取得外部線路，您可以指定最多四個字元（，和0-9）的外部存取前置詞。

<div>


> [!NOTE]  
> 如果您指定外部存取前置詞，就不需要建立額外的正常化規則來容納該前置詞。



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a>正常化規則

正常化規則定義以各種格式表示的電話號碼如何路由至指定位置。 根據撥號的地區設定，相同的數位字串可能會以不同的方式加以轉譯和翻譯。 需要進行呼叫路由的正常化規則，因為使用者可以在連絡人清單中輸入電話號碼時，使用不同的格式。

正常化使用者提供的電話號碼提供一致的格式，可協助進行下列工作：

  - 將撥入號碼與預期收件者的 SIP URI 相符。

  - 將撥號授權規則套用至呼叫方。

下列數位欄位就是您的正常化規則可能需要考慮的專案：

  - 撥號方案

  - 國家/地區代碼

  - 區功能變數代碼

  - 延伸長度

  - 網站首碼

<div>

## <a name="creating-normalization-rules"></a>建立正常化規則

正常化規則使用 .NET Framework 正則運算式指定數位匹配模式，伺服器將撥號字串轉換為 E. 164 格式，以執行 [反向數位查閱] 的目的。 您可以在 Lync Server 控制台中建立正常化規則，方法是手動輸入運算式，或輸入要相符的撥號字串的起始位數和長度，讓 Lync Server 控制台產生對應的正則運算式。 不論是哪一種方式，當您完成時，您可以輸入測試號碼來驗證正常化規則是否如預期的那樣運作。

如需使用 .NET Framework 正則運算式的詳細資料，請參閱 ".NET Framework [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)正則運算式"。

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a>範例正常化規則

下表顯示已寫入為 .NET Framework 一般運算式的範例正常化規則。 這些範例只是範例，並不代表建立您自己的正常化規則的規範性參考。

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a>資料表 1. 使用 .NET Framework 一般運算式的正常化規則

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
<th>數位模式</th>
<th>翻譯</th>
<th>範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>4digitExtension</p></td>
<td><p>翻譯4位數延伸</p></td>
<td><p>^ （\d{4}） $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>0100已轉譯為 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>5digitExtension</p></td>
<td><p>翻譯5位數延伸</p></td>
<td><p>^ 5 （\d{4}） $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>50100已轉譯為 + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>7digitcallingRedmond</p></td>
<td><p>將7位數的數位轉換成雷德式當地電話號碼</p></td>
<td><p>^ （\d{7}） $</p></td>
<td><p>+ 1425 $ 1</p></td>
<td><p>5550100已轉譯為 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>7digitcallingDallas</p></td>
<td><p>將7位數的數位轉換成達拉斯當地數位</p></td>
<td><p>^ （\d{7}） $</p></td>
<td><p>+ 1972 $ 1</p></td>
<td><p>5550100已轉譯為 + 19725550100</p></td>
</tr>
<tr class="odd">
<td><p>10digitcallingUS</p></td>
<td><p>在美國翻譯10位數的數位</p></td>
<td><p>^ （\d{10}） $</p></td>
<td><p>+ 1 $ 1</p></td>
<td><p>2065550100已轉譯為 + 12065550100</p></td>
</tr>
<tr class="even">
<td><p>LDCallingUS</p></td>
<td><p>在美國轉換含長途的數位</p></td>
<td><p>^ 1 （\d{10}） $</p></td>
<td><p>+ $1</p></td>
<td><p>12145550100已轉譯為 + 2145550100</p></td>
</tr>
<tr class="odd">
<td><p>IntlCallingUS</p></td>
<td><p>在美國翻譯含國際首碼的數位</p></td>
<td><p>^ 011 （\d *） $</p></td>
<td><p>+ $1</p></td>
<td><p>01191445550100已轉譯為 + 91445550100</p></td>
</tr>
<tr class="even">
<td><p>RedmondOperator</p></td>
<td><p>轉譯0到雷德蒙運算子</p></td>
<td><p>^ $0</p></td>
<td><p>+ 14255550100</p></td>
<td><p>0已轉譯為 + 14255550100</p></td>
</tr>
<tr class="odd">
<td><p>RedmondSitePrefix</p></td>
<td><p>使用網路上的前置詞（6）和雷德蒙的網站程式碼（222）轉譯數位</p></td>
<td><p>^ 6222 （\d{4}） $</p></td>
<td><p>+ 1425555 $ 1</p></td>
<td><p>62220100已轉譯為 + 14255550100</p></td>
</tr>
<tr class="even">
<td><p>NYSitePrefix</p></td>
<td><p>使用網路上的前置詞（6）和 NY 網站代碼（333）轉譯數位</p></td>
<td><p>^ 6333 （\d{4}） $</p></td>
<td><p>+ 1202555 $ 1</p></td>
<td><p>63330100已轉譯為 + 12025550100</p></td>
</tr>
<tr class="odd">
<td><p>DallasSitePrefix</p></td>
<td><p>使用網路上的前置詞（6）和達拉斯網站程式碼（444）轉譯數位</p></td>
<td><p>^ 6444 （\d{4}） $</p></td>
<td><p>+ 1972555 $ 1</p></td>
<td><p>64440100已轉譯為 + 19725550100</p></td>
</tr>
</tbody>
</table>


下表說明雷蒙德、華盛頓、英國的範例撥號方案，根據上表所示的正常化規則。

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a>表格2。 以資料表1所示之正常化規則為基礎的雷德蒙式撥號方案

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th>雷德 forestFQDN</th>
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
> 上表中顯示的正常化規則名稱不會包含空格，但這是選擇的考慮。 例如，資料表中的第一個名稱可以是 "5 位數副檔名" 或 "5 位數副檔名"，但仍然有效。



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

