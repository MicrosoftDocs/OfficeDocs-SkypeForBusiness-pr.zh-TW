---
title: Lync Server 2013：設定影片範例案例
description: Lync Server 2013：設定影片範例案例。
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
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575139"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>設定 Lync Server 2013 的影片範例案例

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Lync 2013 新增影片功能以支援 1920 x 1080 完整高清晰度 (HD) 影片和圖庫 View 影片。 以客戶資料為基礎的度量顯示一般的影片流量只會稍微增加至 Lync 2010，但是影片的最大頻寬已增加由於完整 HD 支援 (如需詳細資訊，請參閱 [Lync Server 2013) 中媒體流量需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md) 的「媒體流量網路使用量」一節。 因此，系統管理員可能會想要限制某些使用者 (的影片頻寬，例如分支辦公室中具有較少網路容量的使用者) 並協助確保其他 (使用者（例如「行政人員) ）的最佳顯示品質。

下表提供設定不同網路容量影片的建議設定清單。 這些設定會限制部分使用者案例傳送和接收較高解析度的影片 (請參閱最右邊的欄) 。 最小設定會導致圖庫影片無法使用，原因是低的接收網路頻寬上限。

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
<th>預期的影片解析度以取得優質影片</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最佳</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>對等：最高 1920 x 1080 影片解析度</p>
<p>圖庫 View：最多 2 1920 x 1080 個影片或多個較小的解析度影片</p></td>
</tr>
<tr class="even">
<td><p>良好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>對等：最高 1280 x 720 影片解析度</p>
<p>圖庫 View：最多 5 640 x 360 解析度的視頻</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>對等：最高 960 x 540 影片解析度</p>
<p>圖庫 View：最多 5 424 x 240 解析度的視頻</p></td>
</tr>
<tr class="even">
<td><p>最小值</p></td>
<td><p>是</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>對等：最高 424 x 240 影片解析度</p>
<p>圖庫 View：無法使用</p></td>
</tr>
</tbody>
</table>


您可以使用上表中的資訊，針對組織中的某些使用者部署新的 HD 影片和畫廊查看影片功能，同時允許其他人使用不同的影片解析度。

在下列範例中，系統管理員只會以最高的視頻品質來推出新的影片功能，僅供主管人員使用。 對於位於網路容量低的遠端分支辦公室員工，只會部署前述表格的最小設定。 對於所有其他員工，會部署上表中的「正確」設定。

若要將新功能推廣至主管，系統管理員會建立名為 ExecutiveVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 8000 Kbps

  - TotalReceiveVideoBitRateKB 設定為 8000 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 True

針對分公司中的員工，系統管理員會建立名為 BranchOfficeVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 350 Kbps

  - TotalReceiveVideoBitRateKB 設定為 350 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 False

對於所有其他員工，系統管理員會建立名為 StandardVideo 的會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 2500 Kbps

  - TotalReceiveVideoBitRateKB 設定為 2500 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 True

管理員會將會議原則指派給使用者，如下所示：

  - ExecutiveVideo 會議原則指派給主管人員。

  - BranchOfficeVideo 會議原則會指派給分支機搆中的所有員工。

  - StandardVideo 會議原則會指派給所有其他員工。

這些會議原則指派會導致下列使用者體驗：

  - 所有使用者支援函式庫視圖所組織的所有會議，但分支機搆中的員工無法體驗圖庫 View。

  - 對於任何雙方或多方會議，主管可以傳送 1920 x 1080 完整 HD 影片（如果其硬體和網路連結支援），而且可以接收其他參與者用戶端支援的 1920 x 1080 完整 HD 影片。

  - 非執行官員的員工體驗的解決方案低於雙方或多方會議中的主管，但仍然可獲得良好的解決方法。

  - 當 Lync 顯示預設的影片視窗大小時，位於分支辦公室的員工會在兩方通話中取得良好的視頻品質;不過，如果 Lync 視窗最大化為全螢幕，影片解析度將不會增加。 對於多方會議，分支辦公室中的員工只會看到一個使用中影片。

</div>

<span> </span>

</div>

</div>

</div>

