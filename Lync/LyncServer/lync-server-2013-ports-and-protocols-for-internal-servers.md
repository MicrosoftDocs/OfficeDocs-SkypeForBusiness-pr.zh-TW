---
title: Lync Server 2013：內部伺服器的埠與通訊協定
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
ms.openlocfilehash: 858ec90cf3811318cc29a902b56ac8ff31c46a22
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513400"
---
# <a name="ports-and-protocols-for-internal-servers-in-lync-server-2013"></a>Lync Server 2013 中內部伺服器的埠與通訊協定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-04-06_

本節摘要說明 Lync Server 部署中的伺服器、負載平衡器和用戶端所使用的埠和通訊協定。

<div>


> [!IMPORTANT]  
> Lync 和 Communicator 用戶端與單一通訊相關時，通常稱為對等。 從技術角度來看，這兩個用戶端是透過單一交談進行通訊，而立即訊息 multipoint control unit (IMMCU) 中間。 IMMCU 是前端伺服器的元件。 在所需的通訊工作流程中放置 IMMCU，可讓您在前端伺服器上啟用詳細通話記錄及其他功能。 通訊來自用戶端的動態來源埠至前端伺服器埠 TLS/TCP/5061 (假設使用建議的傳輸層安全性) 。 根據設計，對等通訊 (，而且只有在 Lync Server 和 IMMCU 為使用中且可用時，才可以進行多方的 IM) 。



</div>

<div>

## <a name="port-and-protocol-details"></a>埠與通訊協定詳細資料

<div>


> [!NOTE]  
> 在伺服器上啟動 Lync Server 服務之前，必須先執行 Windows 防火牆，因為這是 Lync Server 在防火牆中開啟必要的埠。



</div>

