---
title: Lync Server 2013：啟用監控
description: Lync Server 2013：啟用監視。
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
ms.openlocfilehash: d8995042bdc9b121dc5253940104bb167567ddcc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558479"
---
# <a name="enabling-monitoring-in-lync-server-2013"></a>啟用 Lync Server 2013 中的監控

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-17_

雖然整合的資料集合代理程式會在每一部前端伺服器上自動安裝及啟用，但這並不意味著您會在完成安裝 Microsoft Lync Server 2013 時，自動開始收集監控資料。 您還必須執行下列兩個動作：將前端伺服器/前端集區與監控資料庫建立關聯，且您必須啟用全域範圍及/或網站範圍的詳細通話記錄 (CDR) 及/或經驗品質 (QoE) 監視。

如需將前端伺服器或前端集區與監控資料庫相關聯的逐步指示，請參閱部署指南中的主題：將 [監視存放區與前端集區相關聯的 Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) 。 即使建立好這些關聯並發行新的 Lync Server 拓撲之後，您還是不能收集監視資料。 這是因為在您安裝 Lync Server 2013 時，預設會停用 CDR 和 QoE 資料收集。

若要開始收集資料，您必須啟用 CDR 及/或 QoE 監視。  (請注意，您不需要同時啟用 CDR 和 QoE 監控;如果您願意，您可以啟用一種監控類型，讓其他類型保持停用。 ) 若要在全域範圍啟用 CDR 監控，請在 Lync Server 管理命令介面中執行下列命令：

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

或者，您可以從 Lync Server 2013 控制台中啟用 CDR 監控。 在 [Lync Server 控制台] 中，完成下列程式：

1.  按一下 [監視]****。

2.  在 [詳細通話記錄]**** 索引標籤上，按兩下 [全域]**** 設定。

3.  在 [編輯詳細通話記錄 (CDR) 設定]**** 窗格中，選取 [啟用 CDR 監視]****，然後按一下 [認可]****。

若要在全域範圍啟用 QoE 監視，請在 Lync Server 管理命令介面中執行下列命令：

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

如果您願意，也可以在 Lync Server 控制台中啟用 QoE 監視。 請從控制台，完成下列程序：

1.  按一下 [監視]****。

2.  在 [經驗品質資料]**** 索引標籤上，按兩下 [全域]**** 設定。

3.  在 [編輯經驗品質 (QoE) 設定]**** 窗格中，選取 [啟用 QoE 資料監視]****，然後按一下 [認可]****。

如前所述，上述的範例可啟用全域範圍的監視；也就是說，其可啟用您整個組織的 CDR 和 QoE 監視。 此外，您也可以在網站範圍建立個別的 CDR 和 QoE 組態設定，然後再分別針對每個網站啟用或停用監視。 例如，您可以啟用 Redmond 網站的 CDR 監視，然後停用 Dublin 網站的 CDR 監視。 如需管理監控設定設定的詳細資訊，請參閱部署指南主題， [設定 Lync Server 2013 中的詳細通話記錄及經驗品質設定](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)。

</div>

<span> </span>

</div>

</div>

</div>

