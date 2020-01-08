---
title: Lync Server 2013：IP 位址類型概觀
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90d31045879c4e6f488c232687346ed0413ef62b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013 的 IP 位址類型概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-29_

在 Lync Server 2013 中設定 IP 位址時，有三個選項可供您選擇。 您可以設定 Lync Server 2013，只支援 IP 版本4（IPv4）、僅限 IP 版本6（IPv6），或兩者的組合（稱為*雙堆疊*）。 每個類型的設定都要考慮幾個問題：

  - ****    已建立僅 ipv4 IPv6，因為世界的 ipv4 位址不在正常運作。 我們最終會在全球完全支援 IPv6，但在這段時間，您企業可能需要與之通訊的許多公司和裝置都不支援 IPv6，而且可能不需要一段時間。 僅提供 IPv4 的設定將有助於確保您的 Lync 伺服器實現可以與大多數現有的裝置通訊。

  - **僅 ipv6 相反**   ，目前的完整 ipv6 實現會排除與許多現有裝置的通訊。

  - **雙堆疊**   雙堆疊是啟用 IPv4 和 IPv6 位址的網路。 Lync Server 2013 支援此設定，因為在大多數情況下，從完整 IPv4 轉換到完整 IPv6 時，將需要幾年的時間。

下列各節概述各種 Lync Server 功能在這三種設定中的相容性。

<div>


> [!NOTE]  
> 只有在 lab 或驗證目的中，才支援僅含 IPv6 的用戶端或伺服器設定。 生產部署中不支援僅限 IPv6 的配置。



</div>

<div>

## <a name="client-registration"></a>用戶端註冊


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端端點網路</th>
<th>伺服器網路</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ipv4/ipv6</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>Ipv4/ipv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>對等用戶端

對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。 在兩個用戶端都成功註冊之後，就支援下列組合。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端端點1</th>
<th>用戶端端點2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ipv4/ipv6</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>Ipv4/ipv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>會議

會議包括音訊/視頻、應用程式共用和資料共同作業（whiteboarding 與檔案共用）。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端端點網路</th>
<th>伺服器網路</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ipv4/ipv6</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>Ipv4/ipv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>中繼伺服器/PSTN

如果通信量是透過 IPv6 介面，Lync Server 2013 不支援公用交換電話網絡（PSTN）通話的媒體旁路。 如果需要媒體旁路，建議 PSTN 閘道設定為 IPv4。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>主要介面 *</th>
<th>PSTN 介面（在中繼伺服器上）</th>
<th>PSTN 閘道設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ipv4/ipv6</p></td>
<td><p>雙堆疊</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*主要介面是與 Lync 伺服器元件進行通訊的介面。

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>遠端使用者對等通訊

與遠端使用者進行對等通訊時，包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>遠端使用者網路</th>
<th>Edge 伺服器（外部邊緣）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ipv4/ipv6</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="even">
<td><p>雙堆疊</p></td>
<td><p>Ipv4/ipv6</p></td>
</tr>
<tr class="odd">
<td><p>雙堆疊</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>前臺端池和邊緣池設定

下表顯示前端伺服器池與內部邊緣伺服器池之間的支援矩陣。

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>前端池與邊緣池（內部邊緣）矩陣

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Edge 池： IPv4</strong></p></td>
<td><p><strong>Edge 池：雙堆疊</strong></p></td>
<td><p><strong>Edge 池： IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>前端池： IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>前部端池：雙堆疊</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>前臺端池： IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


\*僅在實驗室環境中使用此組合。

下表是支援的內部和外部邊緣介面組合的矩陣。

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Edge 池（內部邊緣）與邊緣池（外部邊緣）矩陣

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Edge 池（外部邊緣）： IPv4</strong></p></td>
<td><p><strong>Edge 池（外部邊緣）：雙堆疊</strong></p></td>
<td><p><strong>Edge 池（外部邊緣）： IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 池（內部邊緣）： IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edge 池（內部邊緣）：雙堆疊</strong></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 池（內部邊緣）： IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


\*僅在實驗室環境中使用此組合。

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>針對 IPv6 的高級企業語音支援

包括 [呼叫許可控制（CAC）]、[增強9-1-1 （E9-1）] 或 [媒體旁路] 的部署，必須設定為僅使用 IPv4 或雙堆疊式實現。

<div>


> [!NOTE]  
> 在雙堆疊式部署中，即使 Lync 用戶端使用 IPv6 連線至 Lync Server，Lync 也會盡最佳努力，將適當的 IPv4 位址對應至支援 E9-1-1。



</div>

不支援含 IPv6 位址的位置資訊服務。

Exchange 整合通訊（UM）不支援 IPv6。 針對 Exchange UM，請確定 DNS 解析沒有傳回 IPv6 位址。 使用 IPv6 可能會在來電傳送至語音信箱時造成失敗。

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>其他適用于 IPv6 的 Lync Server 2013 功能支援

除了先前提及的功能和元件之外，Lync Server 2013 還支援 IPv6 以執行下列功能：

  - **常設聊天室**
    
    您可以使用拓撲建立器，將 IPv6 設定成持續聊天。 如需有關設定持續聊天的詳細資訊，請參閱部署持久聊天伺服器檔。

  - **經驗品質（QoE）和通話詳細資料錄製（CDR）報告**
    
    無論是 IPv4 或 IPv6 類型，監視報告都包含儲存在監視伺服器資料庫的 IP 位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