如需 edge 元件的防火牆設定的詳細資訊，請參閱 [決定 Lync Server 2013 的外部 A/V 防火牆和埠需求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

下表列出每個內部伺服器角色上必須開啟的埠。

### <a name="required-server-ports-by-server-role"></a>伺服器角色所 (的必要伺服器埠) 

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
<th>連接埠</th>
<th>Protocol (通訊協定)</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>所有伺服器</p></td>
<td><p>SQL 瀏覽器</p></td>
<td><p>1434</p></td>
<td><p>Udp</p></td>
<td><p>SQL Browser 的中央管理存放區資料庫本地複寫複本。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>可選擇性地由 Standard Edition server 和前端伺服器用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>由 Standard Edition server 和前端集區用於伺服器 (MTLS) 、伺服器與用戶端之間的 SIP 通訊 (TLS) 及前端伺服器與轉送伺服器之間的 SIP 通訊 (MTLS) 。 也用於與監控伺服器的通訊。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>444</p></td>
<td><p>HTTPS:</p>
<p>TCP</p></td>
<td><p>用於管理會議狀態) 和個別伺服器的焦點 (Lync Server 元件之間的 HTTPS 通訊。</p>
<p>此埠也用於 Survivable 分支裝置和前端伺服器之間的 TCP 通訊。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>135</p></td>
<td><p>DCOM 和遠端過程呼叫 (RPC) </p></td>
<td><p>用於以 DCOM 為基礎的作業，例如移動使用者、使用者複製器同步處理及通訊錄同步處理。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server IM 會議服務</p></td>
<td><p>5062</p></td>
<td><p>TCP</p></td>
<td><p>用於立即訊息 (IM) 會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 會議服務</p></td>
<td><p>8057</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於聆聽持續性共用物件模型 (PSOM) 來自用戶端的連線。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 會議相容性服務</p></td>
<td><p>8058</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於聆聽持續性共用物件模型 (從 Live Meeting 用戶端和舊版的 Lync Server PSOM) 連線。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Audio/Video 會議服務</p></td>
<td><p>5063</p></td>
<td><p>TCP</p></td>
<td><p>用於音訊/視頻 (A/V) 會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Audio/Video 會議服務</p></td>
<td><p>57501-65535</p></td>
<td><p>TCP/UDP</p></td>
<td><p>用於視訊會議的媒體埠範圍。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>80</p></td>
<td><p>HTTP:</p></td>
<td><p>用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 不使用 HTTPS 時。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
<td><p>用於從前端伺服器到網頁伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>8080</p></td>
<td><p>TCP 和 HTTP</p></td>
<td><p>供外部存取的 web 元件使用。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>網頁伺服器元件</p></td>
<td><p>4443</p></td>
<td><p>HTTPS:</p></td>
<td><p>HTTPS (，來自反向 Proxy) 與 HTTPS 前端集區間的自動探索登入通訊。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>網頁伺服器元件</p></td>
<td><p>8060</p></td>
<td><p>TCP (MTLS) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>網頁伺服器元件</p></td>
<td><p>8061</p></td>
<td><p>TCP (MTLS) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>5086</p></td>
<td><p>TCP (MTLS) </p></td>
<td><p>行動服務內部程式使用的 SIP 埠</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>5087</p></td>
<td><p>TCP (MTLS) </p></td>
<td><p>行動服務內部程式使用的 SIP 埠</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>行動服務元件</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議助理服務 (電話撥入式會議) </p></td>
<td><p>5064</p></td>
<td><p>TCP</p></td>
<td><p>用於電話撥入式會議的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議助理服務 (電話撥入式會議) </p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
<td><p>用於在會議) 中傳入的 SIP 要求 (撥號語音應答。</p></td>
</tr>
<tr class="even">
<td><p>同時執行組合轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>由轉送伺服器用於來自前端伺服器到轉送伺服器的傳入要求。</p></td>
</tr>
<tr class="odd">
<td><p>同時執行組合轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>同時執行組合轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>用於從 PSTN 閘道到轉送伺服器的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>同時執行組合轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5081</p></td>
<td><p>TCP</p></td>
<td><p>用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>同時執行組合轉送伺服器的前端伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5082</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於從轉送伺服器到 PSTN 閘道的傳出 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 應用程式共用服務</p></td>
<td><p>5065</p></td>
<td><p>TCP</p></td>
<td><p>用於應用程式共用的傳入 SIP 聆聽要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 應用程式共用服務</p></td>
<td><p>49152-65535</p></td>
<td><p>TCP</p></td>
<td><p>用於應用程式共用的媒體埠範圍。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 會議宣告服務</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
<td><p>用於 Lync Server 會議宣告服務 (的傳入 SIP 要求，也就是用於電話撥入式會議) 。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 通話駐留服務</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
<td><p>用於通話駐留應用程式的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 音訊測試服務</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
<td><p>用於音訊測試服務的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>不適用</p></td>
<td><p>5066</p></td>
<td><p>TCP</p></td>
<td><p>用於輸出增強型 9-1-1 (E9-1-1) 閘道。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 回應群組服務</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
<td><p>用於回應群組應用程式的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 回應群組服務</p></td>
<td><p>8404</p></td>
<td><p>TCP (MTLS) </p></td>
<td><p>用於回應群組應用程式的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 頻寬原則服務</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
<td><p>用於 A/V Edge 輪流流量的頻寬原則服務的通話許可控制。</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器</p></td>
<td><p>Lync Server 頻寬原則服務</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
<td><p>Lync Server 頻寬原則服務用於通話許可控制。</p></td>
</tr>
<tr class="odd">
<td><p>中央管理存放區所在的前端伺服器</p></td>
<td><p>Lync Server 主複製器代理程式服務</p></td>
<td><p>445</p></td>
<td><p>TCP</p></td>
<td><p>用來將設定資料從中央管理存放區推入執行 Lync Server 的伺服器。</p></td>
</tr>
<tr class="even">
<td><p>所有伺服器</p></td>
<td><p>SQL 瀏覽器</p></td>
<td><p>1434</p></td>
<td><p>Udp</p></td>
<td><p>本機 SQL Server 實例中中央管理存放區資料的本機複製副本的 SQL 瀏覽器</p></td>
</tr>
<tr class="odd">
<td><p>所有內部伺服器</p></td>
<td><p>各種</p></td>
<td><p>49152-57500</p></td>
<td><p>TCP/UDP</p></td>
<td><p>用於所有內部伺服器的音訊會議的媒體埠範圍。 由終止音訊的所有伺服器使用：前端伺服器 (的 Lync Server 會議應答服務、Lync Server 會議宣告服務，以及 Lync Server Audio/Video 會議服務) 和轉送伺服器。</p></td>
</tr>
<tr class="even">
<td><p>Office Web Apps Server</p></td>
<td></td>
<td><p>443</p></td>
<td></td>
<td><p>由 Lync Server 2013 用來連線到 Office Web Apps Server。</p></td>
</tr>
<tr class="odd">
<td><p>董事</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>5060</p></td>
<td><p>TCP</p></td>
<td><p>選擇性地用於信任服務的靜態路由，例如遠端呼叫控制伺服器。</p></td>
</tr>
<tr class="even">
<td><p>董事</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>444</p></td>
<td><p>HTTPS:</p>
<p>TCP</p></td>
<td><p>前端和 Director 之間的伺服器間通訊。 此外，用戶端憑證發行 (至前端伺服器) 或驗證是否已發佈用戶端憑證。</p></td>
</tr>
<tr class="odd">
<td><p>董事</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>80</p></td>
<td><p>TCP</p></td>
<td><p>用於從 Director 到 web 伺服器陣列 Fqdn (的初始通訊) IIS web 元件所使用的 URLs。 在正常作業中，會使用埠443和通訊協定類型 TCP 切換到 HTTPS 流量。</p></td>
</tr>
<tr class="even">
<td><p>董事</p></td>
<td><p>Lync Server Web 相容性服務</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
<td><p>用於從 Director 到 web 伺服器陣列 Fqdn 的通訊 (IIS web 元件所使用的 URLs) 。</p></td>
</tr>
<tr class="odd">
<td><p>董事</p></td>
<td><p>Lync Server Front-End 服務</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
<td><p>用於伺服器與用戶端連線之間的內部通訊。</p></td>
</tr>
<tr class="even">
<td><p>轉送伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
<td><p>由轉送伺服器用於來自前端伺服器的傳入要求。</p></td>
</tr>
<tr class="odd">
<td><p>轉送伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5067</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於來自 PSTN 閘道的傳入 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>轉送伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5068</p></td>
<td><p>TCP</p></td>
<td><p>用於來自 PSTN 閘道的傳入 SIP 要求。</p></td>
</tr>
<tr class="odd">
<td><p>轉送伺服器</p></td>
<td><p>Lync Server 中繼服務</p></td>
<td><p>5070</p></td>
<td><p>TCP (MTLS) </p></td>
<td><p>用於來自前端伺服器的 SIP 要求。</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat 前端伺服器</p></td>
<td><p>Persistent Chat SIP</p></td>
<td><p>5041</p></td>
<td><p>TCP (MTLS) </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Persistent Chat 前端伺服器</p></td>
<td><p>Persistent Chat Windows Communication Foundation (WCF) </p></td>
<td><p>881</p></td>
<td><p>TCP (TLS) 和 TCP (MTLS) </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Persistent Chat 前端伺服器</p></td>
<td><p>Persistent Chat File 傳遞服務</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS) </p></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 某些遠端呼叫控制案例需要在前端伺服器或 Director 和 PBX 之間建立 TCP 連線。 雖然 Lync Server 不再使用 TCP 埠5060，但在遠端呼叫控制部署期間，您會建立信任的伺服器設定，此設定會將 RCC 線路伺服器 FQDN 與前端伺服器或 Director 用來連接 PBX 系統的 TCP 通訊埠產生關聯。 如需詳細資訊，請參閱 Lync Server 管理命令介面檔中的 <STRONG>CsTrustedApplicationComputer</STRONG> Cmdlet。



