---
title: Lync Server 2013：使用者註冊報告
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
ms.openlocfilehash: 079e6cb96a9401d909be4f459d7bbe7c3f6d4ed6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Lync Server 2013 中的使用者註冊報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

[使用者註冊] 報告提供使用者登入活動的概覽，最重要的是在指定的時間期間（每小時、每天、每週、每月）登入 Microsoft Lync Server 2013 的使用者數目。 請記住，報告只會告訴您有多少人登入。 它不會告知您已登入*的*使用者。 [監視報告] 不會提供哪些特定使用者使用的是 Lync Server 2013 （以及哪些不是）的相關資訊。 不過，您可以使用使用者活動報告來取得使用者資訊的粗略估計。

提供使用者登錄的相關資訊時，[使用者註冊] 報告會繪製兩個重要的差異。 首先，它會將登錄中斷為兩個主要類別：內部登錄和外部登錄。 內部登入代表從貴組織的防火牆內部（也就是連線到公司網路時）的使用者。 [外部登入] 代表從防火牆以外的邊緣伺服器登入的使用者（例如，從網路登入的使用者，不會算作外部登入）。 如果您需要知道有多少使用者是從防火牆外登入，使用者註冊報告就能提供此資訊。

此外，使用者註冊報告會記錄在指定時段內有多少*活動*使用者。 [作用中的使用者] 是在立即訊息（IM）會話中參與的使用者，在這段時間內參與 Lync 會議、撥打或接聽電話，或其他使用 Lync Server。 這與已登入，但實際上並未使用系統的使用者不同。

<div>

## <a name="accessing-the-user-registration-report"></a>存取使用者註冊報告

您只能從 [監控報告] 首頁存取使用者註冊報告。 [使用者註冊報告] 不會連結至任何其他報告。

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>充分運用使用者註冊報告

在您部署 Lync Server 之後，我們通常會問到這個問題：如何知道我的使用者是否真的使用這個新技術？ 雖然在這個方面有一些限制，但使用者註冊報告可以協助您回答這個問題。 若要判斷使用者是否正在使用 Lync Server，您必須執行兩項操作。 首先，從使用者註冊報告取得唯一的登入使用者統計值。 這個值告訴您登入 Lync Server 的不同人有多少。

根據比較，[總登入] 度量單位會顯示有多少人登入 Lync Server 的總時間。 例如，假設 Ken Myer 登入 Lync Server 五個不同時間的一天。 在這種情況下，Ken Myer 會針對總共登入統計數計算出五個獨立的登入會話，但只有一個使用者登入使用者的度量。 同樣地，使用者從多個裝置或多個位置登入，並不常見。 例如，使用者可以使用她的桌上型電腦（她的膝上型電腦）登入，而她可以有可自動登入 Lync Server 的 IP 電話。 在這個範例中，有一個具有三次登錄的唯一使用者。

若要進一步說明總登錄與唯一的登錄之間的差異，請考慮在下表中的特定時段內登錄。


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
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 9:17 AM</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 AM</p></td>
</tr>
<tr class="odd">
<td><p>Pilar 方</p></td>
<td><p>7/7/2012 9:31 AM</p></td>
</tr>
</tbody>
</table>


請注意，總共有五次登錄;不過，只有兩個唯一的登錄使用者： Ken Myer （登入三次的人員）和 Pilar 方（登入兩次）。 這就是登入與唯一登入使用者之間的差異。

除了瞭解唯一輸入的數目之外，您還需要知道已啟用 Lync Server 的使用者總數。 您可以開啟 Lync Server 2013 管理命令介面並執行下列 Windows PowerShell 命令來檢索這個值：

    (Get-CsUser).Count

如果上述命令傳回1236和唯一的登入使用者度量值，則會傳回667的平均值，這表示使用者每天都能讓 Lync 實際登入系統（也就是667除以1236）。，大約是54%。

<div>


