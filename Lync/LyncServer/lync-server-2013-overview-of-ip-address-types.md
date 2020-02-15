---
title: 'Lync Server 2013: IP 位址類型概觀'
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
ms.openlocfilehash: feb900c6f3d2ac426c184048986a7a751a205874
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Lync Server 2013 的 IP 位址類型概觀

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-29_

在 Lync Server 2013 中設定 IP 位址時，您會有三個選項。 您可以設定 Lync Server 2013 到支援 IP 版本 4 (IPv4)，唯一 IP 第 6 版 (IPv6)，或兩者的組合 （又稱為*雙重堆疊*）。 有幾個問題，考慮每種類型的設定：

  - **僅限 IPv4**   建立 IPv6，因為在世界用盡 IPv4 位址。 最後，全球，但這次完全支援 IPv6，許多公司和您的企業可能需要與通訊的裝置還不支援 IPv6，並可能不適用於一些時間。 僅 IPv4 的設定有助於確保您實作可以與彼此大多數現有裝置的 Lync 伺服器。

  - **僅限 IPv6**   反之，完整的 IPv6 實作在這個階段中，將排除的通訊與許多現有裝置。

  - **雙重堆疊**   雙重堆疊是獲 IPv4 與 IPv6 位址的網路。 Lync Server 2013 中支援此組態，因為在大多數情況下從完整 IPv4 轉換為完整 IPv6 會花幾年。

下列各節概述這三種組態之各種 Lync Server 功能之間的相容性。

<div>


> [!NOTE]  
> 使用 IPv6 的用戶端或伺服器設定只支援僅供實驗室或驗證之用。 在實際執行部署中不支援 IPv6 唯一組態。



</div>

<div>

## <a name="client-registration"></a>用戶端登錄


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

## <a name="peer-to-peer-client"></a>端對端用戶端

對等通訊包含音訊、 音訊/視訊、 應用程式共用和檔案傳輸。 這兩種用戶端已成功註冊後，支援下列的組合。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端端點 1</th>
<th>用戶端端點 2</th>
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

會議包含音訊/視訊、 應用程式共用，以及資料共同作業 （白板與檔案共用）。


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

## <a name="mediation-serverpstn"></a>中繼伺服器 PSTN

Lync Server 2013 不支援媒體旁路的公用交換的電話網路 (PSTN) 通話如果流量是透過 IPv6 的介面。 如果需要媒體旁路，我們建議的 PSTN 閘道設為 IPv4。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>主要介面 *</th>
<th>PSTN 介面 （中繼伺服器）</th>
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


\*主要介面是與 Lync Server 元件進行通訊的介面。

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>遠端使用者對等通訊

與遠端使用者的對等通訊包含立即訊息、 音訊/視訊、 應用程式共用和檔案傳輸。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>遠端使用者網路</th>
<th>Edge server (外部 edge)</th>
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

## <a name="front-end-pool-and-edge-pool-configuration"></a>前端集區與 Edge 集區組態

下表顯示的前端伺服器集區和內部 Edge Server 集區的支援矩陣。

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>前端集區與 Edge 集區 (內部 Edge) 矩陣

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
<td><p><strong>Edge 集區： 雙重堆疊</strong></p></td>
<td><p><strong>Edge 集區： IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>前端集區： IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>前端集區： 雙重堆疊</strong></p></td>
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


\*使用此組合僅在實驗室環境中。

下表是內部和外部 edge 介面的支援組合矩陣。

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Edge 集區 (內部 Edge) 與 Edge 集區 (外部 Edge) 矩陣

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
<td><p><strong>Edge 集區 (外部 Edge): IPv4</strong></p></td>
<td><p><strong>Edge 集區 (外部 Edge): 雙重堆疊</strong></p></td>
<td><p><strong>Edge 集區 (外部 Edge): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 集區 (內部 Edge): IPv4</strong></p></td>
<td><p>是</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edge 集區 (內部 Edge): 雙重堆疊</strong></p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p><strong>Edge 集區 (內部 Edge): IPv6</strong></p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是*</p></td>
</tr>
</tbody>
</table>


\*使用此組合僅在實驗室環境中。

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>進階 Enterprise Voice 支援 IPv6

部署，包括通話許可控制 (CAC)、 增強型 9-1-1 (E9-1-1) 或媒體旁路必須設定為 IPv4 僅或雙重堆疊實作。

<div>


> [!NOTE]  
> 在雙重堆疊部署中，即使使用 IPv6，Lync 用戶端連線至 Lync Server Lync 將盡可能對應適當的 IPv4 位址，以支援 E9-1-1。



</div>

不支援透過 IPv6 位址的位置資訊服務。

Exchange 整合通訊 (UM) 不支援 IPv6。 對於 Exchange UM，請務必 DNS 解析不會傳回 IPv6 位址。 來電傳送至語音信箱時，使用 IPv6 將導致失敗。

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>其他 Lync Server 2013 支援的 IPv6 功能

除了的功能和元件先前所述，Lync Server 2013 支援 IPv6 的下列功能：

  - **常設聊天室**
    
    您使用拓撲產生器設定 IPv6 的常設聊天室。 如需設定常設聊天室的詳細資訊，請參閱 < Deploying Persistent Chat Server 文件。

  - **品質經驗 (QoE) 與詳細通話記錄 (CDR) 報告**
    
    監控報告包含的 IP 位址是儲存在監控伺服器資料庫中，是否的 IPv4 或 IPv6。

</div>

</div>

<span> </span>

</div>

</div>

</div>

