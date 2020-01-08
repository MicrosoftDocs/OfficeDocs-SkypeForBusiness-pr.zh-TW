---
title: Lync Server 2013：安裝選用軟體
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6723d005a41b52025c7e3e475bc3b3a108f2c3d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>在 Lync Server 2013 中安裝選用軟體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

Microsoft Lync Server 2013、規劃工具的設計目的是匯出至 Microsoft Excel 和 Microsoft Visio。 雖然這些應用程式不是規劃工具運作所必需的，但它們確實會為您設計的部署和檔加上重要的價值。

<div>

## <a name="optional-software"></a>選用軟體

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

將您的設計匯出至 Microsoft Excel 時，會建立一個顯示試算表中七個索引標籤的報表：

  - 摘要–顯示網站設定的相關資訊，包括使用者計數、容量設定和伺服器設定檔資訊。

  - 硬體設定檔–針對拓撲中指定的伺服器（包括 CPU、記憶體、磁片和網路介面），顯示建議的硬體設定報告。 也包含伺服器元件的數量及建議的規格。 此外，每個伺服器都是由網站定義，以根據網站提供伺服器需求的完整表示。

  - 埠需求–顯示所有已啟用埠的報告，以及與網域名稱系統負載平衡（DNS LB）與硬體負載平衡器（HLB）的關聯。 您應該使用這個報告來規劃您的防火牆和 DNS LB 及 HLB 設定。

  - 摘要報告–顯示設定 Edge 伺服器網路所需設定的一般摘要。

  - [憑證報告] –顯示在執行邊緣伺服器所需的憑證所需的消費者名稱和消費者替代名稱。

  - Firewall 報告–顯示外部和內部介面的來源和目的地埠和 IP 位址。

  - DNS 報告–顯示您所建立之每個 DNS 專案所需的完整功能變數名稱（FQDN）和 IP/VIP 位址。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

將您的設計匯出至 Microsoft Visio，就會建立圖表，以供您設定的拓撲和基礎結構的檔用途使用。 您可以編輯和重新排列已匯入的圖表，以符合您的檔需求。 典型的 Visio 圖表會包括：

<div>


> [!NOTE]  
> 如果您的設計足夠大，需要超過三個前端伺服器，則會針對前端池、前端伺服器、執行 SQL Server 的電腦、IP 位址及 Fqdn，建立額外的頁面。



</div>

  - [全域拓撲]-已設定 Lync Server 2013 網站的圖表。

  - [網站名稱] 索引標籤–顯示含 Edge 伺服器、防火牆、公開交換電話網絡（PSTN）與內部伺服器部署的網站配置拓撲。 內部部署由已設定的伺服器和池組成，包括前端池、SQL Server 服務器、Active Directory 網域服務、控制器、Exchange 整合通訊（UM）伺服器、Exchange 信箱伺服器、Office Web Apps 伺服器、中繼伺服器和持續聊天伺服器。

  - [邊緣網狀圖]-詳細說明邊緣伺服器設定與相關聯的 IP 位址和 Fqdn 的圖表。 也包含 DNS 負載平衡與硬體負載平衡器。 此外，會顯示 [控制器] 與 [前端伺服器] 或 [頂層端] 池，其中包含相關聯的 DNS LB 或 HLB 以及指派的 IP 位址（規劃工具支援 IPv4 與 IPv6 位址）和 FQDN。

</div>

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中安裝規劃工具](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

