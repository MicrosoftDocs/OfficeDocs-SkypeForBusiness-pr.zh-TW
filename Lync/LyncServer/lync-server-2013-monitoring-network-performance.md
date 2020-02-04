---
title: Lync Server 2013：監控網路效能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring network performance
ms:assetid: bc3a01da-91eb-4c0c-9598-35e5e46b00f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720923(v=OCS.15)
ms:contentKeyID: 63969647
ms.date: 04/27/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 504b0c28e42b6975cd411c6628cd9f91a30783ef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-network-performance-in-lync-server-2013"></a>監控 Lync Server 2013 中的網路效能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-27_

Lync Server 2013 是一種即時通訊技術，主要是依靠網路來啟用使用者之間的通訊，不論是透過立即訊息（IM）、語音通話或視頻通訊。 因此，請務必連續監視網路效能，以協助保證使用者所選擇的通訊類型能提供最佳的最佳體驗。

網路效能可以衡量為兩個層次：

  - **整體網路效能**   此效能測量層級可讓組織建立其網路的「大型圖片」視圖，通常是透過協力廠商網路監視系統來實現。 這些系統會從遠端網路裝置（例如路由器）傳送效能與容量資料，並在整個網路中切換，以允許系統管理員在一天的任何時間決定任何指定網路元件的健康情況。

  - **個別伺服器效能**   此等級的效能測量值僅限於特定的伺服器，並可協助系統管理員測量特定伺服器的網路效能，以協助您解決特定效能問題，或在指定期間內測量各個伺服器的效能，做為容量規劃流程的一部分。

您可以使用下列各節所述的工具來監控網路。

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>整個網路效能監控工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

系統中心作業管理員可提供端對端的服務管理，輕鬆進行自訂並延伸以改善整個 IT 環境的服務層級。 這可讓操作和 IT 管理小組找出並解決影響分散式 IT 服務健康情況的問題。 端對端服務管理不受限於以 Microsoft 為基礎的環境。 支援 Web 服務以進行管理（WS-MANAGEMENT）、簡單網路管理通訊協定（SNMP），以及合作夥伴解決方案，讓未執行 Microsoft 作業系統的系統和硬體都包含在 System Center 的服務監視中Operations Manager 2012。

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 和協力廠商網路管理解決方案

**Emc Smarts**   emc 針對 Operations Manager 的解決方案可協助您快速解決影響整個服務層級的問題。 透過使用 EMC 針對 Operations Manager 的解決方案，您可以使用一個整合、自動化的解決方案來管理和監控整個 IT 服務鏈。 您可以輕鬆找出效能和可用性問題的根本原因，並以更快的速度來解決，以減少效果和成本。 主要優點包括下列各項：

  - 先進、便於使用的管理重點是提供戰略商業價值，而不是手動排序及篩選混亂的警示。

  - **更快速的解析度**   可解決 IT 問題，並以更快的速度回應業務需求，減少效果和成本。

  - **簡化的作業**   會結合多個管理工具、應用程式和終端來避免 IT 複雜性。

您可以在以下網址找到詳細資訊：

[Microsoft System Center Operations Manager](http://go.microsoft.com/fwlink/p/?linkid=243651)

[Microsoft System Center Operations Manager 的解決方案](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>協力廠商解決方案

**Hp 網路管理中心（先前稱為 HP OpenView）**   [Hp 網路管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供整合的故障與效能管理，以改善網路可用性與效能。 網路管理中心是 HP 自動化網路管理解決方案的一部分，可將故障、效能、配置及變更管理功能統一。

**企業版 cisco 網路管理和自動化產品**   提供了數種管理產品，包括 CiscoWorks LAN 管理解決方案和 Cisco 網路分析模組，以協助改善運營效率並減少網路停機時間。 如需這些產品的其他資料，請參閱 Cisco 網站[http://www.cisco.com/en/US/products/sw/netmgtsw/index.html](http://www.cisco.com/en/us/products/sw/netmgtsw/index.html)。

簡單網路管理通訊協定（SNMP）簡單網路管理通訊協定（SNMP）是定義管理 TCP/IP 網路之策略的網路管理標準。 SNMP 可讓您捕獲網路的設定和狀態資訊，並將資訊傳送至指定的電腦，以進行事件監視。 這個基於標準的網路管理通訊協定使用分散式體系結構，包括下列各項：

  - 多個受管理的節點，每一個都有一個名為代理的 SNMP 實體，可提供管理工具的遠端存取權。

  - 至少一個名為 manager 的 SNMP 實體稱為管理員，可執行管理應用程式來監視及控制受管理的元素。 受管理的元素是主機、路由器等裝置。 它們會透過存取其管理資訊來加以監視及控制。

  - 管理通訊協定（SNMP）是用來在管理工作站與代理程式之間傳達管理資訊。 管理資訊指的是駐留在虛擬資訊儲存區中的受管理物件集合，稱為管理資訊基礎（MIB）。

<div>


> [!NOTE]  
> 上面提供了協力廠商網路監視解決方案的範例。 此清單不是明確的，而且 Microsoft 不會優選任何特定的供應商方案。 諮詢網路服務提供者，或您的技術供應商，以判斷貴組織的最佳網路監視解決方案。



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>監視個別伺服器網路效能的工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

系統中心作業管理器2012可讓管理員透過 Windows Server 2012 管理套件來查看個別伺服器的網路效能： Windows Server 作業系統管理套件包含「效能」管理套件這可讓系統管理員監視網路介面卡的效能和配接器健康情況。

</div>

<div>

## <a name="windows-network-monitor"></a>Windows 網路監視器

收集、顯示、分析伺服器上的資源使用量，並測量網路流量。 網路監視器只會監視網路活動。 透過捕獲及分析網路資料，並在效能記錄中使用此資料，您可以判斷網路使用量、識別網路問題，以及預測未來的網路需求。

如需網路監視器3.4 的詳細資訊，以及如何安裝及設定網路監視器以及捕獲及分析資料，請參閱此會話：網路監視器3.3 概覽。 此外，請參閱[網路監視器博客](http://blogs.technet.com/b/netmon/)。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

