---
title: Lync Server 2013：內部伺服器的埠和通訊協定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Ports and protocols for internal servers
ms:assetid: c94063f1-e802-4a61-be90-022fc185335e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398833(v=OCS.15)
ms:contentKeyID: 48185402
ms.date: 04/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1001cce83d9b23125b177725c77715bd19a00e03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 內部伺服器的埠和通訊協定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-06_

本節摘要說明伺服器、負載平衡器和 Lync Server 部署中的用戶端所使用的埠和通訊協定。

<div>


> [!IMPORTANT]  
> 當 Lync 與 Communicator 用戶端參與單一通訊時，通常稱為對等。 從技術角度來看，兩個用戶端都是以單一交談的方式進行通訊，中間是中間的立即訊息 multipoint 控制項單位（IMMCU）。 IMMCU 是前端伺服器的元件。 將 IMMCU 放在所需的通訊工作流程中，即可允許通話詳細資料錄製，以及前端伺服器所能啟用的其他功能。 通訊來自用戶端上的動態來源埠到前端伺服器埠 TLS/TCP/5061 （假設使用建議的傳輸層安全性）。 透過設計、對等通訊（以及多方 IM），只有當 Lync Server 與 IMMCU 處於作用中且可用時，才可以使用。



</div>

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

<div>


> [!NOTE]  
> 在伺服器上啟動 Lync Server services 之前，Windows 防火牆必須執行，因為 Lync Server 在防火牆中開啟必要的埠。



</div>