</div>

針對只使用硬體負載平衡的集區 (不) DNS 負載平衡]，下表顯示需要開啟硬體負載平衡器的埠。

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
<th>連接埠</th>
<th>Protocol (通訊協定)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5061</p></td>
<td><p>TCP (TLS) </p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>444</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>135</p></td>
<td><p>DCOM 和遠端過程呼叫 (RPC) </p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP:</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>8080</p></td>
<td><p>TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>反向 proxy 中的 HTTPS () </p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5072</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5073</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5075</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5076</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5071</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>5080</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>448</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>轉送伺服器負載平衡器</p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器 (如果集區也執行轉送伺服器) </p></td>
<td><p>5070</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="odd">
<td><p>Director 負載平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="even">
<td><p>Director 負載平衡器</p></td>
<td><p>444</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="odd">
<td><p>Director 負載平衡器</p></td>
<td><p>5061</p></td>
<td><p>TCP</p></td>
</tr>
<tr class="even">
<td><p>Director 負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>反向 proxy 中的 HTTPS () </p></td>
</tr>
</tbody>
</table>


使用 DNS 負載平衡的前端集區和 Director 集區也必須部署硬體負載平衡器。 下表顯示這些硬體負載平衡器上需要開啟的埠。

### <a name="hardware-load-balancer-ports-if-using-dns-load-balancing"></a>硬體負載平衡器埠（如果使用 DNS 負載平衡）

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>負載平衡器</th>
<th>連接埠</th>
<th>Protocol (通訊協定)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>80</p></td>
<td><p>HTTP:</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="odd">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>8080</p></td>
<td><p>TCP-用戶端和裝置對來自前端伺服器的根憑證的檢索-由 NTLM 驗證的用戶端和裝置</p></td>
</tr>
<tr class="even">
<td><p>前端伺服器負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>反向 proxy 中的 HTTPS () </p></td>
</tr>
<tr class="odd">
<td><p>Director 負載平衡器</p></td>
<td><p>443</p></td>
<td><p>HTTPS:</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Director 負載平衡器</p></td>
<td><p>4443</p></td>
<td><p>反向 proxy 中的 HTTPS () </p></td>
</tr>
</tbody>
</table>


