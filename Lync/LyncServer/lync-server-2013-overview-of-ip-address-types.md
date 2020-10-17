---
title: Lync Server 2013： IP 位址類型的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9663f7ee8b57ceba27e1a1892c30bb92a1c86ffc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521000"
---
# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013 的 IP 位址類型概述

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-29_

在 Lync Server 2013 中設定 IP 位址時，您有三個選項。 您可以將 Lync Server 2013 設定為僅支援 IP 版本 4 (IPv4) 、只有 IP 版本 6 (IPv6) ，或是兩種 (（稱為 *雙重堆疊*) ）的組合。 每種類型的設定都有幾個考慮事項：

  - **僅 IPv4**    因為世界用完了 IPv4 位址，所以已建立 IPv6。 最後，我們會完全支援全球的 IPv6，但目前，您的企業可能需要與其通訊的許多公司和裝置都不支援 IPv6，而且可能不是一段時間。 僅限 IPv4 的設定會協助確保您的 Lync Server 實施可以與大多數的現有裝置進行通訊。

  - **僅 IPv6**    相反地，完整的 IPv6 的實施方式，會排除與許多現有裝置的通訊。

  - **雙重堆疊**    雙堆疊是一種同時啟用 IPv4 和 IPv6 位址的網路。 Lync Server 2013 支援此設定，因為在大多數情況下，從完整 IPv4 轉換為完整 IPv6 會需要數年。

下列各節將說明各種 Lync Server 功能的這三個設定之間的相容性。

<div>


> [!NOTE]  
> 只有實驗室或驗證目的才支援用戶端或伺服器設定只支援 IPv6。 在實際執行部署中，不支援只有設定 IPv6。



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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Peer-to-Peer 用戶端

對等通訊包括音訊、音訊/視頻、應用程式共用和檔案傳輸。 這兩個用戶端都成功註冊後，支援下列組合。


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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙重堆疊</p></td>
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

會議包含音訊/視頻、應用程式共用，以及資料共同作業 (白板和檔案共用) 。


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
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>轉送伺服器/PSTN

Lync Server 2013 不支援公用交換電話網路 (PSTN) 通話的媒體旁路，如果流量是透過 IPv6 介面。 如果需要媒體旁路，建議將 PSTN 閘道設定為 IPv4。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>主要介面 *</th>
<th>轉送伺服器上的 PSTN 介面 () </th>
<th>PSTN 閘道設定</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>雙重堆疊</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\* 主要介面是與 Lync Server 元件通訊的介面。

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>遠端使用者 Peer-to-Peer 通訊

與遠端使用者的對等通訊包括立即訊息、音訊/視頻、應用程式共用和檔案傳輸。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>遠端使用者網路</th>
<th>Edge server (外部 edge) </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>雙重堆疊</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>雙重堆疊</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>雙重堆疊</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>前端集區和 Edge 集區設定

下表顯示前端伺服器集區和內部 Edge Server 集區之間的支援矩陣。

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>前端集區和 Edge 集區 (內部 Edge) 矩陣

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
<td><p><strong>Edge 集區： IPv4</strong></p></td>
<td><p><strong>Edge 集區：雙堆疊</strong></p></td>
<td><p><strong>Edge 集區： IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>前端集區： IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>前端集區：雙棧</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>前端集區： IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是*</p></td>
</tr>
</tbody>
</table>


\* 僅在實驗室環境中使用此組合。

下表是支援的內部和外部 edge 介面組合的矩陣。

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Edge 集區 (內部 Edge) 和 Edge 集區 (外部 Edge) 矩陣

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
<td><p><strong>Edge 集區 (外部 Edge) ： IPv4</strong></p></td>
<td><p><strong>Edge 集區 (外部 Edge) ：雙堆疊</strong></p></td>
<td><p><strong>Edge 集區 (外部 Edge) ： IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 集區 (內部 Edge) ： IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edge 集區 (內部 Edge) ：雙堆疊</strong></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 集區 (內部 Edge) ： IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是*</p></td>
</tr>
</tbody>
</table>


\* 僅在實驗室環境中使用此組合。

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 的高級 Enterprise 語音支援

包含通話許可控制的部署 (CAC) 、增強型 9-1-1 (E9-1-1) 或媒體旁路，都必須設定為 IPv4 或雙堆疊式的執行。

<div>


> [!NOTE]  
> 在雙堆疊部署中，即使 Lync 用戶端使用 IPv6 連接至 Lync 伺服器，Lync 也會盡力對應適當的 IPv4 位址，以支援 E9-1-1。



</div>

不支援使用 IPv6 位址的位置資訊服務。

Exchange 整合通訊 (UM) 不支援 IPv6。 若為 Exchange UM，請確定 DNS 解析不會傳回 IPv6 位址。 在來電傳送至語音信箱時，使用 IPv6 可能會造成失敗。

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>其他 Lync Server 2013 功能支援 IPv6

除了先前所述的功能和元件，Lync Server 2013 還支援下列功能的 IPv6：

  - **常設聊天室**
    
    您可以使用拓撲產生器，設定持續聊天的 IPv6。 如需設定持續性聊天的詳細資訊，請參閱部署 Persistent Chat Server 檔。

  - **經驗品質 (QoE) 和詳細通話記錄 (CDR) 報告**
    
    監控報告包含的 IP 位址會儲存在監控伺服器資料庫中，不論其類型是 IPv4 還是 IPv6。

</div>

</div>

<span> </span>

</div>

</div>

</div>