如需有關 edge 元件防火牆設定的詳細資料，請參閱[判斷 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

下表列出每個內部伺服器角色上需要開啟的埠。

### <a name="required-server-ports-by-server-role"></a>所需的伺服器埠（依伺服器角色）

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
<th>伺服器角色</th>
<th>服務名稱</th>
<th>通道</th>
<th>通訊協定</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>所有伺服器</p></td>
<td><p>SQL 瀏覽器</p></td>
<td><p>1434</p></td>
<td><p>UDP-IN</p></td>
<td><p>中央管理儲存資料庫的本機複製複本的 SQL 瀏覽器。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>5060</p></td>
<td><p>TCP-OUT</p></td>
<td><p>您也可以選擇將標準版伺服器與前端伺服器（例如遠端通話控制伺服器）的靜態路由使用。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>5061</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>由標準版伺服器和前端池使用，可用於伺服器與用戶端（MTLS）之間的所有內部 SIP 通訊，以及前端伺服器與中繼伺服器（MTLS）之間的 SIP 通訊。 也用於與監控伺服器進行通訊。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>444</p></td>
<td><p>IP-HTTPS</p>
<p>TCP-OUT</p></td>
<td><p>用於焦點（管理會議狀態的 Lync 伺服器元件）與個別伺服器之間的 HTTPS 通訊。</p>
<p>此埠也用於 Survivable 分支裝置與前端伺服器之間的 TCP 通訊。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>135</p></td>
<td><p>DCOM 與遠端程式通話（RPC）</p></td>
<td><p>用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製程式同步處理和通訊錄同步處理。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server IM 會議服務</p></td>
<td><p>5062</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於立即訊息（IM）會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 會議服務</p></td>
<td><p>8057</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用來偵聽來自用戶端的永久性共用物件模型（PSOM）連線。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 會議相容性服務</p></td>
<td><p>8058</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用來從 Live Meeting 用戶端和舊版的 Lync Server，偵聽永久共用物件模型（PSOM）連線。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 音訊/視訊會議服務</p></td>
<td><p>5063</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於音訊/視頻（A/V）會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 音訊/視訊會議服務</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>用於視訊會議的媒體埠範圍。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
<td><p>用於從前端伺服器到網路伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url），在未使用 HTTPS 時進行通訊。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
<td><p>用來從前端伺服器與網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）進行通訊。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>8080</p></td>
<td><p>TCP 與 HTTP</p></td>
<td><p>供外部存取的網頁元件使用。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Web 服務器元件</p></td>
<td><p>4443</p></td>
<td><p>IP-HTTPS</p></td>
<td><p>HTTPS （從反向 Proxy）與 HTTPS 前端端池通訊，以進行自動探索登入。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Web 服務器元件</p></td>
<td><p>8060</p></td>
<td><p>TCP （MTLS）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Web 服務器元件</p></td>
<td><p>8061</p></td>
<td><p>TCP （MTLS）</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>5086</p></td>
<td><p>TCP （MTLS）</p></td>
<td><p>行動服務內部程式使用的 SIP 埠</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>5087</p></td>
<td><p>TCP （MTLS）</p></td>
<td><p>行動服務內部程式使用的 SIP 埠</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議助理服務（電話撥入式會議）</p></td>
<td><p>5064</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於電話撥入式會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議助理服務（電話撥入式會議）</p></td>
<td><p>5072</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於接聽的傳入 SIP 要求（撥入會議）。</p></td>
</tr>
<tr class="even">
<td><p>同時執行 Collocated 轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5070</p></td>
<td><p>TCP-OUT</p></td>
<td><p>供中繼伺服器用來將前端伺服器的傳入要求傳送到中繼伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>同時執行 Collocated 轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5067</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</p></td>
</tr>
<tr class="even">
<td><p>同時執行 Collocated 轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5068</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用來將 PSTN 閘道的傳入 SIP 要求傳送到轉送伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>同時執行 Collocated 轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5081</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>同時執行 Collocated 轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5082</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用於從中繼伺服器到 PSTN 閘道的傳出 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 應用程式共用服務</p></td>
<td><p>5065</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於應用程式共用的傳入 SIP 偵聽要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 應用程式共用服務</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用來共用應用程式的媒體埠範圍。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議宣告服務</p></td>
<td><p>5073</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於 Lync Server 會議宣告服務的傳入 SIP 要求（也就是電話撥入式會議）。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 通話寄存服務</p></td>
<td><p>5075</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於來電寄存應用程式的內送 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 音訊測試服務</p></td>
<td><p>5076</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於音訊測試服務的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>不適用</p></td>
<td><p>5066</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於輸出增強型9-1-1 （E9-1-1）閘道。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 回應群組服務</p></td>
<td><p>5071</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於回應群組應用程式的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 回應群組服務</p></td>
<td><p>8404</p></td>
<td><p>TCP （MTLS）</p></td>
<td><p>用於回應群組應用程式的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 頻寬原則服務</p></td>
<td><p>5080</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於由頻寬原則服務為 A/V 邊緣開啟流量的呼叫許可控制。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 頻寬原則服務</p></td>
<td><p>448</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於 Lync Server 頻寬策略服務的呼叫許可控制。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理儲存所在的前端伺服器</p></td>
<td><p>Lync Server 主版複製程式代理服務</p></td>
<td><p>445</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用來將配置資料從中央管理存儲推送到執行 Lync Server 的伺服器。</p></td>
</tr>
<tr class="even">
<td><p>所有伺服器</p></td>
<td><p>SQL 瀏覽器</p></td>
<td><p>1434</p></td>
<td><p>UDP-IN</p></td>
<td><p>本機 SQL Server 實例中的中央管理儲存在本機複製複本的 SQL 瀏覽器</p></td>
</tr>
<tr class="odd">
<td><p>所有內部伺服器</p></td>
<td><p>各種各樣</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>在所有內部伺服器上，音訊會議所用的媒體埠範圍。 是由所有終止音訊的伺服器所使用：前端伺服器（適用于 Lync Server 會議助理服務、Lync Server 會議宣告服務，以及 Lync server 音訊/視訊會議服務）及中繼伺服器。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps 伺服器</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>由 Lync Server 2013 用來連線到 Office Web Apps 伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>5060</p></td>
<td><p>TCP-OUT</p></td>
<td><p>您也可以選擇將靜態路由用於受信任的服務，例如遠端通話控制伺服器。</p></td>
</tr>
<tr class="even">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>444</p></td>
<td><p>IP-HTTPS</p>
<p>TCP-OUT</p></td>
<td><p>前端與控制器之間的伺服器間通訊。 此外，用戶端憑證發佈（到前端伺服器）或驗證用戶端憑證是否已發佈。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>80</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於從董事到網頁伺服器陣列 Fqdn （IIS 網頁元件所使用的 Url）的初始通訊。 在 [標準] 操作中，會使用埠443和通訊協定類型 TCP，切換到 HTTPS 流量。</p></td>
</tr>
<tr class="even">
<td><p>控制器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
<td><p>用於從控制器到網頁伺服器陣列 Fqdn （IIS 網頁元件所用的 Url）的通訊。</p></td>
</tr>
<tr class="odd">
<td><p>控制器</p></td>
<td><p>Lync Server 前端服務</p></td>
<td><p>5061</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於伺服器與用戶端連線之間的內部通訊。</p></td>
</tr>
<tr class="even">
<td><p>中繼伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5070</p></td>
<td><p>TCP-OUT</p></td>
<td><p>由中繼伺服器用於來自前端伺服器的傳入要求。</p></td>
</tr>
<tr class="odd">
<td><p>中繼伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5067</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用於來自 PSTN 閘道的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>中繼伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5068</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於來自 PSTN 閘道的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>中繼伺服器</p></td>
<td><p>Lync Server 轉送服務</p></td>
<td><p>5070</p></td>
<td><p>TCP （MTLS）</p></td>
<td><p>用於來自前端伺服器的 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>持續聊天前端伺服器</p></td>
<td><p>持續聊天 SIP</p></td>
<td><p>5041</p></td>
<td><p>TCP （MTLS）</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>持續聊天前端伺服器</p></td>
<td><p>持續聊天 Windows Communication Foundation （WCF）</p></td>
<td><p>881</p></td>
<td><p>TCP （TLS）和 TCP （MTLS）</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>持續聊天前端伺服器</p></td>
<td><p>持續聊天檔案傳輸服務</p></td>
<td><p>443</p></td>
<td><p>TCP （TLS）</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 某些遠端呼叫控制案例需要在前端伺服器或控制器與 PBX 之間建立 TCP 連線。 雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，這會將 RCC 線路伺服器 FQDN 與前端伺服器或控制器用來連接 PBX 系統的 TCP 埠產生關聯。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的<STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。



</div>

針對只使用硬體負載平衡的池（而非 DNS 負載平衡），下表顯示需要開啟硬體負載平衡器的埠。

### <a name="hardware-load-balancer-ports-if-using-only-hardware-load-balancing"></a>硬體負載平衡器埠（如果只使用硬體負載平衡）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>負載平衡器</th>
<th>通道</th>
<th>通訊協定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5061</p></td>
<td><p>TCP （TLS）</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>444</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>135</p></td>
<td><p>DCOM 與遠端程式通話（RPC）</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>8080</p></td>
<td><p>從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS （從反向 proxy）</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5072</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5073</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5075</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5076</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5071</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5080</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>448</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="odd">
<td><p>中繼伺服器負載平衡器</p></td>
<td><p>5070</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器（如果該池也會執行轉送伺服器）</p></td>
<td><p>5070</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="odd">
<td><p>控制器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td><p>控制器負載平衡器</p></td>
<td><p>444</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>控制器負載平衡器</p></td>
<td><p>5061</p></td>
<td><p>TCP-OUT</p></td>
</tr>
<tr class="even">
<td><p>控制器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS （從反向 proxy）</p></td>
</tr>
</tbody>
</table>


您的前端池和使用 DNS 負載平衡的控制器池也必須部署硬體負載平衡器。 下表顯示在這些硬體負載平衡器上需要開啟的埠。

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>使用 DNS 負載平衡的硬體負載平衡器埠

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>負載平衡器</th>
<th>通道</th>
<th>通訊協定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>8080</p></td>
<td><p>從前臺伺服器（即由 NTLM 驗證的用戶端和裝置）對根憑證的 TCP 用戶端和裝置檢索</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS （從反向 proxy）</p></td>
</tr>
<tr class="odd">
<td><p>控制器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>IP-HTTPS</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>控制器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>HTTPS （從反向 proxy）</p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>所需的用戶端埠

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>元件</th>
<th>通道</th>
<th>通訊協定</th>
<th>筆記</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>台</p></td>
<td><p>67/68</p></td>
<td><p>動態</p></td>
<td><p>由 Lync Server 用來尋找註冊機 FQDN （也就是如果 DNS SRV 失敗且沒有設定手動設定）。</p></td>
</tr>
<tr class="even">
<td><p>台</p></td>
<td><p>443</p></td>
<td><p>TCP （TLS）</p></td>
<td><p>用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>443</p></td>
<td><p>TCP （PSOM/TLS）</p></td>
<td><p>用於外部使用者存取網路會議會話。</p></td>
</tr>
<tr class="even">
<td><p>台</p></td>
<td><p>443</p></td>
<td><p>TCP （STUN/MSTURN）</p></td>
<td><p>供外部使用者存取 A/V 會話及媒體（TCP）</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>3478</p></td>
<td><p>UDP （STUN/MSTURN）</p></td>
<td><p>供外部使用者存取 A/V 會話及媒體（UDP）</p></td>
</tr>
<tr class="even">
<td><p>台</p></td>
<td><p>5061</p></td>
<td><p>TCP （MTLS）</p></td>
<td><p>用於用戶端到伺服器的 SIP 流量，以供外部使用者存取。</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP-OUT</p></td>
<td><p>用於 Lync 用戶端與舊版用戶端之間的檔案傳輸（Microsoft Office 通訊伺服器 2007 R2 的用戶端、Microsoft Office 通訊伺服器2007，以及即時通訊伺服器2005）。</p></td>
</tr>
<tr class="even">
<td><p>台</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>音訊埠範圍（所需的最小20個埠）</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>影片埠範圍（需要20個埠的最小值）。</p></td>
</tr>
<tr class="even">
<td><p>台</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP-OUT</p></td>
<td><p>對等檔案傳輸（適用于會議檔案傳輸，用戶端使用 PSOM）。</p></td>
</tr>
<tr class="odd">
<td><p>台</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP-OUT</p></td>
<td><p>應用程式共用。</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip 常見區域電話</p>
<p>Aastra 6725ip phone</p>
<p>HP 4110 IP Phone （通用區域電話）</p>
<p>HP 4120 IP Phone （辦公桌電話）</p>
<p>Polycom CX500 IP 常見區域電話</p>
<p>Polycom CX600 IP 電話機</p>
<p>Polycom CX700 IP 電話機</p>
<p>Polycom CX3000 IP 會議電話</p></td>
<td><p>67/68</p></td>
<td><p>動態</p></td>
<td><p>由所列的裝置使用，以尋找 Lync 伺服器憑證、資源調配 FQDN 和註冊機 FQDN。</p></td>
</tr>
</tbody>
</table>


**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet （ClientMediaPortRangeEnabled、ClientMediaPort 和 ClientMediaPortRange 參數）。

<div>


> [!NOTE]  
> Lync 用戶端的設定程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。



</div>

<div>


> [!NOTE]  
> 在用戶端必須遍歷組織的防火牆（例如，任何外部通訊或其他組織託管的會議）的情況下，對於外部使用者存取所用的埠，都是必要的。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

