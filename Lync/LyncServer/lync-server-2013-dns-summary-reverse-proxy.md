---
title: 'Lync Server 2013: DNS 摘要-反向 proxy'
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
ms.openlocfilehash: fde945b4bd08020a072f36be073169454e423279
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>DNS 摘要-Lync Server 2013 中的反向 proxy

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-22_

您可以在反向 Proxy 上設定兩片網路介面卡，如下所示：

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>反向 Proxy 網路介面卡需求

  - **網路介面卡 1 (內部介面)** 範例
    
    已指派 172.25.33.40 的內部介面。
    
    未定義預設閘道。
    
    確定從內含反向 proxy 內部介面的網路，到內含 Lync Server 前端集區伺服器 （例如，從 172.25.33.0 到 192.168.10.0) 的網路路由。

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
<th>位置/類型/連接埠</th>
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
<td><p>外部 web 服務的 Director 或 Director 集區部署中。 您可以定義為多個 Director 都有不同的 Director，其中可能會與其他 SIP 網域相關聯。</p>
<div>

> [!IMPORTANT]  
> 定義 DNS 的記錄，且發佈 Director 不可以是前端集區或 Director 決策。 您必須定義並發行 Director 與前端集區的外部 web 服務，如果您使用 Director。 特定的流量類型 （適用於驗證和其他用途） 會被傳送給 Director 首先，如果它定義在拓撲中。


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
<td><p>Office Web Apps server 的指派接聽程式</p></td>
<td><p>Office Web Apps Server 部署在內部或在周邊網路，並為外部用戶端存取發行</p></td>
</tr>
<tr class="even">
<td><p>外部 DNS/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>為對外發佈的資源指派聆聽程式</p></td>
<td><p>Lync Discover External 記錄的外部發行之自動探索，以及包括行動性、 Microsoft Lync Web App，以及排程器 Web 應用程式</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

