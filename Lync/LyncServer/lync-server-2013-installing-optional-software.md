---
title: Lync Server 2013：安裝選用軟體
description: Lync Server 2013：安裝選用軟體。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7423c0d54b762fb4af7cedc8d7ba8745fd94bdf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573909"
---
# <a name="installing-optional-software-in-lync-server-2013"></a>在 Lync Server 2013 中安裝選用軟體

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

規劃工具是設計用來匯出至 Microsoft Excel 和 Microsoft Visio 的 Microsoft Lync Server 2013。 雖然不需要在規劃工具作業時執行這些應用程式，但是會為部署和設計的檔增加重要的價值。

<div>

## <a name="optional-software"></a>選用軟體

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

將設計匯出至 Microsoft Excel 會建立一個報告，該報告會顯示試算表中的七個索引標籤：

  - 摘要–顯示網站設定的資訊，包括使用者計數、容量設定和伺服器設定檔資訊。

  - 硬體設定檔–針對拓撲中指定的伺服器（包括 CPU、記憶體、磁片及網路介面），顯示建議硬體設定的報告。 此外，也包含伺服器元件的數量和建議規格。 此外，每個伺服器都是由網站定義，以透過網站提供伺服器需求的完整標記法。

  - 埠需求–顯示所有已啟用的埠報告，以及與網域名稱系統負載平衡 (DNS LB) 和硬體負載平衡器 (HLB) 的關聯。 您應該使用此報告規劃您的防火牆和 DNS LB 和 HLB 設定。

  - 摘要報告–顯示設定 Edge Server 網路所需之設定的一般摘要。

  - 憑證報告–顯示取得執行 Edge Server 所需之憑證所需的主體名稱和主體替代名稱。

  - 防火牆報告–顯示外部及內部介面的來源和目的地埠及 IP 位址。

  - DNS 報告–顯示您所建立之每個 DNS 專案所需的完整功能變數名稱 (FQDN) 和 IP/VIP 位址。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

將您的設計匯出至 Microsoft Visio，會建立圖表，以供您設定的拓撲和基礎結構的檔目的使用。 您可以編輯並重新排列已匯入的圖表，以符合您的檔需求。 典型的 Visio 圖表會包含：

<div>


> [!NOTE]  
> 如果您的設計足夠大，需要超過三部前端伺服器，則會為前端集區、前端伺服器、執行 SQL Server 的電腦、IP 位址和 Fqdn 建立額外的頁面。



</div>

  - 通用拓撲–設定的 Lync Server 2013 網站圖表。

  - [網站名稱] 索引標籤–顯示與 Edge Server、防火牆、公用交換電話網路 (PSTN) 搭配閘道和內部伺服器部署的網站設定拓撲。 內部部署包含已設定的伺服器及集區，包括前端集區、SQL Server 型伺服器、Active Directory 網域服務、Director、Exchange 整合通訊 (UM) 伺服器、Exchange 信箱伺服器、Office Web Apps Server、轉送伺服器及 Persistent Chat Server。

  - Edge Network 圖表–詳述具有關聯之 IP 位址和 Fqdn 之 Edge Server 設定的圖表。 此外，也包含 DNS 負載平衡與硬體負載平衡器。 此外，會顯示 Director 和前端伺服器或前端集區，並有相關聯的 DNS LB 或 HLB，以及已指派的 IP 位址 (規劃工具可同時支援 IPv4 和 IPv6 位址) 和 FQDN。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中安裝規劃工具](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

