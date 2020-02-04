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
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Lync Server 2013 的硬體負載平衡器需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2015-05-11_

Lync Server 2013 縮放的合併邊緣拓朴已針對新部署的 DNS 負載平衡進行優化，主要與使用 Lync Server 的其他組織聯盟。 如果下列任何案例都需要高可用性，則必須在 Edge 伺服器池中使用硬體負載平衡器，以進行下列作業：

  - 與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟

  - 在 Exchange 2010 之前使用 Exchange UM 的遠端使用者的 exchange UM 與 SP1

  - 公用 IM 使用者的連線能力

<div>


> [!IMPORTANT]  
> 在一個介面上使用 DNS 負載平衡，而另一個介面上的硬體負載平衡則不受支援。 您必須針對兩種介面或 DNS 負載平衡使用硬體負載平衡。



</div>

<div>


> [!NOTE]  
> 如果您使用的是硬體負載平衡器，則必須將與內部網路的連線所部署的負載平衡器設定為只進行負載平衡，以便只對執行存取邊緣服務和 A/V 邊緣服務的伺服器進行負載平衡。 它無法將流量負載平衡到內部網路會議邊緣服務或內部 XMPP Proxy 服務。



</div>

<div>


> [!NOTE]  
> Lync Server 2013 不支援直接伺服器返回（DSR） NAT。



</div>

若要判斷您的硬體負載平衡器是否支援 Lync Server 2013 所需的必要功能，請參閱「Lync Server 2010 負載[http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)平衡器合作夥伴」。

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求

以下是執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求：

  - 針對內部和外部埠443關閉 TCP Nagling。 Nagling 是將數個小型資料包合併成單一、較大的資料包以獲得更有效率的傳輸的程式。

  - 關閉外部埠範圍50000–59999的 TCP Nagling。

  - 請勿在內部或外部防火牆上使用 NAT。

  - Edge 內部介面必須在不同的網路上，而不是 Edge 伺服器外部介面且必須停用它們之間的路由。

  - 執行 A/V 邊緣服務的邊緣伺服器外部介面必須使用可公開路由的 IP 位址，而且任何邊緣外部 IP 位址都沒有 NAT 或埠轉譯。

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>硬體負載平衡器需求

在 Lync Server 2013 for Web 服務中，以 Cookie 為基礎的關聯需求大大減少。 如果您要部署 Lync Server 2013，且不會保留任何 Lync Server 2010 前端伺服器或前端池，則不需要以 cookie 為基礎的持久性。 不過，如果您要暫時或永久保留任何 Lync Server 2010 前端伺服器或前端池，您仍然會在針對 Lync Server 2010 部署和設定的情況下，使用以 cookie 為基礎的持久性。

<div>


> [!NOTE]  
> <STRONG>如果您決定使用以 cookie 為基礎的關聯，即使您的部署不需要它</STRONG>，也不會有任何負面影響可執行此動作。



</div>

針對**將不會使用**cookie 的關聯的部署：

  - 在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。 這可確保原始 URL 已轉寄。

針對**將使用**以 cookie 為基礎的關聯性的部署：

  - 在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。 這可確保原始 URL 已轉寄。

  - 硬體負載平衡器 cookie 不能標示為 HTTPOnly

  - 硬體負載平衡器 cookie 不能有到期時間

  - 硬體負載平衡器 cookie 必須命名為**MS-WSMAN** （這是 Web 服務預期的值，且無法變更）

  - 硬體負載平衡器 cookie 必須在每一個 HTTP 回應中設定（無論是否已在相同的 TCP 連線中先前的 HTTP 回應都已取得 cookie）。 如果負載平衡器針對每個 TCP 連線優化 cookie 插入，則不一定要使用該優化

<div>


> [!NOTE]  
> 典型的硬體負載平衡器設定使用來源位址關聯和20分鐘的 TCP 會話存留期，這對 Lync Server 和 Lync 2013 用戶端來說是很好的，因為會話狀態是透過用戶端使用量和/或應用程式互動來維護。



</div>

如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 會話中的個別要求之間進行負載平衡（事實上，您必須能夠根據目標 IP 位址來載入個別的要求）。

<div>


> [!WARNING]  
> F5 硬體負載平衡器具有一個名為 [OneConnect] 的功能，可確保 TCP 連線中的每個要求都有個別的負載平衡。 如果您要部署行動裝置，請確保您的硬體負載平衡器供應商支援相同的功能。 最新的 Apple iOS 行動裝置 app 需要傳輸層安全性（TLS）版本1.2。 F5 會針對此提供特定設定。<BR>如需協力廠商硬體負載平衡器的詳細資料，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

以下是控制器和前臺端池 Web 服務的硬體負載平衡器需求：

  - 針對內部 Web 服務 Vip，請在\_硬體負載平衡器上設定源位址持久性（內部埠80，443）。 在 Lync Server 2013 中，\_來源位址暫留代表來自單一 IP 位址的多個連線，會一直傳送到一個伺服器，以維持會話狀態。

  - 使用1800秒的 TCP 空閒超時。

  - 在反向 proxy 與下一個躍點池的硬體負載平衡器之間，建立規則來允許 HTTPs：埠4443上的流量，從反向 proxy 傳送到硬體負載平衡器。 硬體負載平衡器必須設定為在埠80、443和4443上聆聽。

<div>


> [!IMPORTANT]  
> 如需進一步瞭解硬體負載平衡器的設定，請參閱<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-在 Lync Server 2013 中使用硬體負載平衡器進行合併的合併邊緣</A>。



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>硬體負載平衡器關聯需求摘要


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端/使用者位置</th>
<th>外部 web 服務 FQDN 關聯需求</th>
<th>內部 web 服務 FQDN 關聯需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App （內部與外部使用者）</p>
<p>行動裝置（內部和外部使用者）</p></td>
<td><p>沒有關聯性</p></td>
<td><p>來源位址關聯</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App （僅限外部使用者）</p>
<p>行動裝置（內部和外部使用者）</p></td>
<td><p>沒有關聯性</p></td>
<td><p>來源位址關聯</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App （僅限內部使用者）</p>
<p>行動裝置（未部署）</p></td>
<td><p>沒有關聯性</p></td>
<td><p>來源位址關聯</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>硬體負載平衡器的埠監控

您可以在硬體負載平衡器上定義埠監視，以判斷因硬體或通訊失敗而無法使用特定服務的時間。 例如，如果前端伺服器或前端池發生故障，[前端伺服器服務（RTCSRV）] 停止，則 HLB 監視也應該停止在 Web 服務上接收流量。 您可以在 HLB 上執行埠監視，以監視下列各項：

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>前端伺服器使用者池– HLB 內部介面

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
<th>虛擬 IP/埠</th>
<th>節點埠</th>
<th>節點電腦/監視器</th>
<th>持久性設定檔</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;網路&gt;池網頁-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>從源</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;網路&gt;池網頁-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>從源</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>前端伺服器使用者池– HLB 外部介面

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
<th>虛擬 IP/埠</th>
<th>節點埠</th>
<th>節點電腦/監視器</th>
<th>持久性設定檔</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>無</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>前端</p>
<p>5061</p></td>
<td><p>無</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

