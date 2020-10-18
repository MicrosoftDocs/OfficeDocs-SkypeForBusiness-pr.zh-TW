---
title: Lync Server 2013 可擴充性測試
description: Lync Server 2013 可伸縮性測試。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73b4ab8726de7ea068ed60fedf104b01fe91ac1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574849"
---
# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 的可擴充性測試

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Lync Server 2013 提供所有 Lync Server 即時通訊的伺服器基礎結構，包括立即訊息 (IM) 和目前狀態、會議及 Enterprise Voice。 這包括任何使用 Lync Server 2013 集區之硬體資源的功能，因此會影響效能及規模。 所有組織都不會平等使用所有功能。

例如，有些組織可能會在會議中經常使用影片，有些人可能會有很少或無影片的使用方式。 有些組織喜歡 PowerPoint 的幻燈片共用應用程式共用，其他組織則喜歡相反的工作。 部署企業語音的組織可能會有或不會大量使用回應群組應用程式。 大多陣列織會部署監控伺服器，但不是許多部署封存伺服器。 此外，組織沒有相同的基礎結構，包括硬體容量、網路容量，以及已部署集區的集區數量和大小。 功能和基礎結構的多樣性對可擴充性測試面臨挑戰–無法模擬所有可能的功能和基礎結構組合。

為判斷 Lync Server 的可伸縮性支援，我們會根據平均使用模式 (使用者模型) ，以並行方式使用所有 Lync 伺服器功能進行測試。 若要判斷 Lync Server 工作負載的適當使用者模型，我們會分析許多資料點，包括客戶問卷調查、Microsoft 客戶經驗改進計畫的回饋、microsoft 的內部 IT 部門的 Lync Server 使用方式資料，以及從 Live Meeting 服務挖掘的資料。 在許多情況下，使用者模型有一個偏向的負載，可為組織內的使用提供舒適的邊界。

在我們的可擴充性測試中，我們會根據建議的硬體和軟體規格（包括基礎結構元件，例如 Active Directory 網域服務、硬體負載平衡器和防火牆）設定 Lync Server 2013 集區。 我們將 Lync Server 環境盡可能與一般的實際環境緊密地設定。 然後，我們會使用 Lync Server 2013 壓力和效能工具，根據我們的使用者模型) ，模擬 Lync Server 2013 的負載 (。 .

我們會執行多個可伸縮性測試的反覆運算 (包括多個三周的測試執行) 。 我們會使用所有測試的結果來協助效能調整，並確認對我們使用者模型中的可伸縮性數目的支援。

</div>

<span> </span>

</div>

</div>

</div>

