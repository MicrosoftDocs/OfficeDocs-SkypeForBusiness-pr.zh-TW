---
title: Lync Server 2013 硬體負載平衡器需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bb8c3ff97930411cb8d679054015ffc18ab3ce2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013 的硬體負載平衡器需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-11_

Lync Server 2013 調整式合併 Edge 拓撲已針對新部署的 DNS 負載平衡進行優化，主要與使用 Lync Server 的其他組織合作。 如果在下列任一情況下需要高可用性，則必須在 Edge Server 集區上使用硬體負載平衡器予以因應：

  - 與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟

  - Exchange 2010 與 SP1 前使用 Exchange UM 的遠端使用者 exchange UM

  - 公用 IM 使用者的連線

<div>


> [!IMPORTANT]  
> 不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。



</div>

<div>


> [!NOTE]  
> 在您使用硬體負載平衡器時，針對內部網路的連線所部署的負載平衡器必須經過設定，使其僅對流向執行 Access Edge Service 與 A/V Edge Service 之伺服器的流量執行負載平衡。對於流向內部 Web Conferencing Edge Service 或內部 XMPP Proxy 服務的流量，不可執行負載平衡。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支援 direct server return (DSR) NAT。



</div>

若要判斷您的硬體負載平衡器是否支援 Lync Server 2013 所需的必要功能，請參閱 at 中的「Lync Server 2010 負載平衡器合作夥伴」 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>執行 A/V Edge Service 之 Edge Server 的硬體負載平衡器需求

以下是執行 A/V Edge service 之 Edge Server 的硬體負載平衡器需求：

  - 關閉內部及外部連接埠 443 的 TCP Nagling。Nagling 是一種程序，將數個小型封包合併為較大型的單一封包以進行有效傳輸。

  - 關閉外部連接埠範圍 50,000 - 59,999 的 TCP Nagling。

  - 不要在內部或外部防火牆上使用 NAT。

  - Edge 內部介面必須與 Edge 外部介面位在不同的網路上，而且必須停用在它們之間進行的路由傳送作業。

  - 執行 A/V Edge Service 之 Edge Server 的外部介面必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

在 Web 服務的 Lync Server 2013 中，會大幅減少 Cookie 基礎的親近性需求。 如果您部署的是 Lync Server 2013，而且不會保留任何 Lync Server 2010 前端伺服器或前端集區，則不需要以 cookie 為基礎的持久性集。 不過，如果您暫時或永久保留任何 Lync Server 2010 前端伺服器或前端集區，您仍會使用以 cookie 為基礎的持久性，因為它是針對 Lync Server 2010 部署及設定。

<div>


> [!NOTE]  
> <STRONG>如果您決定使用 Cookie 型相似性 (即使您的部署不需要它)</STRONG>，則這樣做並不會產生任何負面影響。



</div>

針對**不使用** Cookie 型相似性的部署：

  - 在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。

針對**將使用** Cookie 型相似性的部署：

  - 在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。

  - 硬體負載平衡器 Cookie「絕不能」標示為 httpOnly

  - 硬體負載平衡器 Cookie「絕不能」有到期時間

  - 硬體負載平衡器 Cookie「必須」命名為 **MS-WSMAN** (此為 Web 服務預期的值且無法變更)

  - 無論該相同 TCP 連線上先前的 HTTP 回應是否已取得 Cookie，在傳入 HTTP 要求沒有 Cookie 的每個 HTTP 回應中，都「必須」設定硬體負載平衡器 Cookie。如果負載平衡器將 Cookie 插入最佳化成針對每個 TCP 連線只出現一次，則「絕不能」使用該最佳化

<div>


> [!NOTE]  
> 一般硬體負載平衡器設定會使用來源位址親近性和20分鐘的 TCP 會話壽命，這對 Lync Server 和 Lync 2013 用戶端而言是很好的，因為會話狀態是透過用戶端使用方式和/或應用程式互動來維護。



</div>

如果您正在部署行動裝置，硬體負載平衡器就必須能夠在 TCP 工作階段中負載平衡個別要求 (實際上，您必須能夠根據目標 IP 位址來負載平衡個別要求)。

<div>


> [!WARNING]  
> F5 硬體負載平衡器有一項叫做 OneConnect 的功能，可以確保 TCP 連線中的每個要求都能個別負載平衡。如果您正在部署行動裝置，請確定硬體負載平衡器廠商支援相同的功能。最新版的 Apple iOS 行動應用程式需要傳輸層安全性 (TLS) 版本 1.2。F5 提供適用於此版本的特殊設定。<BR>如需協力廠商硬體負載平衡器的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

下面是 Director 與前端集區 Web 服務的硬體負載平衡器需求：

  - 針對 [內部 Web 服務] Vip，設定 \_ 硬體負載平衡器上的 [來源位址] 持久性 (內部埠80，443) 。 針對 Lync Server 2013，來源 \_ 位址暫留表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器以維護會話狀態。

  - 使用 TCP 閒置逾時：1800 秒。

  - 在反向 Proxy 與下一個躍點集區之硬體負載平衡器間的防火牆上，建立允許 https 的規則：連接埠 4443 上從反向 Proxy 到硬體負載平衡器的流量。硬體負載平衡器必須設定成接聽連接埠 80、443 及 4443。

<div>


> [!IMPORTANT]  
> 如需硬體負載平衡器設定的進一步閱讀，請參閱通訊<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-調整式合併 edge （在 Lync Server 2013 中使用硬體負載平衡</A>器）。



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬體負載平衡器相似性需求摘要


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端/使用者位置</th>
<th>外部 Web 服務 FQDN 相似性需求</th>
<th>內部 Web 服務 FQDN 相似性需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (內部及外部使用者) </p>
<p>行動裝置 (內部和外部使用者)</p></td>
<td><p>無相似性</p></td>
<td><p>來源位址相似性</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (僅限外部使用者) </p>
<p>行動裝置 (內部和外部使用者)</p></td>
<td><p>無相似性</p></td>
<td><p>來源位址相似性</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (僅限內部使用者) </p>
<p>行動裝置 (未部署)</p></td>
<td><p>無相似性</p></td>
<td><p>來源位址相似性</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>適用於硬體負載平衡器的連接埠監控

您可以在硬體負載平衡器上定義連接埠監控，以判斷特定的服務何時因為發生硬體或通訊失敗而無法使用。 例如，如果前端伺服器服務 (RTCSRV) 停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。 您可以在 HLB 上實作連接埠監控以監控下列各項：

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>前端伺服器使用者集區– HLB 內部介面

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>虛擬 IP/連接埠</th>
<th>節點連接埠</th>
<th>節點電腦/監視器</th>
<th>持續性設定檔</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;集區 &gt; web int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>來源</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="even">
<td><p>&lt;集區 &gt; web int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>來源</p></td>
<td><p>HTTP:</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>前端伺服器使用者集區– HLB 外部介面

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>虛擬 IP/連接埠</th>
<th>節點連接埠</th>
<th>節點電腦/監視器</th>
<th>持續性設定檔</th>
<th>附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;集區 &gt; web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>無</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="even">
<td><p>&lt;集區 &gt; web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>無</p></td>
<td><p>HTTP:</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