### <a name="required-client-ports"></a>必要的用戶端埠

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
<th>連接埠</th>
<th>Protocol (通訊協定)</th>
<th>注意事項</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>67/68</p></td>
<td><p>Dhcp</p></td>
<td><p>由 Lync Server 用來尋找註冊機 FQDN (也就是說，如果 DNS SRV 失敗，且未設定) 手動設定。</p></td>
</tr>
<tr class="even">
<td><p>用戶端</p></td>
<td><p>443</p></td>
<td><p>TCP (TLS) </p></td>
<td><p>用於外部使用者存取的用戶端對伺服器 SIP 流量。</p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>443</p></td>
<td><p>TCP (PSOM/TLS) </p></td>
<td><p>用於外部使用者存取 web 會議會話。</p></td>
</tr>
<tr class="even">
<td><p>用戶端</p></td>
<td><p>443</p></td>
<td><p>TCP (STUN/MSTURN) </p></td>
<td><p>用於外部使用者存取 A/V 會話和媒體 (TCP) </p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>3478</p></td>
<td><p>UDP (STUN/MSTURN) </p></td>
<td><p>用於外部使用者存取 A/V 會話和媒體 (UDP) </p></td>
</tr>
<tr class="even">
<td><p>用戶端</p></td>
<td><p>5061</p></td>
<td><p>TCP (MTLS) </p></td>
<td><p>用於外部使用者存取的用戶端對伺服器 SIP 流量。</p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>6891-6901</p></td>
<td><p>TCP</p></td>
<td><p>用於 Lync 用戶端和舊版用戶端之間的檔案傳輸 (Microsoft Office 通訊伺服器 2007 R2、Microsoft Office 通訊伺服器2007及 Live 通訊伺服器 2005) 的用戶端。</p></td>
</tr>
<tr class="even">
<td><p>用戶端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>音訊埠範圍 (至少需要20個埠) </p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP/UDP</p></td>
<td><p>影片埠範圍 (至少需要20個埠) 。</p></td>
</tr>
<tr class="even">
<td><p>用戶端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>對等檔案傳輸 (若為會議檔案傳輸，用戶端會使用 PSOM) 。</p></td>
</tr>
<tr class="odd">
<td><p>用戶端</p></td>
<td><p>1024-65535 *</p></td>
<td><p>TCP</p></td>
<td><p>應用程式共用。</p></td>
</tr>
<tr class="even">
<td><p>Aastra 6721ip 公共區域電話</p>
<p>Aastra 6725ip 電話機</p>
<p>HP 4110 IP 電話 (通用區域電話) </p>
<p>HP 4120 IP 電話 (電話機)</p>
<p>Polycom CX500 IP 公共區域電話</p>
<p>Polycom CX600 IP 電話機</p>
<p>Polycom CX700 IP 服務台電話</p>
<p>Polycom CX3000 IP 會議電話</p></td>
<td><p>67/68</p></td>
<td><p>Dhcp</p></td>
<td><p>由所列裝置使用以尋找 Lync Server 憑證、布建 FQDN 和註冊機 FQDN。</p></td>
</tr>
</tbody>
</table>


**\*** 若要設定這些媒體類型的特定埠，請使用 CsConferencingConfiguration Cmdlet (ClientMediaPortRangeEnabled、ClientMediaPort 及 ClientMediaPortRange 參數) 。

<div>


> [!NOTE]  
> 設定的 Lync 用戶端程式會自動在用戶端電腦上建立所需的作業系統防火牆例外狀況。



</div>

<div>


> [!NOTE]  
> 在用戶端必須透過組織的防火牆 (的任何情況下（例如，其他組織所主控的外部通訊或會議) ），都需要用於外部使用者存取的埠。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

