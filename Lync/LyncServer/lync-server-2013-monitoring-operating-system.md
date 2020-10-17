---
title: Lync Server 2013：監控作業系統
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
ms.openlocfilehash: 8d6cad561761b7387cb4c268229f76b52f4bd24b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500630"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a>Lync Server 2013 中的監控作業系統

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

您必須監視 Lync Server 2013 中所有伺服器與元件的效能。 顯然，其中一個最重要的元件是作業系統本身。 Lync Server 2013 支援 x64 版本：

  - Windows Server 2008 R2

  - Windows Server 2012 和 Windows Server 2012 R2

監視作業系統最透明的方式是使用 Windows Server 作業系統管理套件。 它可提供執行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 之電腦的基礎監控基礎，例如效能、健康情況及可用性。

透過偵測、警示及自動回應重要的事件和效能指標，這些管理元件可減少問題的解決時間，並增加執行 Windows Server 作業系統之系統的整體可用性和效能。

除了相關的 Windows Server management pack for System Center Operations Manager 之外，下列系統工具和資源可用於監視作業系統 (的健康情況，視作業系統版本) 而定。

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 包含下列其他功能和工具，可協助系統管理員進行基本作業系統監控和管理：

  - **Windows Resource Monitor** 是一種強大的工具，可讓您瞭解程式和服務如何使用系統資源。 除了即時監控資源使用量之外，資源監視器也可協助分析無回應的處理常式、識別哪些應用程式正在使用檔案，以及控制程式和服務。

  - **可靠性分析元件** 是一個內建的代理程式，提供系統使用狀況與可靠性的詳細體驗資訊。 此資訊透過 WMI 介面公開，可供可擕式讀取器系統使用。 透過 WMI 介面公開可靠性分析元件，開發人員可以監視及分析應用程式，進而增強可靠性和效能。

  - **Windows Server 2008 R2** 使用內建的可靠性分析元件來計算可靠性索引，其可提供一段時間內整體系統使用量和穩定性的相關資訊。 可靠性分析元件也會持續追蹤可能會影響穩定性的任何重要變更，例如 Windows 更新和應用程式安裝。

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 可靠性和效能監視器

Windows 可靠性和效能監視器是一種 MMC 嵌入式管理單元，結合了舊獨立工具的功能，包括效能記錄和警示、伺服器效能顧問和系統監視器。 它會提供圖形介面，以自訂效能資料收集和事件追蹤會話。

此外，它也包含可靠性監視器，也就是追蹤系統變更的 MMC 嵌入式管理單元，並比較系統穩定性的變化，並提供其關聯的圖形化視圖。

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 可靠性和效能監視器

雖然 Windows 可靠性和效能監視器會結合一些先前獨立工具（例如效能記錄和警示）和系統監視器與伺服器效能顧問的功能，但也會提供一些新功能給 Windows Server 2008 和 Windows Server 2008 R2，例如：

  - 資料收集器集

  - 資源檢視

  - 可靠性監視器

  - 用於建立記錄的嚮導與範本

**資料收集器集會將** 資料收集器群組成可重複使用的元素，以用於不同的效能監視案例。 在將一組資料收集器儲存為資料收集器集後，可透過單一屬性變更將作業（例如排程）套用至整個集。Windows 可靠性和效能監視器包含預設的資料收集器集範本，可協助系統管理員立即開始收集伺服器角色或監控案例特有的效能資料。

Windows 可靠性和效能監視器的首頁是新的 [ **資源 View** ] 畫面，可提供 CPU、磁片、網路及記憶體使用量的即時圖形概述。 透過展開每個受監視的元素，系統管理員便可識別哪些處理常式正在使用哪些資源。 在舊版 Windows 中，只有在工作管理員的有限表單中，才可取得處理常式特有的資料。

**可靠性監視器** 會計算系統穩定性指數，反映未預期的問題是否會降低系統的可靠性。 一段時間的穩定性索引圖表會快速識別發生問題的日期。 伴隨的系統穩定性報告提供詳細資料，可協助疑難排解可靠性降低的原因。 透過查看系統的變更 (安裝或移除應用程式、作業系統的更新，或新增或修改驅動程式) 並排存在失敗 (應用程式失敗、作業系統損毀或硬體失敗) ，您可以快速開發解決問題的策略。

現在可以透過 **嚮導介面**，將計數器新增至記錄檔並排程其開始、停止和持續時間。 此外，將此設定另存為範本，可讓系統管理員在其他電腦上收集相同的記錄，而不需重複資料收集器選取及排程處理常式。 效能記錄和警示功能已融入 Windows 可靠性和效能監視器中，以用於任何資料收集器集。

</div>

</div>

<span> </span>

</div>

</div>

</div>

