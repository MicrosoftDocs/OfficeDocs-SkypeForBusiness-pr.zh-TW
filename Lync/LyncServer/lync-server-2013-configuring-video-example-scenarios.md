---
title: Lync Server 2013：設定影片範例案例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd47056b97da1ba3ac1bf884cc3e8bd9aaf43f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>設定 Lync Server 2013 的影片範例案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync 2013 新增了支援 1920 x 1080 完整高清（HD）影片和圖庫視圖影片的新影片功能。 以客戶資料為基礎的度量單位顯示典型的影片頻寬只有與 Lync 2010 稍有增加，但由於完整的 HD 支援而增加了最大的影片頻寬，所以請參閱[Lync Server 2013 中媒體流量需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)的「媒體流量網路使用量」一節。 因此，系統管理員可能會想要限制特定使用者的影片頻寬（例如分支辦公室中網路容量較低的使用者），並協助確保其他使用者可能獲得最佳的影片品質（例如主管）。

下表提供針對不同網路容量配置影片的建議設定清單。 這些設定會限制部分使用者案例傳送和接收較高解析度的影片（請參閱最右邊的資料行）。 由於最大的接收網路頻寬不足，因此 [最小值] 設定將導致圖庫影片無法使用。

### <a name="recommended-video-settings"></a>建議的影片設定

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th>AllowMultiView</th>
<th>EnableMultiViewJoin</th>
<th>VideoBitRateKB</th>
<th>TotalReceiveVideoBitRateKB</th>
<th>預期的影片解析度以取得良好品質的影片</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>大</p></td>
<td><p>滿足</p></td>
<td><p>滿足</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>對等：高達 1920 x 1080 視頻解析度</p>
<p>圖庫視圖：高達 2 1920 x 1080 的影片或多個較小的解析度影片</p></td>
</tr>
<tr class="even">
<td><p>良好</p></td>
<td><p>滿足</p></td>
<td><p>滿足</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>對等：高達 1280 x 720 視頻解析度</p>
<p>圖庫視圖：最高至 5 640 x 360 解析度的影片</p></td>
</tr>
<tr class="odd">
<td><p>深淺</p></td>
<td><p>滿足</p></td>
<td><p>滿足</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>對等：高達 960 x 540 視頻解析度</p>
<p>圖庫視圖：最高至 5 424 x 240 解析度的影片</p></td>
</tr>
<tr class="even">
<td><p>基本</p></td>
<td><p>滿足</p></td>
<td><p>虛假</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>對等：高達 424 x 240 視頻解析度</p>
<p>圖庫視圖：無法使用</p></td>
</tr>
</tbody>
</table>


您可以使用上表中的資訊，為貴組織中的部分使用者部署新的 HD 影片和圖庫，同時為其他人允許不同的影片解析度。

在下列範例中，系統管理員會推出僅提供給主管的最高視頻品質的新視頻功能。 對於在網路容量較低的遠端分支辦公室中的員工，只會部署來自上表的最小設定。 針對其他所有員工，部署來自上一個資料表的「良好」設定。

若要將新功能推出給主管，系統管理員會建立名為 ExecutiveVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 已設定為 8000 Kbps

  - TotalReceiveVideoBitRateKB 已設定為 8000 Kbps

  - AllowMultiview 已設定為 True

  - EnableMultiviewJoin 已設定為 True

針對分支辦公室中的員工，系統管理員會建立名為 BranchOfficeVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 已設定為 350 Kbps

  - TotalReceiveVideoBitRateKB 已設定為 350 Kbps

  - AllowMultiview 已設定為 True

  - EnableMultiviewJoin 已設定為 False

對於其他所有員工，系統管理員會建立名為 StandardVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 已設定為 2500 Kbps

  - TotalReceiveVideoBitRateKB 已設定為 2500 Kbps

  - AllowMultiview 已設定為 True

  - EnableMultiviewJoin 已設定為 True

系統管理員會將會議原則指派給使用者，如下所示：

  - ExecutiveVideo 會議原則已指派給主管人員。

  - BranchOfficeVideo 會議原則會指派給分支機搆中的所有員工。

  - StandardVideo 會議原則會指派給其他所有員工。

這些會議原則指派會產生下列使用者體驗：

  - 所有由任何使用者支援圖庫視圖組織的會議，但分支機搆中的員工無法體驗圖庫視圖。

  - 對於任何二方或多方會議，主管都可以傳送 1920 x 1080 完整的 HD 影片（如果其硬體和網路連結支援），而且可以在其他參與者用戶端支援它的地方收到 1920 x 1080 完整 HD 影片。

  - 非主管人員在其雙方或多方會議中與主管相比，不會有較低解析度的員工，但仍能取得良好的解析度。

  - 當 Lync 顯示預設的影片視窗大小時，分支辦公室中的員工就能在兩方通話中取得良好的影片品質;不過，如果 Lync 視窗已最大化至全螢幕，影片解析度就不會增加。 對於多方會議，分支辦公室中的員工只會看到一個 [活動中的影片]。

</div>

<span> </span>

</div>

</div>

</div>

