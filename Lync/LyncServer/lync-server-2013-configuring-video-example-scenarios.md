---
title: Lync Server 2013： 設定視訊範例案例
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
ms.openlocfilehash: 128703a39563124f6abfc4ae44143d274fd3a7c5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a>Lync Server 2013 設定視訊範例案例

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-02_

Lync 2013 新增視訊功能以支援 1920 x 1080 全彩高畫質 (HD) 視訊與圖庫檢視視訊。 根據客戶資料的度量單位顯示一般的視訊頻寬增加僅稍微相較於 Lync 2010，但最大視訊資料流頻寬已經增加由於完整 HD 支援 （如需詳細資訊，請參閱中[的 Lync Server 2013 中的媒體流量網路頻寬需求](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)的 「 媒體流量網路使用率 」 一節）。 因此，系統管理員可能會想要限制特定使用者 （例如中具有較少的網路容量的分公司的使用者） 的視訊頻寬及協助確保最佳視訊品質的其他使用者 （例如主管）。

下表提供建議設定的清單設定不同的網路容量的影片。 這些設定會傳送及接收較高 （請參閱右方的欄） 的解析度的視訊限制某些使用者的案例。 最小的設定會導致無法使用的圖庫影片，由於低的最大值會收到的網路頻寬。

### <a name="recommended-video-settings"></a>建議的視訊設定

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
<th>預期的品質良好視訊解析度的視訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最佳</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>8000</p></td>
<td><p>8000</p></td>
<td><p>若要對等： 最 1920 x 1080 的視訊解析度</p>
<p>圖庫檢視： 最多兩個 1920 x 1080 的視訊或多個較小解析度的視訊</p></td>
</tr>
<tr class="even">
<td><p>良好</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>2500</p></td>
<td><p>2500</p></td>
<td><p>若要對等： 最高 1280 x 720 的視訊解析度</p>
<p>圖庫檢視： 最多五個 640 x 360 解析度的視訊</p></td>
</tr>
<tr class="odd">
<td><p>中</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
<td><p>1000</p></td>
<td><p>1000</p></td>
<td><p>若要對等： 最高 960 x 540 的視訊解析度</p>
<p>圖庫檢視： 最多五個 424 x 240 解析度的視訊</p></td>
</tr>
<tr class="even">
<td><p>最小值</p></td>
<td><p>True</p></td>
<td><p>False</p></td>
<td><p>350</p></td>
<td><p>350</p></td>
<td><p>若要對等： 最高 424 x 240 的視訊解析度</p>
<p>圖庫檢視： 無法使用</p></td>
</tr>
</tbody>
</table>


您可以使用上表中的資訊來部署新的 HD 視訊與圖庫檢視 」 視訊會議功能，部分使用者在您組織中，同時允許其他人的不同的視訊解析度。

在下列範例中，系統管理員可用的最高視訊品質新視訊功能回復才能主管。 低網路容量遠端分公司中的員工，就會部署只從上表的最小設定。 其他所有員工，就會部署上述表格中的 「 良好 」 設定。

若要推行至高階主管的新功能，系統管理員會建立名為 ExecutiveVideo 會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 8000 Kbps

  - TotalReceiveVideoBitRateKB 設定為 8000 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 True

在分公司員工，系統管理員會建立名為 BranchOfficeVideo 會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 350 Kbps

  - TotalReceiveVideoBitRateKB 設定為 350 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 False

其他所有員工，系統管理員會建立名為 StandardVideo 會議原則。 此會議原則具有下列設定：

  - VideoBitRateKB 設定為 2500 Kbps

  - TotalReceiveVideoBitRateKB 設定為 2500 Kbps

  - AllowMultiview 設定為 True

  - EnableMultiviewJoin 設定為 True

系統管理員會將會議原則給使用者，如下所示：

  - 將 ExecutiveVideo 會議原則指派給高階主管。

  - 將 BranchOfficeVideo 會議原則指派給分公司中的所有員工。

  - 將 StandardVideo 會議原則指派給所有其他員工。

這些會議原則指派產生下列使用者體驗：

  - 任何使用者召集的所有會議都支援圖庫檢視，但分公司員工無法體驗圖庫檢視。

  - 針對任何雙方或多方會議，主管可以傳送 1920 x 1080 全彩 HD 視訊，如果其硬體與網路連結支援，而且可接收 1920 x 1080 全 HD 視訊其中其他參與者用戶端支援。

  - 非高階主管的員工體驗的解析度低於高階主管在雙方或多方會議，但仍屬良好解析度。

  - 在分公司員工會良好視訊品質在雙方通話時取得 Lync 顯示預設的視訊視窗大小;不過，如果 Lync 視窗最大化至全螢幕，將不會增加的視訊解析度。 多方會議，在分公司員工將會看到只能有一個作用中的影片。

</div>

<span> </span>

</div>

</div>

</div>

