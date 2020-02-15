---
title: Lync Server 2013： 使用監控儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 643cbc55730d8efb1520ed88c40977c90e35f2fa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a>Lync Server 2013 中使用監控儀表板

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-05_

監控儀表板提供系統管理員使用其 Microsoft Lync Server 2013 系統健康情況與系統使用情況的快速概觀。 儀表板被設計來顯示重要系統計量彙總檢視並若要這麼做會顯示下列一項：

  - 目前日期的總數。 請注意顯示當天的值，代表已從午夜到目前的時間 （根據報表伺服器本地時間） 將記錄的資料。 這表示，您通常檢視資料部分的一天，以及不在 24 小時期間內。 例如，如果伺服器的本地時間為上午 8:00，您看到八個小時的資料因為有八個小時午夜與目前時間的上午 8:00 之間。

  - 當週的總計和過去六週的趨勢總計。

  - 當月總計和過去六個月 （適用於僅限系統使用量） 的趨勢總計。

請注意，您可以使用[Get-csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet 可傳回用來存取 Lync Server 2013 Monitoring Reports 的 URL:

    Get-CsReportingConfiguration

根據預設，監控儀表板會顯示的週 （以及前六週的趨勢總計） 的下列計量資料：

<div>

## <a name="system-usage-metrics"></a>系統使用狀況計量

**註冊**

  - 唯一的使用者登入

**端對端**

  - 工作階段總數

  - IM 工作階段

  - 音訊工作階段

  - 視訊工作階段

  - 應用程式共用

  - 音訊工作階段分鐘總數

  - 平均音訊工作階段分鐘

**會議**

  - 會議總數

  - IM 會議

  - A / V 會議

  - 應用程式共用會議

  - Web 會議

  - 召集人總數

  - A/V 會議總分鐘數

  - 平均A / V 會議分鐘

  - PSTN 會議總數

  - PSTN 參與者總數

  - PSTN 參與者分鐘總數

除了系統使用狀況計量，下列計量可以顯示總當天與前六天 （如果您選取 [**每週檢視**) 或週與過去六週如果您選取 [**每月檢視**。

</div>

<div>

## <a name="per-user-call-diagnostics"></a>每位使用者通話診斷

**通話失敗的使用者**

  - 通話失敗的使用者總數

  - 通話失敗的會議召集人

**通話品質不良的使用者**

  - 通話品質不良的使用者總數

</div>

<div>

## <a name="call-diagnostics"></a>通話診斷

端對端

  - 失敗總數

  - 整體失敗率

  - IM 失敗率

  - 音訊失敗率

  - 應用程式共用失敗率

會議

  - 失敗總數

  - 整體失敗率

  - IM 失敗率

  - A / V 失敗率

  - 應用程式共用失敗率

工作階段失敗的前五部伺服器

</div>

<div>

## <a name="media-quality-diagnostics"></a>媒體品質診斷

端對端

  - 通話品質不良總數

  - 通話品質不良百分比

  - 品質不良的 PSTN 通話

會議

  - 通話品質不良總數

  - 通話品質不良百分比

  - 品質不良的 PSTN 通話

通話品質不良百分比最差的伺服器

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a>使用監控儀表板

如所述，預設總計會顯示目前日當週，並顯示過去六週的趨勢值。 如果您偏好以查看總針對本月 （以及過去六個月的趨勢值），按一下 [儀表板右上角中的**每月檢視**] 連結。 如果您決定要檢視每月總計，連結文字將變更為**每週檢視**。 您可以切換回每週檢視，請按一下該連結。

<div>


> [!TIP]  
> 監控儀表板會限制您查看目前星期幾 （或） 的總計和過去六週 （或月數） 的趨勢值。 您無法變更這些日期和時間。 例如，您無法使用儀表板，來檢視報表總計開始前九個月的時間週期。



</div>

所顯示的值在**本週**]、 [**這個月**，或 [**今天**] 資料行連結您關於項目的詳細資訊。 請記住，資料行名稱並顯示在該欄的值將會經常而有所不同選擇評量，並根據您是否已選取每週檢視] 或 [每月檢視。 例如，如果您按一下 [顯示為**唯一的使用者登入**評量的總計您會看到**使用者註冊報告**在指定的時間週期內。 您可以回到 [監控儀表板隨時按一下**儀表板**。

<div>


> [!TIP]  
> 您也可以存取監控伺服器報告首頁上，按一下儀表板右上角的 [<STRONG>報告</STRONG>] 連結。



</div>

**趨勢**資料行會顯示過去六週的 （或，視評量和過去六天或過去六個月的時間間隔而定） 顯示總計簡單線條圖。 這些簡單線條圖形會顯示一個未標示的資料點的每個時間週期 （例如，過去六週的每一個未標示的資料點）。 不過，您可以透過此圖形按住滑鼠指標擷取這些圖形的實際值。 在此情況下，工具提示顯示您的最大和最小值圖形中。

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a>從監控儀表板匯出資料

監控儀表板提供多種方式來匯出目前的儀表板檢視。 在儀表板] 工具列中，您會看到帶有綠色箭頭附加至它看起來像軟碟圖示。 如果您按一下此圖示，會出現] 下拉式清單，提供您下列的資料匯出格式：

  - XML 檔附加報告資料

  - CSV (逗點分隔)

  - PDF

  - MHTML (網頁封存)

  - Excel

  - TIFF 檔

  - Word

若要匯出目前的儀表板檢視 （和其值），請按一下想要的匯出的選項。 Lync Server 2013 產生報告，以指定的格式，然後為您提供的開啟該報表，或將它儲存選項。 請注意，根據預設，Lync Server titles 報表**監控儀表板**並將它儲存到您的下載項目] 資料夾。 若要授與報表的不同的名稱，或將它儲存在不同的資料夾，按一下 [**儲存**] 按鈕旁的箭號，然後按一下 [**另存新檔**。 如果您是好名稱**監控儀表板**並與需要儲存的下載項目資料夾中的報告您也可以按一下 [**儲存**] 按鈕。

有可能，當您嘗試匯出儀表板的資料，**安全性警訊**] 對話方塊會顯示訊息以及 「 您目前的設定不允許下載這個檔案。 」 如果發生這種情形，請執行下列動作：

  - Internet Explorer 中，選取 [**網際網路選項**。

  - 在 [**網際網路選項**] 對話方塊的 [**安全性**] 索引標籤中，按一下 [**信任的網站**，然後按一下 [**網站**。

  - 在 [**信任的網站**] 對話方塊中，按一下 [**新增**若要新增至信任的網站集合執行 Lync Server 2013 Reports Lync Server 2013。

  - 按一下 [**關閉**]，然後按一下 [**確定]**。

您接著需要重新整理監控儀表板之前所做的變更才會生效。 若要這麼做，請按 f5 鍵或按一下 [儀表板工具列中的 [**重新整理**] 圖示。 （[**重新整理**] 圖示是圓中它的綠色箭頭的一組）。

您也可以建立 Excel 試算表，其中包含即時資料摘要，包括最新的監控儀表板資料的連結。 若要建立的即時資料摘要的檔案，按一下工具列中橘色的 [**匯出至資料摘要**] 圖示。

如果您偏好列印目前的儀表板，然後按一下工具列中的 [印表機] 圖示。

</div>

</div>

<span> </span>

</div>

</div>

</div>

