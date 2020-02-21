---
title: Lync Server 2013： 使用者註冊報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd7ff808b766d7366e39595a46d1a2d7dfb75996
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Lync Server 2013 中的使用者註冊報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-21_

使用者註冊報告提供的使用者登入活動的概觀，最特別是在指定的時間期間內 （每小時、 每天、 每週、 每月） 登入 Microsoft Lync Server 2013 的使用者數目的相關資訊。 請記住，報告只會告訴您登入的人數。 它不會告訴您*哪些*人的身分登入。 使用 Lync Server 2013 相關的特定使用者 （且哪些項目不） 監控報告不會提供資訊。 不過，您可以使用使用者活動報告來取得使用者資訊大約估計。

使用者註冊報告在提供使用者登入的相關資訊時，會提出兩項重要差異。 首先，其會將登入分為兩種主要類別：內部登入及外部登入。 內部登入代表從組織防火牆內部登入的使用者 (也就是連線到公司網路時)。 外部登入代表從登入透過 Edge Server （例如，從咖算作外部登入網際網路登入的使用者） 防火牆外的使用者。 如果您需要知道您有多少使用者從防火牆外部登入，使用者註冊報告可以提供您此資訊。

此外，使用者註冊報告會記錄在指定的時段內，有多少「作用中」** 使用者存在。 作用中的使用者是時間的參與立即訊息 (IM) 工作階段的使用者參與 Lync 會議、 進行或收到的電話，或否則在該期間內使用 Lync Server。 這不同於登入但實際上從未使用系統的使用者。

<div>

## <a name="accessing-the-user-registration-report"></a>存取使用者註冊報告

您只能從監視報告首頁存取使用者註冊報告。使用者註冊報告沒有連結至任何其他報告。

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>善加利用使用者註冊報告

部署 Lync Server 其中經常要求後的問題是： 如何知道我的使用者是否實際上使用這項新技術？ 雖然在這方面有些許限制，但是使用者註冊報告可以協助您回答這個問題。 若要決定使用者要使用 Lync Server，您需要執行下列兩件事。 首先，從使用者註冊報告取得唯一登入使用者計量值。 此值會告訴您如何許多不同的個人登入 Lync Server。

相較之下，登入總數公制顯示多少人登入 Lync Server 的總時間。 例如，假設為 Ken myer 的使用者登入 Lync Server 五個不同的時間，在一天。 在此情況下，就總登入計量而言，Ken Myer 會計為五個不同的登入工作階段，但是就唯一登入使用者計量而言，只有一位登入使用者。 同樣地，一位使用者從多個裝置或多個位置登入並無不同。 例如，使用者可以使用登入其桌面的電腦，其膝上型電腦，而她可以有自動登入 Lync Server IP 電話。 在此範例中，共有一位唯一使用者登入三次。

為進一步說明總登入及唯一登入之間的差異，請想想下表中特定時段內的登入。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者</th>
<th>登入時間</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:45 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


請注意，總共有五次登入；不過，只有兩位唯一登入使用者：Ken Myer (登入三次) 及 Pilar Ackerman (登入兩次)。這就是登入與唯一登入使用者之間的差異。

除了瞭解有多少的唯一登入，您需要知道的已啟用 Lync Server 的使用者總數。 值可以被擷取的開啟 Lync Server 2013 管理命令介面，並執行下列 Windows PowerShell 命令：

    (Get-CsUser).Count

如果上述命令會傳回的值為 1236，而唯一登入使用者計量傳回的平均值為 667，建議，有點超過一半的使用者啟用 Lync 實際登入系統 (也就是 667 除以 1236 每日也就是大約為 54%)。

<div>


> [!WARNING]  
> 請記住，登入度量資訊記錄在指定的時間期間實際登入的使用者。 它們不追蹤的已登入系統的使用者。 例如，如果您唯一登入使用者計量顯示 667 登入，且您有 1,236 的使用者的建議，您大約一半的使用者登入系統。 不過，假設 300 位使用者已登入系統次您開始檢查登入資料。 這表示您真的開幾乎 1000 位使用者登入 Lync Server，這就是，近 80%的使用者已登入。



</div>

您也應該要比較唯一登入使用者值與唯一作用中使用者計量值。 唯一作用中使用者] 計量會告訴您單獨使用者人數實際上使用 Lync Server： 他們進行的通話、 他們加入 Lync 會議中，或他們參與的 IM 工作階段。 這是很有用的資訊，因為 Microsoft Lync 2013 可以設定設為自動啟動 [每次使用者啟動視窗。 因此，您可能有大量的自動登入 Lync 當他們登入 Windows 每一天，但然後從未實際在該時間期間內使用 Lync Server 的使用者。

唯一作用中使用者] 計量也會提供更有意義的資料，其中使用者通常不需登關閉 Windows 一天結尾處的組織中。 相反地，他們只要鎖定他們的電腦，並保留 Windows 和執行 Lync。 在這類情況下，您可能結尾很少的登入每日因為您的使用者登入數天之內及永遠不會關閉登入。 不過，唯一作用中使用者會告訴您是否使用者目前正在使用 Lync 或其他的 Lync Server 用戶端。

</div>

<div>

## <a name="filters"></a>篩選

篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。 例如，使用者註冊報告可讓您檢視所有登錄器集區與 Edge Server 的資料，或檢視個別的集區的資料。 您也可以選擇資料的分組方式。 在這種情況下，註冊會按照小時、日、星期或月來分組。

下表列出您可以搭配使用者註冊報告的篩選。

### <a name="user-registration-report-filters"></a>使用者註冊報告篩選

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
<td><p>時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</p>
<p>2012/7/7</p>
<p>若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</p>
<p>2012/7/3</p>
<p>星期永遠是從星期日開始星期六結束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。請選取下列其中一項：</p>
<ul>
<li><p>每小時 (最多可以顯示 25 個小時)</p></li>
<li><p>每日 (最多可以顯示 31 天)</p></li>
<li><p>每週 (最多可以顯示 12 週)</p></li>
<li><p>每月 (最多可以顯示 12 個月)</p></li>
</ul>
<p>若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。 您可以選取個別的集區，或是選擇 [全部]<strong></strong>，以檢視所有集區的資料。 此下拉式清單會自動將資料庫內的資料填入。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>計量

下表列出使用者註冊報告提供的資訊。

### <a name="user-registration-report-metrics"></a>使用者註冊報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>每小時</strong></p>
<p><strong>每日</strong></p>
<p><strong>每週</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>在篩選工具列上顯示您所選取的時間間隔。在適用的情況下，只要按一下所指定的時間間隔，即可檢視該間隔的詳細資訊。例如，您若是使用 [每日] 間隔，然後按一下 7/7/2012，將會顯示該日之使用者註冊活動的每小時明細。</p></td>
</tr>
<tr class="even">
<td><p><strong>登入總數</strong></p></td>
<td><p>否</p></td>
<td><p>登入工作階段總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>內部登入</strong></p></td>
<td><p>否</p></td>
<td><p>內部網路內的登入總數。</p></td>
</tr>
<tr class="even">
<td><p><strong>外部登入</strong></p></td>
<td><p>否</p></td>
<td><p>使用 Edge Server，來自內部網路以外的登入總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一登入使用者</strong></p></td>
<td><p>否</p></td>
<td><p>至少有一次登入工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一作用中使用者</strong></p></td>
<td><p>否</p></td>
<td><p>參與對等或會議工作階段的使用者總數。若使用者擁有多個登入工作階段，仍會計為一個使用者；和僅有單一登入工作階段的人員相同。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

