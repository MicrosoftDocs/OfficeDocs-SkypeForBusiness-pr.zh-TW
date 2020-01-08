---
title: Lync Server 2013：DNS 摘要 - 反向 Proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要 - 反向 Proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-22_

您可以在反向 proxy 中設定兩個網路介面卡，如下所示：

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>反向 Proxy 網路介面卡需求

  - **網路介面卡1（內部介面）** 範例
    
    已指派172.25.33.40 的內部介面。
    
    未定義預設閘道。
    
    請確定有一個從網路的路由，包含對包含 Lync Server 前端池伺服器的任何網路（例如從172.25.33.0 到192.168.10.0）的反向 proxy 內部介面。

  - **網路介面卡2（外部介面）** 範例
    
    至少已將一個公用 IP 位址指派給此網路介面卡。
    
    閘道定義為指向外部週邊中的路由器或整合式防火牆。 （案例範例中的10.45.16.1）

### <a name="dns-records-required-for-reverse-proxy"></a>反向 Proxy 所需的 DNS 記錄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>位置/類型/埠</th>
<th>稱</th>
<th>IP 位址</th>
<th>地圖/批註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>外部發佈資源的指派監聽程式</p></td>
<td><p>內部部署的外部 web 服務。 您可以針對任何要使用此反向 proxy 的 SIP 網域，為所有的 pool 和單一伺服器定義及建立其他記錄，並已定義外部 web 服務。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>外部發佈資源的指派監聽程式</p></td>
<td><p>您部署中的控制器或控制器池的外部 web 服務。 您可以定義多個控制器，因為有不同的控制器，可能會與其他 SIP 網域產生關聯。</p>
<div>

> [!IMPORTANT]  
> 定義及發佈主管的 DNS 記錄並不是前端池或主管決策。 如果您使用的是董事，您必須定義併發布主管和前端池外部 web 服務。 特定流量類型（針對驗證及其他用途）會先傳送給主管（如果它是在拓撲中定義）。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>外部發佈資源的指派監聽程式</p></td>
<td><p>外部發佈的電話撥入式會議</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>外部發佈資源的指派監聽程式</p></td>
<td><p>外部發佈的會議</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>已指派給 Office Web Apps Server 的偵聽程式</p></td>
<td><p>Office Web Apps 伺服器是在內部部署或在週邊部署，且已針對外部用戶端存取發佈</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>外部發佈資源的指派監聽程式</p></td>
<td><p>Lync 探索外部發佈的自動探索的外部記錄，並包含行動性、Microsoft Lync Web App 及排程程式 Web 應用程式</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

