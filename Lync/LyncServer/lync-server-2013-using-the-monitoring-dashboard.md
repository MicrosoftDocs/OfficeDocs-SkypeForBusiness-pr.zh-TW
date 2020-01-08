---
title: Lync Server 2013：使用 [監視] 儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>在 Lync Server 2013 中使用 [監視] 儀表板

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-05_

[監視儀表板] 可讓系統管理員快速概覽其 Microsoft Lync Server 2013 系統健康與系統使用量。 儀表板的設計目的是顯示主要系統規格的匯總視圖，並顯示下列其中一項：

  - 當天的合計。 請注意，目前日期顯示的值代表從午夜到目前時間為止所記錄的資料（根據報表伺服器的當地時間）。 這表示您通常會查看部分日期的資料，而不是24小時的時間。 例如，如果伺服器的當地時間是 8:00 AM，您會看到八小時的資料，因為午夜和目前時間 8:00 AM 之間有八個小時。

  - 周總計與過去六周的總趨勢。

  - 當月總計及過去六個月的總趨勢（僅適用于系統使用量）。

請注意，您可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) Cmdlet 來傳回用來存取 Lync Server 2013 監視報告的 URL：

    Get-CsReportingConfiguration

根據預設，[監視] 儀表板會針對目前的周數（以及前六周的趨勢總計）顯示下列度量單位的資料：

<div>

## <a name="system-usage-metrics"></a>系統使用量指標

**註冊**

  - 唯一的使用者登錄

**對等**

  - 總會話數

  - IM 會話

  - 音訊會話

  - 影片會議

  - 應用程式共用

  - 音訊會話總分鐘數

  - 平均音訊會話分鐘數

**會議**

  - 會議總數

  - IM 會議

  - A/V 會議

  - 應用程式共用會議

  - 網路會議

  - 召集人總計

  - A/V 會議紀要總計

  - 速率.A/V 會議紀要

  - PSTN 會議總數

  - PSTN 參與者總數

  - PSTN 參與者通話總分鐘數

除了系統使用標準之外，下列度量單位還會顯示當天及前六天的總計（如果您選取 [**每週檢視**]），或是在您選取 [**每月檢視**] 時，則為 [目前周] 和 [過去六周]。

</div>

<div>

## <a name="per-user-call-diagnostics"></a>每個使用者呼叫診斷

**有通話失敗的使用者**

  - 使用通話失敗的使用者總數

  - 含通話失敗的會議召集人

**較差品質通話的使用者**

  - 具有較差品質通話的使用者總數

</div>

<div>

## <a name="call-diagnostics"></a>呼叫診斷

對等

  - 失敗總計

  - 整體失敗率

  - IM 失敗率

  - 音訊失敗率

  - 應用程式共用失敗率

會議

  - 失敗總計

  - 整體失敗率

  - IM 失敗率

  - A/V 失敗率

  - 應用程式共用失敗率

依失敗的會話排前五台伺服器

</div>

<div>

## <a name="media-quality-diagnostics"></a>媒體質量診斷

對等

  - 低品質通話總計

  - 品質不佳的通話百分比

  - 品質不佳的 PSTN 通話

會議

  - 低品質通話總計

  - 品質不佳的通話百分比

  - 品質不佳的 PSTN 通話

低品質通話百分比的最差伺服器

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>使用 [監視儀表板]

如前所述，預設的合計會顯示在目前的周，而趨勢值則會顯示過去六周。 如果您想要查看當月的合計（以及過去六個月的趨勢值），請按一下儀表板右上角的 [**每月檢視**] 連結。 如果您決定要查看每月總計，連結文字將會變更為 [**每週] 視圖**。 您可以按一下該連結，切換回 [每週] 視圖。

<div>


> [!TIP]  
> [監視儀表板] 會限制您在過去六周（或幾個月）的 [本周] （或 [月]）和趨勢值中查看 [合計]。 您無法變更這些日期和時間。 例如，您無法使用儀表板來查看第九個月前的時間週期的報表合計。



</div>

[**本周]、[****本月**] 或 [ **Today** ] 欄中顯示的值會將您連結到專案的更詳細資訊。 請記住，欄名稱和顯示在該欄中的值通常會根據所選的度量，以及您是否已選取 [每週檢視] 或 [每月] 視圖而有所不同。 例如，如果您按一下 [針對**唯一的使用者登錄**統計顯示的合計]，您會在指定的時間範圍內看到 [**使用者註冊] 報告**。 您隨時都可以按一下 [**儀表板**] 返回 [監視] 儀表板。

<div>


> [!TIP]  
> 您也可以按一下儀表板右上角的 [<STRONG>報告</STRONG>] 連結，以存取 [監視伺服器報告] 首頁。



</div>

[**趨勢**] 欄會顯示一個簡單的線形圖形，其中顯示過去六周的總計（或是根據公制和時間間隔、過去六天或過去六個月）。 這些簡單的折線圖會針對每個時間段顯示一個未標記的資料點（例如，過去六周內的一個未標記資料點）。 不過，您可以透過將滑鼠指標放在圖形上，來檢索這些圖表的實際值。 在這種情況下，工具提示會顯示圖形中的最大值和最小值。

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>從 [監控] 儀表板匯出資料

[監視儀表板] 提供多種匯出目前儀表板視圖的方法。 在 [儀表板] 工具列上，您會看到一個圖示，看起來像是一個附加了綠色箭號的軟碟。 如果您按一下這個圖示，就會出現下拉式清單，提供下列資料匯出格式：

  - 含報表資料的 XML 檔案

  - CSV （逗號分隔）

  - PDF

  - MHTML （網頁檔案）

  - Excel

  - TIFF 檔案

  - Word

若要匯出目前的儀表板視圖（及其值），請按一下所需的匯出選項。 Lync Server 2013 會以指定的格式產生報表，然後提供開啟或儲存該報表的選項。 請注意，根據預設，Lync Server 會將 [報告**監控] 儀表板**標題儲存至 [下載] 資料夾。 若要為報表指定不同的名稱，或將其儲存在不同的資料夾，請按一下 [**儲存**] 按鈕旁的箭號，然後按一下 [**另存**新檔]。 如果您使用 [名稱**監視] 儀表板**，並將報告儲存在 [下載] 資料夾中，您就可以按一下 [**儲存**] 按鈕。

您可以嘗試匯出儀表板資料時，會出現 [**安全性警告**] 對話方塊，並顯示「您目前的設定不允許下載此檔案」訊息。 如果發生這種情況，請執行下列動作：

  - 在 Internet Explorer 中，選取 [**網際網路選項**]。

  - 在 [**網際網路選項**] 對話方塊中，按一下 [**安全性**] 索引標籤上的 [**信任的網站**]，然後按一下 [**網站**]。

  - 在 [**信任的網站**] 對話方塊中，按一下 [**新增**]，將運行 lync Server 2013 報告的 lync server 2013 新增至信任的網站集合。

  - 按一下 [**關閉**]，然後按一下 **[確定]**。

然後，您必須重新整理監視儀表板，變更才會生效。 若要這樣做，請按 F5 或按一下儀表板工具列中**的 [重新**整理] 圖示。 （[重新整理 **] 圖示是**一個在其中有一對綠色箭號的圓圈）。

您也可以建立包含即時資料摘要的 Excel 試算表，其中包含最新監視儀表板資料的連結。 若要建立即時資料摘要檔案，請按一下工具列中的 [橙色**匯出至資料**摘要] 圖示。

如果您想要列印目前的儀表板，請按一下工具列中的 [印表機] 圖示。

</div>

</div>

<span> </span>

</div>

</div>

</div>

