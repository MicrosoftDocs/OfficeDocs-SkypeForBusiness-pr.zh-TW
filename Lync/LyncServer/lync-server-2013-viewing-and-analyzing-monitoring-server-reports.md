---
title: Lync Server 2013：查看及分析監視伺服器報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing and analyzing monitoring server reports
ms:assetid: 4dd448f1-01d2-49b2-b109-0728f36566b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720332(v=OCS.15)
ms:contentKeyID: 63969599
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc942c887175bacb0047c5d82d1ad9a89c18ef5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-and-analyzing-monitoring-server-reports-in-lync-server-2013"></a>在 Lync Server 2013 中查看及分析監視伺服器報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-05-19_

[監視伺服器] 報告提供數種不同的語音品質測量，以監控傳送給最終使用者的 QoE。 此外，監視伺服器還包含數個內建的報表，您的組織可以用來在組織的網路上觀看使用方式及媒體質量趨勢，並針對發生的媒體質量問題進行疑難排解。

讓監視伺服器報告對日常及每週操作感興趣的主要部分，就是查看並分析媒體質量報告，特別是：

  - QoE 摘要/趨勢報表

  - QoE 效能報告

<div>

## <a name="view-reports-from-the-monitoring-server"></a>從監控伺服器查看報表

1.  從網頁瀏覽器，找出託管 SQL reporting services 的伺服器。

2.  從瀏覽器畫面查看所需的報告。

3.  可選選取 [匯出] 選項和 [所需的輸出格式]，匯出報表。

</div>

<div>

## <a name="configure-call-detail-recording-cdr"></a>設定通話詳細資料錄製（CDR）

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或擁有同等許可權），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**呼叫詳細資料錄製**]。

4.  在 [**通話詳細資料記錄**] 頁面上，按一下表格中的適當網站，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  若要開啟清除，請選取 [**啟用監視伺服器的清除**]。

6.  在 **[保持通話詳細資料錄製的最大持續時間（天）** ] 中：選取應保留通話詳細資料錄製的最大天數。

7.  若要在**最大持續時間（天）內保留錯誤報表資料：** 請選取要保留錯誤報表的最大天數。

8.  按一下 [認可]****。

</div>

<div>

## <a name="configure-qoe"></a>設定 QoE

1.  以 RTCUniversalServerAdmins 群組的成員或 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員的身分登入電腦。 如需詳細資訊，請參閱委派設定許可權。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [**體驗資料品質**]。

4.  在 [**體驗品質資料**] 頁面上，從表格中按一下適當的網站，按一下 [**編輯**]，然後按一下 [**顯示詳細**資料]。

5.  若要開啟清除，請選取 [**啟用監視伺服器的清除**]。

6.  在 **[保持通話詳細資料記錄的最大持續時間（天）** ] 中：選取 QoE 資料應保留的最大天數。

7.  按一下 [認可]。

</div>

<div>

## <a name="change-the-archiving-policy"></a>變更存檔原則

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。

4.  按一下原則清單中的 [全域]****，按一下 [編輯]****，然後按一下 [顯示詳細資料]****。

5.  在 [**編輯封存原則-全域**] 中，執行下列動作：

6.  若要啟用或停用部署的內部存檔，請選取或清除 [封存**內部通訊**] 核取方塊。

7.  若要啟用或停用部署的外部存檔，請選取或清除 [封存**外部通訊**] 核取方塊。

8.  按一下 [認可]****。

</div>

<div>

## <a name="apply-an-archiving-policy-to-a-user"></a>將存檔原則套用至使用者

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。

3.  在左導覽列中，按一下 [使用者]****，然後搜尋想要設定的使用者帳戶。

4.  在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]**** 及 [顯示詳細資料]****。

5.  在 [**存檔原則**] 下的 [**編輯 Lync Server 使用者**] 中，選取您要套用的存檔使用者原則。

6.  按一下 [認可]****。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中使用監視報告](lync-server-2013-using-monitoring-reports.md)  
[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)  
[Lync Server 2013 中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

