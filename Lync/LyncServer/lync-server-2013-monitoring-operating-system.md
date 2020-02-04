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
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a>Lync Server 2013 中的監控作業系統

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-01-26_

您必須監視 Lync Server 2013 中所有伺服器與元件的效能。 很明顯地，其中一個最重要的元件就是作業系統本身。 Lync Server 2013 支援 x64 版本的：

  - Windows Server 2008 R2

  - Windows Server 2012 和 Windows Server 2012 R2

若要監視作業系統，最透明的方法是使用 Windows Server 作業系統管理套件。 它提供執行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 之電腦的效能、健康情況及可用性等基本監視基礎。

透過檢測、觸發及自動回應重要的事件和效能指標，這些管理套件減少了問題的解決時間，並增加執行 Windows Server 的系統的整體可用性與效能作業系統。

除了適用于 System Center Operations Manager 的相關 Windows Server management pack 之外，下列系統工具和資源可用於監視作業系統的健康情況（視作業系統版本而定）。

<div>

## <a name="windows-server2008r2"></a>Windows Server 2008 R2

Windows Server 2008 R2 包含下列其他功能與工具，可協助系統管理員進行基本的作業系統監視與管理：

  - **Windows 資源監視器**  是一款強大的工具，可讓您透過程序和服務瞭解系統資源的使用情況。除了即時監控資源使用量之外，資源監視器還能協助分析無回應的程序、找出哪些應用程式在使用檔案，並控制程序與服務。

  - **可靠性分析元件** 是一款隨附的代理程式，可提供系統使用量和可靠性的詳細體驗資訊。這項資訊會透過 WMI 介面公開，讓可攜式讀取器系統使用。透過 WMI 介面公開可靠性分析元件，開發人員就能監控並分析應用程式，增加可靠性和效能。

  - **Windows Server 2008 R2**使用內建的可靠性分析元件來計算可靠性索引，這會提供總體系統使用方式及時間的穩定性資訊。 The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a>Windows Server 2008 Windows 可靠性和效能監視器

Windows 可靠性和效能監視器是一款 MMC 嵌入式管理單元，結合了先前的獨立工具的功能，包括效能記錄和警示、伺服器效能顧問及系統監視器。其提供圖形介面供自訂效能資料收集和事件追蹤工作階段。

其也包含可靠性監視器，這是一款 MMC 嵌入式管理單元，可追蹤系統變更並與系統穩定性的變更作比較，並提供關係圖檢視。

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a>Windows 可靠性和效能監視器

雖然 Windows 可靠性和效能監視器結合了一些舊版獨立工具（例如效能記錄和警報）的功能，以及系統監視器和伺服器效能審察程式，但它也提供一些新功能給 Windows Server 2008，並Windows Server 2008 R2，如下所示：

  - 資料收集器集

  - 資源檢視

  - 可靠性監視器

  - 建立記錄的精靈和範本

**資料收集器集**會將資料收集器分組成可重複使用的元素，以搭配其他效能監控案例使用。將資料收集器的群組儲存為資料收集器集之後，像是排程這類作業，只要變更單一屬性就能套用至整個集。Windows 可靠性和效能監視器包含預設的資料收集器集範本，可協助系統管理員立即開始收集對伺服器角色或監控案例特定的效能資料。

Windows 可靠性和效能監視器的首頁是全新的**資源檢視**畫面，其中提供 CPU、磁碟、網路和記憶體使用量的即時圖形概觀。展開每個監控的元素之後，系統管理員就能找出哪些程序在使用哪些資源。在舊版 Windows 中，這項即時的程序特定資料於 [工作管理員] 中為限定使用的。

**可靠性監視器** 會計算系統穩定性指數，以反映出未預期的問題是否降低系統的可靠性。隨時間的穩定性指數圖表可快速找出開始發生問題的日期。隨附的系統穩定性報告則可提供詳細資料，以協助疑難排解降低可靠性的原因。透過並行檢視系統變更 (安裝或移除應用程式、更新作業系統或新增或修改驅動程式) 和故障 (應用程式故障、作業系統當機或硬體故障) 情形，就能快速制定解決問題的策略。

將計數器新增至記錄檔並排程其開始、停止和持續期間等這些動作，現在可透過**精靈介面**來執行。除此之外，將此設定另存為範本還能讓系統管理員在其他電腦上收集相同的記錄，而不必重複資料收集器選擇和排程程序。效能記錄和警示功能已併入 Windows 可靠性和效能監視器中，可搭配任何資料收集器集使用。

</div>

</div>

<span> </span>

</div>

</div>

</div>

