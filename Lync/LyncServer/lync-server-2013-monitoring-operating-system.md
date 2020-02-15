---
title: Lync Server 2013： 監視作業系統
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5bd837bab2ca4323dd0fb2f4d29b31d653d37c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Lync Server 2013 中的監視作業系統

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015年-01-26_

您必須監視效能的所有伺服器和 Lync Server 2013 中的元件。 很明顯地，下列其中一個最重要的元件是作業系統本身。 Lync Server 2013 支援 x64 版本的：

  - Windows Server 2008 R2

  - Windows Server 2012 和 Windows Server 2012 R2

監視作業系統的最透明方法是使用 Windows Server 作業系統管理組件。 執行 Windows Server 2012、 Windows Server 2012 R2 和 Windows Server 2008 R2 的電腦提供基礎監視基本項目，例如效能、 健康情況及可用性。

藉由偵測、 警示，並自動回應重要事件及效能指標，這些管理組件減少問題的解決時間，並增加整體的可用性和正在執行 Windows Server 的系統的效能作業系統。

不同相關 Windows Server 管理組件的 System Center Operations Manager，於下列系統工具和資源可以用來監視健康狀況的作業系統 （根據作業系統的版本）。

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 包括下列額外的功能和工具，以協助系統管理員使用基本的作業系統監控與管理：

  - **Windows 資源監視器**是功能強大的工具，了解如何使用系統資源的程序和服務。 除了監視即時的資源使用量，資源監視器可協助分析回應程序，請識別哪些應用程式正在使用的檔案，以及控制程序和服務。

  - **可靠性分析元件**是內建代理程式上，提供詳細的經驗資訊系統使用狀況和可靠性。 這項資訊公開 WMI 介面，以使其可耗用透過可攜式讀者系統。 藉由透過 WMI 介面公開可靠性分析元件，開發人員可以監視及分析應用程式、 增加可靠性和效能。

  - **Windows Server 2008 R2**使用內建的可靠性分析元件來計算可靠性索引中，提供一段時間整體系統使用狀況] 和 [穩定性的相關資訊。 可靠性分析元件也會追蹤的系統，可能會影響所展現的穩定性，例如 Windows 更新和應用程式安裝任何重要變更。

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 可靠性和效能監視器

Windows 可靠性和效能監視器是 MMC 嵌入式管理單元，結合了前一個獨立的工具，包括效能記錄檔和提醒、 伺服器效能顧問，以及系統監視器的功能。 它提供圖形化介面自訂效能資料收集和事件追蹤工作階段。

它還包含可靠性監視器] MMC 嵌入式管理單元中，系統會追蹤的變更，然後比較它們變更在系統所展現的穩定性，並提供其關聯的一種圖形檢視。

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 可靠性和效能監視器

Windows 可靠性和效能監視器結合例如效能記錄檔及警示和系統監視器和伺服器效能顧問某些離職獨立工具的功能，它還提供一些新功能至 Windows Server 2008 和Windows Server 2008 R2，如下所示：

  - 資料收集器集合工具

  - [資源] 檢視

  - 可靠性監視器

  - 精靈和範本來建立記錄檔

**資料收集器集合工具**資料收集器群組到可重複使用元素搭配不同的效能監視案例。 一群資料收集器儲存為資料收集器集合工具之後，作業，例如排程可以套用至整個集透過單一屬性變更。Windows 可靠性和效能監視器包含預設資料收集器集合範本，可協助系統管理員開始立即收集效能資料的特定伺服器角色或監視案例。

[首頁] 頁面上的 Windows 可靠性和效能監視器是新的 **[資源] 檢視**畫面，可提供 CPU、 磁碟、 網路和記憶體使用量的即時圖形化概觀。 藉由展開每個這些受監視的項目，系統管理員可以識別哪一個程序所使用的資源。 在舊版 Windows 中，此即時、 程序特有的資料是只能在有限的表單在 [工作管理員] 中。

**可靠性監視器**計算反映未預期的問題是否降低系統的可靠性系統所展現的穩定性索引。 經過一段時間的穩定性索引圖形快速識別問題開始發生時的日期。 隨附的系統所展現的穩定性報告提供詳細資料] 來協助疑難排解降低可靠性的原因。 藉由檢視變更為並排失敗 （應用程式故障、 作業系統損毀或硬體故障），系統 （安裝或移除應用程式、 更新作業系統，或是新增或修改驅動程式） 的策略解決問題可以快速地開發。

新增的計數器，以記錄檔及排程其開始、 停止]，並持續時間現在可透過**精靈介面**來執行。 此外，這種組態儲存為範本可讓系統管理員收集相同的記錄在其他電腦上沒有重複的資料收集器選取範圍和排程處理程序。 效能記錄檔及警示功能會併入 「 Windows 可靠性和效能監視器搭配任何資料收集器集合工具。

</div>

</div>

<span> </span>

</div>

</div>

</div>

