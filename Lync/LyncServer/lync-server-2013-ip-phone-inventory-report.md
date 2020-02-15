---
title: 'Lync Server 2013: IP 電話清查報告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013 中的 IP 電話清查報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-11-12_

IP 電話清查報告報告目前正在使用您組織中的 IP 電話的相關資訊。 IP 清查報告提供實際期間指定的報表期間內使用的 IP 電話的詳細的清單。 除此之外，這份報告可讓系統管理員知道仍在使用，應被取代; 是否有任何舊的、 過時的電話它也可以有貴組織中的電話，很少使用的事實警示系統管理員。 提到的時間來購買新電話或轉散佈現有的電話時，該類型的資訊十分有用。 （例如，很少使用他/她昂貴的電話的使用者可能會要求來進行更常使用他/她電話的使用者交換電話。）

請注意，這份報告有一些限制對正在作為檔案，則為 true 的清查報告過濾。 第一，IP 電話報告只會列出所有登入 Lync Server 在指定的時間期間，其最後登入時間來排序的電話。 如果電話沒有登入指定的時間期間然後它將不會列在清查報告。 包含之前的時間期間啟動，且已在指定的時間間隔期間仍登入的身分登入的電話。 例如，假設您想要查看所有電話清查 2012 年 7 月。 假設以及數個電話登入 Lync Server 在 2012 年 6 月 30 日，且已截至年 7 月 1st 仍登入。 這些電話不會顯示在清查報告的年 7 月 1st。

務必也請注意，清查報告可能包含您的組織無法再使用的電話。 例如，假設在 2012 年 7 月 1 日; 登入系統的 Fabrikam 電話的數目5 天後您的組織 got 排除所有這些 Fabrikam 電話，並取代較新的 Contoso 模型。 Fabrikam 電話上仍會顯示 「 存貨 」 報告只是因為他們登入系統的年 7 月份期間。

此外，IP 電話清查報告不會報告不同類型的電話摘要合計。 例如，假設您有 105 Polycom CX600 電話。 報表不會告訴您，您有 105 的這些電話;相反地，您只會看到 Polycom Cx600 105 的個別項目。 若要知道有 Polycom Cx600 105 項目的唯一方法是手動計算每個這些項目。

<div>


> [!WARNING]  
> 或者，匯出資料，並使用 Microsoft Excel 或 Windows PowerShell 來執行計算。



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>存取 IP 電話清查報告

從監視報告首頁存取 IP 電話清查報告。 如果您按一下 [使用者 URI] 計量可以存取該使用者的使用者活動報告。 按一下 [上次活動計量的端對端電話將帶您前往端對端工作階段詳細資料報表;按一下該相同的會議計量，將帶您前往會議詳細資料報告。

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 電話清查報告的最佳用法

如果您有興趣只有一種特定電話使用方式資訊 （例如，「 頻率使用者使用 Polycom CX600 電話？ 」） 您可以透過電話該特定類型的篩選直接從 IP 電話清查報告取得該資訊。 不過，如果您想要所有的電話摘要資訊 （多少人正在使用多少使用 LG Nortel IP8540 等 Polycom CX600） 則必須以匯出資料，並執行該類型的使用另一個應用程式 （例如 Windows PowerShell)分析。 例如，假設您將資料匯出成逗點分隔值檔案 (c:\\資料\\IP\_電話\_庫存\_Report.csv)。 在此情況下，您可以使用這兩個命令提供所有的電話摘要資料：

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

該命令將傳回類似下列的資料：

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

同樣地，這兩個命令會告訴您哪些電話登入系統，但從未實際用於撥打電話 （上次活動計量值為空白，表示沒有任何上次活動）：

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

會傳回資料尚未使用每個電話如下：

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

有趣的另一種方式使用 IP 電話清查報告這是： 如果您有您可以找出使用者上次使用該電話只在 MAC 位址] 文字方塊中輸入該地址 IP 電話的 MAC 位址。 IP 電話清查報告會再報告回 （除此之外） 上次登入與該電話之使用者的 SIP 位址。 或者，您可以輸入使用者 （在 [使用者 URI 字首] 方塊中） 的 SIP 位址，以找出所有使用過該使用者的電話。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，IP 電話清查可讓您檢視僅限生產特定的公司或甚至是這些電話的特定版本的電話。 您也可以選擇資料的分組方式。 在此情況下，註冊分組小時、 日、 週或月。

下表列出您可以使用 IP 電話清查報告的篩選器。

### <a name="ip-phone-inventory-report-filters"></a>IP 電話清查報告篩選器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>製造商</strong></p></td>
<td><p>生產該 IP 電話的公司名稱。 此篩選的值會自動填入您根據 IP 電話，而且目前在資料庫中。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬體版本</strong></p></td>
<td><p>IP 電話; 的版本號碼製造商和硬體版本篩選器您可以使用唯一識別特定類型的電話。 此篩選的值會自動填入您根據 IP 電話，而且目前在資料庫中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用者代理程式</strong></p></td>
<td><p>IP 電話所使用的軟體識別碼。 此篩選的值會自動填入您根據目前資料庫中的 IP 電話。</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC 位址</strong></p></td>
<td><p>IP 電話上的網路介面的唯一識別碼。 在電話生產，並且為硬體有線方式於裝置硬體的時間通常指派的媒體存取控制 (MAC) 位址。</p>
<p>若要搜尋記錄屬於特定的 MAC 位址只輸入該地址。 例如：</p>
<p>00-08-5D-16-16-48</p>
<p>您必須輸入完整的地址。 部分的地址 (例如 00-08-5 D) 不會傳回任何資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>天前的最後活動</strong></p></td>
<td><p>選取下列其中一個下列值：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>天數前的最後登出時間</strong></p></td>
<td><p>選取下列其中一個下列值：</p>
<ul>
<li><p>[全部]</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>使用者 URI 字首</strong></p></td>
<td><p>使用 IP 電話之使用者的 SIP 位址。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出 IP 電話清查報告中提供的資訊。

### <a name="ip-phone-inventory-report-metrics"></a>IP 電話清查報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>製造商</strong></p></td>
<td><p>是</p></td>
<td><p>生產該 IP 電話的公司名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬體版本</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話的版本號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC 位址</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話上的網路介面的唯一識別碼。 在電話生產，並且為硬體有線方式於裝置硬體的時間通常指派的 MAC 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者 URI</strong></p></td>
<td><p>是</p></td>
<td><p>使用 IP 電話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話所使用的軟體識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>上次登入時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間 IP 電話上次登入 Lync Server。</p></td>
</tr>
<tr class="odd">
<td><p><strong>上次登出時間</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間 IP 電話上次登出從 Lync Server。</p></td>
</tr>
<tr class="even">
<td><p><strong>上次活動</strong></p></td>
<td><p>是</p></td>
<td><p>日期和時間上次使用 IP 電話。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

