---
title: Lync Server 2013： DNS 摘要-反向 proxy
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a468e74206fdc6bad8f078267688450636b8a725
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532140"
---
# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Lync Server 2013 中的 DNS 摘要-反向 proxy

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-22_

您可以在反向 Proxy 上設定兩片網路介面卡，如下所示：

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>反向 Proxy 網路介面卡需求

  - **網路介面卡 1 (內部介面)** 範例
    
    已指派 172.25.33.40 的內部介面。
    
    未定義預設閘道。
    
    確定有從包含反向 proxy 內部介面的網路到包含 Lync Server 前端集區伺服器的任何網路的路由 (例如，從172.25.33.0 到 192.168.10.0) 。

  - **網路介面卡 2 (外部介面)** 範例
    
    至少指派一個公用 IP 位址給這個網路介面卡。
    
    已將閘道定義為指向您外部周邊中的路由器或整合式防火牆 (此範例中為 10.45.16.1)。

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
<th>FQDN</th>
<th>IP 位址</th>
<th>對應至/註解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>從內部部署到外部 Web 服務。您可為所有集區及單一伺服器，針對要使用此反向 Proxy，且具有已定義之外部 Web 服務的 SIP 網域，定義及建立其他記錄。</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>部署中 Director 或 Director 集區的外部 web 服務。 您可以定義多個具有不同 Director 的 Director，其可能會與其他 SIP 網域產生關聯。</p>
<div>

> [!IMPORTANT]  
> 定義及發佈 Director 的 DNS 記錄不是前端集區或 Director 決定。 如果您使用 Director，則必須定義及發佈 Director 和前端集區外部 web 服務。 若要將特定流量類型 (用於驗證及其他使用) ，請先將它傳送給 Director （如果是在拓撲中定義）。


</div></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>電話撥入式會議已對外發行</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>已對外發行會議</p></td>
</tr>
<tr class="odd">
<td><p>外部 DNS/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Office Web Apps Server 的指派監聽器</p></td>
<td><p>Office Web Apps Server 內部部署或在周邊環境中部署，並已發佈供外部用戶端存取</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>Lync 探索外部發佈 AutoDiscover 的外部記錄，並包含行動性、Microsoft Lync Web App 及排程器 Web app</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

