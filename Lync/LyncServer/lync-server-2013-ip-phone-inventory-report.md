---
title: Lync Server 2013： IP 電話清查報告
description: Lync Server 2013： IP 電話清查報告。
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
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575019"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Lync Server 2013 中的 IP 電話清查報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-12_

IP 電話清查報告會報告您組織中目前使用之 IP 電話的相關資訊。 IP 清查報告提供在指定報告期間實際使用的 IP 電話詳細清單。 除了其他事項之外，此報告還可讓系統管理員知道是否仍在使用任何舊的過期電話，而這些電話是否仍在使用中;此外，它也可以警示系統管理員，因為組織中有很少使用的電話很昂貴。 當購買新的電話或重新發佈現有的電話時，該類型的資訊可能非常寶貴。  (例如，很少使用他或她的昂貴電話的使用者，可能要求您將電話換用使用他或她之電話的使用者頻率較高。 ) 

請注意，此報告在用來做為真正的庫存報告時，會有一些限制。 一方面，IP 電話報告只會列出在指定期間內登入 Lync Server 的所有電話，並依上次登入時間排序。 如果電話沒有在指定的時間期間登入，則不會在庫存報告中列出。 ，包括在啟動期間之前登入的電話，而且在指定的時間間隔內仍會登入。 例如，假設您想要查看2012年7月的所有電話清點。 假設您也可以在2012年6月30日登入 Lync Server，並在7月1日之後仍登入。 這些電話在7月1日的庫存報告上不會顯示。

此外，請務必注意，庫存報告可以包含您的組織不再使用的電話。 例如，假設您在2012年7月1日在系統上登入的 Fabrikam 電話數目。5天之後您的組織會擺脫所有的 Fabrikam 電話，並以新的 Contoso 模型取代。 Fabrikam 電話仍會出現在「清查」報告上，因為它們是在七月期間登入系統。

此外，IP 電話清查報告不會報告不同電話類型的摘要總數。 例如，假設您有 105 Polycom CX600 電話。 報告不會告訴您，您有105以上的電話;相反地，您只會看到 Polycom Cx600 的105個別專案。 Polycom Cx600 的105專案的唯一方法，就是手動統計每個專案。

<div>


> [!WARNING]  
> 或者，匯出資料，並使用 Microsoft Excel 或 Windows PowerShell 為您進行計算。



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>存取 IP 電話清查報告

IP 電話清查報告可從監控報告的首頁進行存取。 如果您按一下 [使用者 URI] 度量，您可以存取該使用者的使用者活動報告。 按一下對等通話的最後一個活動度量會帶您前往 Peer-to-Peer 會話詳細資料包告。按一下會議的相同公制會帶您前往會議詳細資料包告。

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>IP 電話清查報告的最佳用法

如果您只對一種特殊電話的使用資訊感興趣 (例如，「使用 Polycom CX600 電話的使用者頻率為何？」。) 您可以透過篩選該特定類型的電話，直接從 IP 電話清查報告取得資訊。 不過，如果您想要所有電話的摘要資訊 (多少人使用的是 Polycom CX600、使用 LG-Nortel IP8540 的數目，等等。 ) 之後，您將需要匯出資料，並使用另一個應用程式 (例如 Windows PowerShell) 來執行該類型的分析。 例如，假設您會將資料匯出到逗號分隔值檔案 (C： \\ 資料 \\ IP \_ 電話 \_ 清點 \_Report.csv) 。 在這種情況下，您可以使用這兩個命令，提供您所有電話的摘要資料：

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

同樣地，這兩個命令會告訴您登入系統的電話，但永不實際用來撥打電話 (最後一個活動度量值為空白，表示沒有任何上一個活動) ：

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

針對每個尚未使用的電話，傳回類似以下的資料：

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

使用 IP 電話清查報告的另一種有趣方式是：如果您有 IP 電話的 MAC 位址，只要在 [MAC 位址] 文字方塊中輸入該位址，即可找出最近使用該電話的使用者。 然後，[IP 電話清點] 報告會向 (報告) 使用者上次登入該電話之使用者的 SIP 位址的其他事項。 或者，您也可以在 [使用者 URI 前置詞] 方塊中輸入使用者 SIP 位址 (，) 以找出該使用者已使用的所有電話。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。 例如，IP 電話清查可讓您只查看特定公司製造的電話，甚至只查看這些電話的特定版本。 您也可以選擇資料的分組方式。 在此情況下，登記會依小時、日、周或月進行分組。

下表列出您可以搭配 IP 電話清查報告使用的篩選器。

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
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>7/7/2012</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>7/3/2012</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>製造商</strong></p></td>
<td><p>製造 IP 電話的公司名稱。 根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬體版本</strong></p></td>
<td><p>IP 電話的版本號碼;使用製造商和硬體版本篩選器，您可以唯一識別特定類型的電話。 根據資料庫中目前的 IP 電話，此篩選器的值會自動填入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用者代理程式</strong></p></td>
<td><p>IP 電話所使用之軟體的識別碼。 根據目前資料庫中的 IP 電話，此篩選器的值會自動填入。</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC 位址</strong></p></td>
<td><p>IP 電話上網路介面的唯一識別碼。 Media Access Control (MAC) 位址通常是在電話製造時，且硬接線到裝置硬體時進行指派。</p>
<p>若要搜尋與特定 MAC 位址相關的記錄，只要輸入該位址即可。 例如：</p>
<p>00-08-16-16-48</p>
<p>您必須輸入完整的位址。 部分位址 (例如，00-08-5D) 不會傳回任何資料。</p></td>
</tr>
<tr class="odd">
<td><p><strong>天數之前的最後一個活動</strong></p></td>
<td><p>選取下列其中一個值：</p>
<ul>
<li><p>一切</p></li>
<li><p>10 </p></li>
<li><p>共</p></li>
<li><p>大約</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>前一天的登出時間</strong></p></td>
<td><p>選取下列其中一個值：</p>
<ul>
<li><p>一切</p></li>
<li><p>10 </p></li>
<li><p>共</p></li>
<li><p>大約</p></li>
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

## <a name="metrics"></a>指標

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
<td><p>製造 IP 電話的公司名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>硬體版本</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話的版本號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC 位址</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話上網路介面的唯一識別碼。 MAC 位址通常是在電話製造時所指派，而且會硬接線至裝置硬體。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者 URI</strong></p></td>
<td><p>是</p></td>
<td><p>使用 IP 電話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>使用者代理程式</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話所使用之軟體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>上次登入時間</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話上次登入 Lync Server 的日期和時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>上次登出時間</strong></p></td>
<td><p>是</p></td>
<td><p>IP 電話上次從 Lync Server 登出的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>最後一個活動</strong></p></td>
<td><p>是</p></td>
<td><p>上次使用 IP 電話的日期和時間。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

