---
title: Lync Server 2013 可伸縮性測試
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f454ad3d78affb7106bcd0e750adae13624d9c9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>Lync Server 2013 中的可伸縮性測試

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

Lync Server 2013 提供所有 Lync Server 即時通訊的伺服器基礎結構，包括立即訊息（IM）與目前狀態、會議和企業語音。 這包括使用 Lync Server 2013 池之硬體資源的所有功能，因此會影響效能和縮放比例。 所有組織都不是同等地使用所有功能。

例如，某些組織可能會在會議中大量使用影片，而其他人可能只會有很少或沒有影片使用。 某些組織傾向于將 PowerPoint 投影片共用到應用程式共用，而其他組織則喜歡相反的方式。 那些部署企業語音的組織可能會或不會大量使用回應群組應用程式。 大多陣列織會部署監視伺服器，但不是許多人都會部署封存伺服器。 此外，組織並非全部都有相同的基礎結構，包括硬體容量、網路容量，以及已部署的池數和大小。 這些功能與基礎結構的多樣性會帶來可伸縮性測試的挑戰，不可能模擬所有可能的功能與基礎結構組合。

為了判斷 Lync Server 的伸縮性支援，我們會根據平均使用量模型（使用者模型），以並行方式使用所有 Lync Server 功能進行測試。 若要針對 Lync Server 工作負載判斷適當的使用者模型，我們分析了許多資料點，包括客戶問卷、Microsoft 客戶經驗改進計畫的意見反應，以及來自 Microsoft 內部 IT 部門的 Lync Server 使用資料。以及從我們的 Live Meeting 服務挖掘的資料。 在許多情況下，使用者模型會有較重的負載來偏向，為組織內的使用提供舒適的邊界。

在我們的可伸縮性測試中，我們根據建議的硬體和軟體規格設定 Lync Server 2013 池，包括基礎結構元件，例如 Active Directory 網域服務、硬體負載平衡器和防火牆。 我們將 Lync Server 環境盡可能緊密地設定為一般的實際環境。 接著，我們使用 Lync Server 2013 的應力和效能工具來模擬 Lync Server 2013 載入（根據我們的使用者模型）。 .

我們會進行多個伸縮性測試的多次小性，包括多個為期三周的測試執行）。 我們會使用所有測試的結果來協助效能調整，以及驗證使用者模型中的可伸縮性數位支援。

</div>

<span> </span>

</div>

</div>

</div>