> [!WARNING]  
> 請記住，登入度量單位會記錄在指定時段內實際登入的使用者。 它們不會追蹤已登入系統的使用者。 例如，如果您唯一的登入使用者度量會顯示667登入，而您有1236個使用者，這表示您的使用者會登入系統的一半。 不過，假設您在開始檢查登入資料時，已登入系統中的300使用者。 這表示您實際已有近1000的使用者登入 Lync Server，這會代表使用者已登入80% 的使用者。



</div>

您也應該將唯一的登入使用者值與唯一的作用中使用者度量值進行比較。 [唯一作用中的使用者] 指標會告訴您實際使用 Lync Server 的使用者數目有多少（他們已撥打電話）、加入 Lync 會議，或參與 IM 會話。 這是有用的資訊，因為 Microsoft Lync 2013 可以設定為在使用者每次啟動 Windows 時自動啟動。 因此，您可能會有大量的使用者會在每天登入 Windows 時自動登入 Lync，但在該期間不會實際使用 Lync Server。

唯一的作用中使用者規格也會在組織中提供更有意義的資料，而使用者通常不會在一天結束時登入 Windows。 相反地，它們只是鎖定其電腦，並離開 Windows 和 Lync 執行。 在這種情況下，您可能會因為您的使用者在數天前登入，且從未登核，所以每天登錄時間都會稍少。 不過，唯一作用中的使用者會告訴您使用者是否正在使用 Lync 或其他 Lync Server 用戶端。

</div>

<div>

## <a name="filters"></a>濾鏡

篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。 例如，[使用者註冊] 報告可讓您查看所有註冊機構池及邊緣伺服器的資料，或查看個別池的資料。 您也可以選擇分組資料的方式。 在這種情況下，登記會依小時、日、周或月分組。

下表列出可與使用者註冊報告搭配使用的篩選。

### <a name="user-registration-report-filters"></a>使用者註冊報告篩選

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>從</strong></p></td>
<td><p>時間範圍的開始日期和時間。 若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="even">
<td><p><strong>自</strong></p></td>
<td><p>時間範圍的結束日期和時間。 若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。 若要依天查看資料，只需輸入日期：</p>
<p>7/7/2012</p>
<p>若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>周數總是從星期日到星期六執行。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>時間間隔。 選取下列其中一項：</p>
<ul>
<li><p>每小時（最多可顯示25小時）</p></li>
<li><p>每天（最多可以顯示31天）</p></li>
<li><p>每週（最多可以顯示12周）</p></li>
<li><p>每月（最多可以顯示12個月）</p></li>
</ul>
<p>如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數目，則只會顯示最大值數（從開始日期開始）。 例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</p></td>
</tr>
<tr class="even">
<td><p><strong>集區</strong></p></td>
<td><p>註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。 您可以選取個別的池子，或選擇<strong>[all] （[全部]）</strong>來查看所有資源庫的資料。 這個下拉式清單會根據資料庫中的記錄，自動填入給您。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指標

下表列出 [使用者註冊] 報告中提供的資訊。

### <a name="user-registration-report-metrics"></a>使用者註冊報告度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>工資</strong></p>
<p><strong>日常</strong></p>
<p><strong>周更新</strong></p>
<p><strong>次</strong></p></td>
<td><p>否</p></td>
<td><p>指出您在 [篩選] 工具列上選取的時間間隔。 在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。 例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</p></td>
</tr>
<tr class="even">
<td><p><strong>登錄總計</strong></p></td>
<td><p>否</p></td>
<td><p>成功登入會話的總數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>內部登錄</strong></p></td>
<td><p>否</p></td>
<td><p>內部網路中的登錄總數量。</p></td>
</tr>
<tr class="even">
<td><p><strong>外部登錄</strong></p></td>
<td><p>否</p></td>
<td><p>使用 Edge 伺服器從內部網路外部進行的登錄總次數。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一的登入使用者</strong></p></td>
<td><p>否</p></td>
<td><p>至少有一個登入會話的使用者總數。 有多個登入會話的使用者會算作一個使用者，與只有單一登入會話的人一樣。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一的作用中使用者</strong></p></td>
<td><p>否</p></td>
<td><p>參與對等或會議會話的使用者總數。 擁有多個會議的使用者，與只有單一會話的人員相同。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

