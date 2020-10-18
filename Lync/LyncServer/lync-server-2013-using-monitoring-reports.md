---
title: Lync Server 2013：使用監控報告
description: Lync Server 2013：使用監控報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e19b266e0580a89b814e80982c5f4ff2146ec01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580309"
---
# <a name="using-monitoring-reports-in-lync-server-2013"></a>在 Lync Server 2013 中使用監控報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-21_

Lync Server 2013 包含一組 Microsoft SQL Server Reporting Service 所發佈的標準報告。 這些可透過網頁瀏覽器存取的報告，會根據詳細通話記錄 (CDR) 和經驗品質 (QoE) 資料庫中儲存的 CDR 和 QoE 記錄，提供使用情況、通話診斷資訊況及媒體品質資訊。

為了使用這些報告，您必須在執行 SQL Server 實例的電腦上安裝監控報告。

<div>

## <a name="in-this-section"></a>本章節內容

  - [在 Lync Server 2013 中使用監控儀表板](lync-server-2013-using-the-monitoring-dashboard.md)    為系統管理員提供系統健康情況和系統使用狀況的快速綜述。

  - [Lync Server 2013](lync-server-2013-system-usage-reports.md)     中的系統使用方式報告提供根據 Lync Server 收集之 CDR 資料的系統使用資訊。

  - [在 Lync Server 2013 中 (每位使用者) 的通話診斷報告](lync-server-2013-call-diagnostic-reports-per-user.md)    提供失敗的對等和會議會話的每一使用者相關資訊。

  - [在 Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)     中呼叫診斷報告提供失敗的對等和會議會話的摘要資訊和診斷資料。

  - [Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)     中的媒體質量診斷報告提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。

</div>

<div>

## <a name="locating-records"></a>找出記錄

監控報告每次只會在螢幕上顯示一小部分的記錄。螢幕上實際顯示的記錄數量會依報告而異。若要檢視螢幕上未顯示的記錄，可使用標準的上一頁和下一頁控制項 (在每份報告的工具列上) 來翻閱資料。您也可以快速跳至資料集的第一頁或最後一頁。

除了使用上一頁和下一頁控制項外，只要在 **[目前頁面]** 方塊中鍵入頁碼再按 ENTER 鍵，就可跳至資料集的任何一頁。

除了翻閱資料的功能外，每份報告也提供有限的記錄尋找功能。若要依指定的值來尋找記錄，請在 **[尋找]** 方塊中鍵入指定值，然後按一下 **[尋找]**。接著報告即會開始搜尋資料，並會停在符合 **[尋找]** 方塊輸入值的第一筆記錄上，若要尋找下一筆符合搜尋條件的記錄，請按 **[下一筆]**。

如前所述，監控報告只提供最基本的搜尋功能。例如，您無法指定要在哪一個欄位內搜尋值。此搜尋機制會自動在所有記錄的所有欄位中搜尋符合的值。搜尋中不能使用萬用字元，且每筆搜尋都會找出部分符合的結果。也就是說，如果您搜尋 111，將不只會找到數值 111，也會找到 11100、811、3112、611A5B 以及任何其他含有數值 111 的欄位 (無論出現在欄位的任何地方)。

每份報告會顯示的記錄都是預先設定好的。例如，使用者註冊報告預設會顯示過去一星期使用者的註冊活動。某些情況下，這可能會導致報告沒有傳回任何結果。以這個案例來說，就代表過去一星期內沒有任何使用者註冊活動發生。若您看見「沒有結果符合報告篩選」訊息，請嘗試變更篩選值 (例如，將時間範圍從過去一星期改成過去一個月) 再重新查詢。如需詳細資訊，請參閱本主題稍後的＜篩選資料＞一節。

</div>

<div>

## <a name="filtering-data"></a>篩選資料

有些時候您可能只想查看某一組子集的資料。例如，只看對等工作階段，而排除對等工作階段和會議工作階段兩者的資料。同樣地，也有些時候您需要減少傳回記錄的筆數。依預設，每份報告只能顯示資料集中的首 1,000 筆記錄。為因應這些情況，多半的報告都含有一些篩選的選項。例如，如果您只想檢視 2011 年 1 月 1 日到 2011 年 1 月 15 日之間的記錄，您可在 **[從]** 方塊中輸入 2011 年 1 月 1 日，然後在 **[到]** 方塊中輸入 2011 年 1 月 15 日。接著只要按一下 **[檢視報告]**，便只會傳回 2011 年 1 月 1 日到 2011 年 1 月 15 日之間所發生的活動。

可用的篩選器依您檢視的報告而有所不同。如需特定報告的詳細資訊，請參閱該報告的說明主題。

</div>

<div>

## <a name="exporting-data"></a>匯出資料

監控報告提供了至少兩種匯出報告內資料的方式。您可使用工具列 (在報告的最上方) 中的 **[匯出]** 選項。若要使用這個選項，請在 **[選取格式]** 下拉式清單中選取想要的匯入格式。共有下列幾種格式可選：

  - XML 檔附加報告資料

  - CSV (逗點分隔)

  - Acrobat (PDF) 檔

  - MHTML (網頁封存)

  - Excel

  - TIFF 檔

  - Word

格式選好後，按一下 [匯出]****。[檔案下載]**** 對話方塊出現時，按一下 [儲存]****。在 [另存新檔]**** 對話方塊中，選取一個目的資料夾，輸入檔案名稱，然後按一下 [儲存]****。

若有安裝 Microsoft OneNote，您也可複製報告資料到 OneNote。方法是以滑鼠右鍵按一下工具列上的 [檢視報告]**** 按鈕。接著在 [在 OneNote 中選擇位置]**** 對話方塊中選擇您要複製哪些位置的資料到 OneNote，最後按一下 [確定]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

