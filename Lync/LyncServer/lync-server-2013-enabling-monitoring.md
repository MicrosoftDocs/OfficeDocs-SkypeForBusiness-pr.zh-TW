---
title: Lync Server 2013：啟用監視
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f11aab3c58a43ac0746cb1f297bf4f3f85d28c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a>在 Lync Server 2013 中啟用監視

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

雖然整合的資料收集代理程式會在每個前端伺服器上自動安裝並啟用，這並不表示您會在完成安裝 Microsoft Lync Server 2013 的時刻，自動開始收集監視資料。 相反地，您必須執行兩個動作：您必須將前端伺服器/前端池與監控資料庫建立關聯，而且您必須啟用 [呼叫詳細資料錄製（CDR）] 和/或 [（QoE）] （在全域範圍和/或網站範圍中）的監視品質（）。

如需將前端伺服器或頂層池與監視資料庫相關聯的逐步指示，請參閱部署指南中的[使用 Lync Server 2013 中的 [監視存儲] 與 [前端] 池關聯](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md)的主題。 建立這些關聯之後，且在您新的 Lync Server 拓撲發佈之後，您仍然無法收集監視資料。 這是因為，在您安裝 Lync Server 2013 時，會停用 CDR 與 QoE 資料收集。

若要開始收集資料，您需要啟用 CDR 和/或 QoE 監視。 （請注意，您不需要同時啟用 CDR 與 QoE 監視; 如果您想要的話，您可以啟用一種監視類型，讓其他類型保持停用。）若要在全域範圍啟用 CDR 監視，請在 Lync Server 管理命令介面中執行下列命令：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

或者，您可以在 Lync Server 2013 的 [控制台] 中啟用 CDR 監視。 在 Lync Server [控制台] 中，完成下列程式：

1.  按一下 [**監視**]。

2.  在 [**通話詳細資料記錄**] 索引標籤上，按兩下 [**全域**] 設定。

3.  在 [**編輯通話詳細資料錄製（CDR）] 設定**窗格中，選取 [**啟用 CDRs 監視**]，然後按一下 [**確認**]。

若要在全域範圍中啟用 QoE 監視，請在 Lync Server 管理命令介面內執行此命令：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

如果您想要的話，您也可以在 Lync Server 的 [控制台] 中啟用 QoE 監視。 從 [控制] 面板中，完成下列程式：

1.  按一下 [**監視**]。

2.  在 [**體驗品質**] 的 [資料] 索引標籤上，按兩下 [**全域**] 設定。

3.  在 [**編輯體驗品質（QoE）] 設定**窗格中，選取 [**啟用 QoE 資料的監視**]，然後按一下 [**確認**]。

如前所述，前面的範例可在全域範圍內啟用監視;也就是說，它們可在整個組織中啟用 CDR 與 QoE 監視。 或者，您可以在網站範圍中建立個別的 CDR 及 QoE 設定設定，然後有選擇性地針對每個網站啟用或停用監視。 例如，您可以為雷德蒙的網站啟用 CDR 監視，但卻停用了您的都柏林網站的 CDR 監視。 如需管理監視設定設定的詳細資訊，請參閱在[Lync Server 2013 中設定通話詳細資料錄製和體驗品質設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)的 [部署指南] 主題。

</div>

<span> </span>

</div>

</div>

</div>

