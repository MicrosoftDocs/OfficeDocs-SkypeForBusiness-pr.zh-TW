---
title: Lync Server 2013 延展性測試
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
ms.openlocfilehash: b23bd731e123c8dba78c3919f9f2a1ff1a6fd1cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049885"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scalability-testing-in-lync-server-2013"></a>在 Lync Server 2013 中進行測試的延展性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

Lync Server 2013 提供的伺服器基礎結構的所有 Lync Server 即時通訊，包括立即訊息 (IM) 和目前狀態、 會議以及 Enterprise Voice。 這包括任何功能會使用 Lync Server 2013 集區的硬體資源，並且因此，會影響效能和規模。 所有組織同樣也無法使用所有功能。

例如，某些組織可能使用視訊在會議中非常嚴重時其他人可能會很少或沒有視訊流量。 有些組織偏好共用應用程式共用，而其他人偏好相反的 PowerPoint 投影片。 部署 Enterprise Voice 這些組織可能或可能不常使用的回應群組應用程式。 大多數的組織部署監控伺服器，但不是許多部署封存伺服器。 此外，組織並非所有沒有相同的基礎結構，包括硬體容量、 網路容量及集區的數目和部署的集區的大小。 功能和基礎結構的多樣性帶來的挑戰延展性測試 – 不能以模擬的功能和基礎結構中的所有可能組合。

若要判斷延展性支援 Lync server，我們進行測試同時，使用 Lync Server 的所有功能的平均使用量模型 （使用者模型） 為基礎。 若要判斷適用於 Lync Server 工作負載的適當的使用者模型，我們分析多個資料點，包括客戶問卷調查、 來自 Microsoft 客戶經驗改進計畫的意見反應、 內部 IT 部門 microsoft Lync Server 使用狀況資料並從我們 Live Meeting 服務探索的資料。 在許多情況下，使用者模型有偏差向粗的負載，以針對組織內的使用狀況提供不感到安心邊界。

在我們的延展性測試，我們將設定 Lync Server 2013 集區，根據建議的硬體和軟體規格，包括基礎結構元件，例如 Active Directory 網域服務，硬體負載平衡器和防火牆。 我們將設定 Lync Server 環境盡可能將一般的真實環境。 我們接著會使用 [Lync Server 2013 壓力及效能工具來模擬 Lync Server 2013 負載 （以我們使用者模型為基礎）。 .

我們執行動作延展性測試 （包括多個三週測試回合） 的多個反覆運算的次數。 協助符合效能調整以及驗證我們的使用者模型中的延展性數字的支援，我們會使用所有測試的結果。

</div>

<span> </span>

</div>

</div>

</div>

