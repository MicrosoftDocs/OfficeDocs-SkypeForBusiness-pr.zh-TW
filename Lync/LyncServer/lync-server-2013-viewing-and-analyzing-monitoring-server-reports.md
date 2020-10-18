---
title: Lync Server 2013：查看和分析監控伺服器報告
description: Lync Server 2013：查看和分析監控伺服器報告。
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
ms.openlocfilehash: 3f2a1812d76a49d487bea35acae3e22ea403f105
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580039"
---
# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>在 Lync Server 2013 中查看及分析監控伺服器報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-19_

監控伺服器報告提供數種不同的語音品質度量，以監視傳遞給使用者的 QoE。 此外，監控伺服器也包含數個內建報告，您的組織可以用來監視組織網路的流量和媒體質量趨勢，並疑難排解所引發的媒體質量問題。

使監控伺服器報告成為每日和每週作業的主要工作是查看和分析媒體質量報告，具體如下：

  - QoE 摘要/趨勢報表

  - QoE 效能報告

<div>

## <a name="view-reports-from-the-monitoring-server"></a>從監控伺服器查看報告

1.  從網頁瀏覽器中，找出主控 SQL reporting services 的伺服器。

2.  從瀏覽器畫面查看必要的報表。

3.   (選用) 請選取 [匯出] 選項及必要的輸出格式，以匯出報告。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>設定 (CDR) 的詳細通話記錄

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或具有對等許可權) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。

4.  在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。

5.  若要開啟清除，請選取 [ **啟用監視伺服器的清除**]。

6.  在 [ **保留詳細通話記錄 (天數) ：** ] 中，選取應該保留詳細通話記錄的最大天數。

7.  在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="configure-qoe"></a>設定 QoE

1.  以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜Delegate Setup Permissions＞。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。

3.  在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。

4.  在 [ **經驗品質資料** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細**資料]。

5.  若要開啟清除，請選取 [ **啟用監視伺服器的清除**]。

6.  在 [ **保留詳細通話記錄的最大持續時間 (天數) ：** ] 中，選取應該保留 QoE 資料的最大天數。

7.  按一下 [認可]。

</div>

<div>

## <a name="change-the-archiving-policy"></a>變更封存原則

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。

3.  在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。

4.  按一下原則清單中的 **[全域]**，並按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。

5.  在 **[編輯封存原則 - 全域]** 中，執行下列動作：

6.  若要啟用或停用部署的內部封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。

7.  若要啟用或停用部署的外部封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。

8.  按一下 **[認可]**。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>將封存原則套用至使用者

1.  使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。

3.  在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。

5.  在 [封存**原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的封存使用者原則。

6.  按一下 **[認可]**。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中使用監控報告](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

