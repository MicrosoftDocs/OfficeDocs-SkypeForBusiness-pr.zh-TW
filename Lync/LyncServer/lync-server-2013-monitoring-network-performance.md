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
ms.openlocfilehash: efeba476609ad293cd94e67f8dfdbe674b42f3f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500640"
---
# <a name="monitoring-network-performance-in-lync-server-2013"></a>在 Lync Server 2013 中監控網路效能

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-27_

Lync Server 2013 是一種即時通訊技術，其主要是透過網路來啟用使用者之間的通訊，既可以透過立即訊息 (IM) 、語音通話或視頻通訊。 因此，請務必連續監視網路效能，以協助確保使用者選擇的通訊形式可提供最佳的體驗。

網路效能的衡量可以是兩個層級：

  - **整體網路效能**    這種效能測量層級可讓組織建立其網路的「大圖片」視圖，通常是透過協力廠商網路監控系統來執行。 這些系統會接收來自遠端網路裝置（例如路由器）上的效能及容量資料，以供系統管理員在一天中的任何時間決定任何指定網路元件的健康情況。

  - **個別的伺服器效能**    這層級的效能測量會限制在特定伺服器上，並可協助系統管理員 gauging 特定伺服器的網路效能，以協助疑難排解特定效能問題，或在指定期間內評估各伺服器的效能，做為容量規劃程式的一部分。

您可以使用下列各節所述的工具來監視網路。

<div>

## <a name="tools-for-overall-network-performance-monitoring"></a>整體網路效能監控工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 提供端對端的服務管理，便於自訂及擴充，以改善整個 IT 環境中的服務等級。 這可讓作業和 IT 管理小組識別及解決影響分散式 IT 服務健康情況的問題。 端對端服務管理不受限於以 Microsoft 為基礎的環境。 支援管理的 Web 服務 (WS-MANAGEMENT) 、簡易網路管理通訊協定 (SNMP) 及夥伴解決方案，都可以在 System Center Operations Manager 2012 內的服務監視中包含未執行 Microsoft 作業系統和硬體的系統。

</div>

<div>

## <a name="system-center-operations-manager-2012-and-third-party-network-management-solutions"></a>System Center Operations Manager 2012 及 Third-Party 網路管理解決方案

**EMC Smarts**    EMC 的 Operations Manager 解決方案可協助您快速解決整個中影響服務層級的問題。 透過使用 EMC 的 Operations Manager 解決方案，您可以使用一個整合、自動化的解決方案，管理及監視整個 IT 服務鏈。 您可以輕鬆識別效能及可用性問題的根本原因，並更快地解決影響和成本。 主要優點包括下列各項：

  - 高級、便於使用的管理著重于提供戰略性的商業價值，而不是手動排序和篩選混亂的警示。

  - **更快的解析度**    更快速地解決 IT 問題，並回應業務需求，以降低影響及成本。

  - **精簡作業**    結合多個管理工具、應用程式和終端，避免 IT 複雜性。

您可以在以下位置找到相關資訊：

[Microsoft System Center Operations Manager](https://go.microsoft.com/fwlink/p/?linkid=243651)

[Microsoft System Center Operations Manager 的解決方案](http://www.emc.com/collateral/software/data-sheet/h6135-server-manager-ds.pdf)

</div>

<div>

## <a name="third-party-solutions"></a>Third-Party 解決方案

**Hp 網路管理中心 (之前稱為 hp OpenView) **    [hp 網路管理中心](http://www8.hp.com/us/en/software-solutions/network-management/index.html?%26zn=bto%26cp=1-11-15-119_4000_100__)提供整合式的故障和效能管理，以提升網路可用性和效能。 網路管理中心是 HP 自動化網路管理解決方案的一部分，可統一執行錯誤、效能、設定及變更管理。

**Cisco 網路管理和自動化產品**    針對企業，Cisco 具有數個可供使用的管理產品，包括 CiscoWorks LAN 管理解決方案和 Cisco 網路分析模組，以協助改善操作效率並減少網路停機時間。 如需這些產品的其他資料，請參閱 Cisco 網站，網址為 [https://www.cisco.com/en/US/products/sw/netmgtsw/index.html](https://www.cisco.com/en/us/products/sw/netmgtsw/index.html) 。

簡易網路管理通訊協定 (SNMP) 簡易網路管理通訊協定 (SNMP) 是網路管理標準，用來定義管理 TCP/IP 網路的策略。 SNMP 可讓您捕獲網路的設定和狀態資訊，並將資訊傳送至指定的電腦，以進行事件監視。 這種以標準為基礎的網路管理通訊協定使用分散式架構，其中包括下列各項：

  - 多個受管理的節點，每個都有一個稱為「代理程式」的 SNMP 實體，可提供管理規範的遠端存取。

  - 至少有一個 SNMP 實體稱為管理員，它會執行管理應用程式來監視和控制受管理的元素。 Managed 元素是主機、路由器等裝置。 他們會透過存取其管理資訊來加以監控和控制。

  - 管理通訊協定（SNMP）是用來在管理工作站和代理程式之間交流管理資訊。 管理資訊指的是即時于虛擬資訊儲存區（稱為「管理資訊基底 (MIB) ）中的受管理物件集合。

<div>


> [!NOTE]  
> 以上提供協力廠商網路監視解決方案的範例。 此清單並不是明確的，Microsoft 不會優選任何特定的廠商解決方案。 請與網路服務提供者和您的各技術供應商協商，以判斷貴組織的最佳網路監控解決方案。



</div>

</div>

</div>

<div>

## <a name="tools-for-monitoring-individual-server-network-performance"></a>監視個別伺服器網路效能的工具

<div>

## <a name="system-center-operations-manager-2012"></a>System Center Operations Manager 2012

System Center Operations Manager 2012 可讓系統管理員透過 Windows Server 2012 管理元件來查看個別伺服器的網路效能： Windows Server 作業系統管理元件包括「效能」管理元件，可讓系統管理員監視網路介面卡的效能和配接器健康情況。

</div>

<div>

## <a name="windows-network-monitor"></a>Windows 網路監視器

會收集、顯示、分析伺服器上的資源使用狀況，並測量網路流量。 網路監視器會以獨佔方式監視網路活動。 透過捕獲和分析網路資料，並使用這些資料搭配效能記錄，您可以判斷網路使用量、識別網路問題，以及預測未來的網路需求。

如需網路監視器3.4 的詳細資訊，以及若要瞭解如何安裝及設定網路監視器及捕獲和分析資料，請複查此會話：網路監視器3.3 簡介。 此外，請複查 [網路監視器博客](https://blogs.technet.com/b/netmon/)。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

