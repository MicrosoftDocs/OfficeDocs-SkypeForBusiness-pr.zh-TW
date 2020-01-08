---
title: Lync Server 2013：使用監視報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>在 Lync Server 2013 中使用監視報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

Lync Server 2013 包含一組 Microsoft SQL Server Reporting Services 發佈的標準報告。 這些報表可透過網頁瀏覽器存取，提供使用方式、呼叫診斷資訊和媒體質量資訊，所有這些都是以呼叫詳細資料錄製（CDR）以及儲存在 CDR 和 QoE 資料庫的體驗品質（QoE）記錄為基礎。

若要使用這些報告，您必須在執行 SQL Server 實例的電腦上安裝 [監視報告]。

<div>

## <a name="in-this-section"></a>本節內容

  - [使用 Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   中的 [監視儀表板]，可讓系統管理員快速瞭解其系統健康情況與系統使用量。

  - [Lync server 2013](lync-server-2013-system-usage-reports.md)   中的系統使用量報告可根據 Lync Server 所收集的 CDR 資料，提供系統使用量資訊。

  - [在 Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   中呼叫診斷報告（每位使用者）可提供對點對點與會議會話失敗的每使用者資訊。

  - [在 Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   中呼叫診斷報告，可提供失敗對等與會議會話的摘要資訊與診斷資料。

  - [Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   中的媒體質量診斷報告提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。

</div>

<div>

## <a name="locating-records"></a>尋找記錄

監視報告只會在任何時間顯示畫面上有限數量的記錄。 顯示在螢幕上的實際記錄數會依報表而有所不同。 若要查看目前未顯示在螢幕上的記錄，您可以使用 [標準前向] 和 [向後] 控制（可在每個報表的工具列上找到），讓您可以分頁流覽資料。 您也可以快速跳至資料集的第一頁或最後一頁。

除了使用向前和向後控制項之外，您也可以直接在 [**目前頁面**] 方塊中輸入頁碼，然後按 enter 鍵，跳至資料集中的任何頁面。

除了提供頁面流覽資料的功能之外，每個報告也包含尋找記錄的有限能力。 若要尋找以特定值為基礎的記錄，請在 [**尋找**] 方塊中輸入該值，然後按一下 [**尋找**]。 報告會開始搜尋資料，並停止在您在 [**尋找**] 方塊中輸入之值的第一個實例。 若要尋找符合搜尋準則的下一筆記錄，請按 **[下一步]**。

如所述，監視報告只提供最基本的搜尋功能。 例如，您無法指定應該在哪個欄位中找到值。 [搜尋] 機制會自動在每一筆記錄的每個欄位中搜尋相符的值。 您無法在搜尋中使用萬用字元，且所有搜尋都會尋找部分值。 如此一來，如果您搜尋111，搜尋會傳回值111，以及在該欄位內任何位置都包含 value 3112 的值11100、811、111、611A5B 及任何其他欄位。

每個報告都設定為顯示一組預設的記錄。 例如，根據預設，[使用者註冊] 報告會顯示上周的使用者註冊活動。 在某些情況下，這可能會導致不會傳回任何記錄的報表。 在這種情況下，這表示上周不會發生任何使用者註冊。 如果您看到「沒有結果符合報表篩選」的訊息，請嘗試變更篩選值（例如，將時段變更為 [上個月]，而非上周），然後重新執行查詢。 如需詳細資訊，請參閱本主題稍後的「篩選資料」一節。

</div>

<div>

## <a name="filtering-data"></a>篩選資料

有時候，您可能會想要只查看記錄的子集。 例如，只有點對點工作階段，而不是點對點工作階段與會議會話。 同樣地，您也需要減少傳回的記錄數。 根據預設，報告只能顯示資料集中的前1000筆記錄。 為了解決這些問題，大多數報表都包含許多篩選選項。 例如，如果您只想要查看2011年1月1日到2011日的記錄，您可以在 [收件者] 方塊中輸入 [年1月 2011 1 日]，在 **[收****件**者] 方塊中輸入1月 2011 15 日。 如果您接著按一下 [**查看報表**]，則傳回的資料會限制在2011年1月1日到2011年1月15日之間發生的活動。

您可使用的篩選依據您所查看的報表而有所不同。 如需特定報告的詳細資訊，請參閱該報告的 [說明] 主題。

</div>

<div>

## <a name="exporting-data"></a>匯出資料

[監視報告] 提供至少兩種不同的方式來匯出報表中包含的資料。 您可以在每個報告頂端出現的工具列中，使用 [**匯出**] 選項。 若要使用此選項，請從 [**選取格式**] 下拉式清單中選取所要的匯出格式。 您可以使用下列格式：

  - 含報表資料的 XML 檔案

  - CSV （逗號分隔）

  - Acrobat （PDF）檔案

  - MHTML （網頁檔案）

  - Excel

  - TIFF 檔案

  - Word

選取格式之後，按一下 [**匯出**]。 當 [檔案**下載**] 對話方塊出現時，按一下 [**儲存**]。 在 [**另存**新檔] 對話方塊中，選取目的地資料夾，輸入檔案名，然後按一下 [**儲存**]。

如果您已安裝 Microsoft OneNote，您也可以將報表資料複製到 OneNote。 若要這樣做，請以滑鼠右鍵按一下工具列上的 [**查看報表**] 按鈕。 在 [在**onenote 中選取位置**] 對話方塊中，選取 OneNote 中您要複製資料的區段，然後按一下 **[確定]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

