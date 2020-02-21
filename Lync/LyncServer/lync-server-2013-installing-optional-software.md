---
title: Lync Server 2013： 安裝選用軟體
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
ms.openlocfilehash: 2ce81d2005a9bbed5432f2c78f3d8df5507d6679
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a>Lync Server 2013 中安裝選用軟體

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

Microsoft Lync Server 2013、 規劃工具的設計匯出至 Microsoft Excel 與 Microsoft Visio。 這些應用程式都不是必要的規劃工具的作業時，它們不要加入重大值的部署與您的設計的文件。

<div>

## <a name="optional-software"></a>選用軟體

<div>

## <a name="microsoft-excel"></a>Microsoft Excel

將您的設計匯出至 Microsoft Excel 會建立一份報告，顯示在試算表中的七個索引標籤：

  - 摘要 – 顯示有關網站組態，包括使用者計數、 容量設定，以及伺服器設定檔資訊。

  - 硬體設定檔 – 顯示報表上的拓撲，包括 CPU、 記憶體、 磁碟，以及網路介面中指定的伺服器的建議的硬體組態。 數量及建議的規格的伺服器元件也會是包含項目。 此外，每一部伺服器是由網站，以提供完整的伺服器需求呈現網站所定義。

  - 連接埠需求 – 網域名稱系統負載平衡 (DNS LB) 和硬體負載平衡器 (HLB) 將會顯示所有已啟用的連接埠和關聯的報告。 您應該使用此報告來規劃您的防火牆和 DNS LB 和 HLB 組態。

  - 摘要報告 – 顯示一般，才能設定 Edge Server 網路設定的摘要。

  - 憑證報表 – 顯示主旨名稱及所要執行的 Edge 伺服器所需的憑證的主體替代名稱。

  - 防火牆報告 – 顯示來源和目的地連接埠和 IP 位址的外部及內部介面。

  - DNS 報告 – 顯示的完整的網域名稱 (FQDN) 與 IP/VIP 位址所需的每個 DNS 項目，您建立。

</div>

<div>

## <a name="microsoft-visio"></a>Microsoft Visio

將您的設計匯出至 Microsoft Visio 會在您的文件目的，您設定的拓撲和基礎結構中建立用於圖表。 匯入的圖表可以編輯，而且以符合您的文件需要重新排列。 會包含在一般的 Visio 圖表：

<div>


> [!NOTE]  
> 如果您的設計規模夠大，需要超過三個前端伺服器，一個額外的頁面會建立前端集區，前端伺服器，執行 SQL Server、 IP 位址和 Fqdn 的電腦。



</div>

  - 通用拓撲 – 已設定 Lync Server 2013 網站的圖表。

  - 網站名稱] 索引標籤 – 顯示站台組態拓撲與 Edge 伺服器、 防火牆、 公用交換電話網路 (PSTN) 閘道，與內部伺服器部署。 在內部部署設定的伺服器所組成與集區，包括前端集區，SQL Server 型伺服器、 Active Directory 網域服務、 Director、 Exchange 整合通訊 (UM) 伺服器，Exchange 信箱伺服器，Office Web Apps Server，中繼伺服器和 Persistent Chat Server。

  - Edge 網狀圖 – 圖詳述相關聯的 IP 位址和 Fqdn 的 Edge Server 組態。 DNS 負載平衡與硬體負載平衡器也會包含。 此外，Director 與前端伺服器或前端集區，以顯示相關聯的 DNS LB 或 HLB （規劃工具支援 IPv4 和 IPv6 地址） 指派的 IP 位址和 FQDN。

</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中安裝規劃工具](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

