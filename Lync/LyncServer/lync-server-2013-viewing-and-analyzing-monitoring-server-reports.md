---
title: Lync Server 2013： 檢視及分析監控伺服器報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9970e4c440148cac2002088212a48283c86184eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>檢視及分析 Lync Server 2013 中的監控伺服器報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-05-19_

監控伺服器報告提供監視 QoE，即會傳遞至使用者的語音品質的數個不同的量值。 此外，監控伺服器包含幾個內建的報告，您的組織可觀看您的組織網路上的使用情況和媒體品質趨勢和引發的媒體品質問題的疑難排解。

保持 Monitoring Server Reports 有趣每天與每週作業的主要部分是檢視，且分析媒體品質的報告，特別是：

  - QoE 摘要/趨勢報告

  - QoE 效能報告

<div>

## <a name="view-reports-from-the-monitoring-server"></a>從監控伺服器檢視報告

1.  從 web 瀏覽器中，找出您主控 SQL reporting services 的伺服器。

2.  檢視從瀏覽器] 畫面中所需的報表。

3.  （選用）將報表匯出藉由選取 [匯出] 選項及所需的輸出格式。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>設定詳細通話記錄 (CDR)

1.  從使用者帳戶是 RTCUniversalServerAdmins 群組成員 （或具有相等權限），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入是在您部署了 Lync Server 2013 網路中的任何電腦。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。

4.  在 [**詳細通話記錄**] 頁面上，按一下表格中的適當網站按一下 [**編輯**]，然後按一下 [**顯示詳細資料**。

5.  若要開啟清除，請選取 [**啟用清除的監控伺服器**。

6.  在 [**保留通話詳細資料錄製最大持續期限 （天）：** 選取應該保留詳細通話最大天數。

7.  在 [**將錯誤報告資料保留最大持續期限 （天）：** 選取錯誤報告應保留天數上限。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="configure-qoe"></a>需要設定 QoE

1.  以 RTCUniversalServerAdmins 群組成員或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜Delegate Setup Permissions＞。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4.  在 [**經驗品質資料**] 頁面上，按一下表格中的適當網站按一下 [**編輯**]，然後按一下 [**顯示詳細資料**。

5.  若要開啟清除，請選取 [**啟用清除的監控伺服器**。

6.  在 [**保留通話詳細資料錄製最大持續期限 （天）：** 選取應該保留 QoE 資料最大天數。

7.  按一下 [認可]。

</div>

<div>

## <a name="change-the-archiving-policy"></a>若要變更封存原則

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。

3.  在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。

4.  按一下原則清單中的 **[全域]**，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。

5.  在 **[編輯封存原則 - 全域]** 中，執行下列動作：

6.  若要啟用或停用內部封存的部署，請選取或清除 [**封存內部通訊**] 核取方塊。

7.  若要啟用或停用 [部署的外部封存，請選取或清除 [**封存外部通訊**] 核取方塊。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>封存原則套用至使用者

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，，，然後輸入 Admin URL 以開啟 Lync Server Control Panel。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [**編輯 Lync Server 使用者**] [**封存原則**] 下，選取您想要套用的封存使用者原則。

6.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中使用監控報告](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 中的媒體品質比較報告](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

