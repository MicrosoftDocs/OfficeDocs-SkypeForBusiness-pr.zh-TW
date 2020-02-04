---
title: Lync Server 2013： Lync 用戶端視頻需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d174b73bd4369220ae83bc8365267a626849e235
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013 的 lync 用戶端視頻需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-01-29_

本節說明 Lync 2013 視頻通話的視頻硬體支援，並說明如何判斷各種電腦、平板電腦和行動裝置設定的預期視頻品質。

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows 桌面和平板電腦影片需求與功能

Lync 2013 會針對視頻編碼與解碼提供硬體加速，並根據 H-p/MPEG-4 個第10部分高級視頻編碼標準來進行。 此功能可讓使用較低 CPU 時脈速度的電腦來編碼及解碼較高的解析度影片。 根據電腦設定與視頻解析度的不同，視頻硬體需求會有所不同。

<div>

## <a name="video-hardware-requirements"></a>影片硬體需求


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>使用 DirectX Video 加速進行硬體加速的264解碼（DXVA）</p></td>
<td><ul>
<li><p>圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</p></li>
<li><p>必須安裝最新的圖形卡驅動程式。</p></li>
</ul>
<div>

> [!NOTE]  
> 如需解碼模式的詳細資訊<A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>，請參閱。


</div></td>
</tr>
<tr class="even">
<td><p>硬體加速的264編碼：晶片需求</p></td>
<td><p>支援下列 Intel 硬體加速視頻編碼解決方案：</p>
<ul>
<li><p>第二和第三代英特爾高質圖形2000、2500、3000和4000晶片組（或更新版本），集成硬體視頻編碼器。 必須安裝英特爾高質圖形驅動程式15.28.9.2884 或包含下列的最新驅動程式：</p>
<ul>
<li><p>顯示驅動程式9.17.10.2884 或最新的驅動程式</p></li>
<li><p>硬體媒體基礎轉換（HMFT）版本3.12.10.31 或最新 HMFT</p></li>
</ul></li>
</ul>
<p>支援下列 AMD 硬體加速視頻編碼解決方案（需要 Lync Server 2013 的 CU1 更新）：</p>
<ul>
<li><p>在幾個獨立的圖形卡中，以及 AMD A 系列加速處理器的整合式加速處理單元中提供的 AMD Video 編解碼器引擎。 必須安裝 AMD Video 編解碼器引擎驅動程式9.12.0.0 或更新版本。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>硬體加速的264編碼：相機需求</p></td>
<td><p>含集成式 H-p 硬體編碼器的 USB 攝影機，符合 USB Video Class （UVC）規格版本1.5。</p>
<div>

> [!NOTE]  
> Lync 2013 支援 Windows 8 或 Windows 8.1 的 UVC 1.5 攝影機，包括支援 UVC 1.5。 因為 Windows 7 不包括 UVC 1.5 的支援，所以 Lync 2013 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝影機。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>決定 H-p 的視頻編碼與解碼功能

一般來說，以下四個主要因素決定了特定電腦設定的最大編碼與解碼功能：

  - 支援使用 DXVA 進行硬體加速解碼

  - 硬體加速編碼支援

  - 物理內核數

  - Windows 體驗索引（WEI）

Windows 系統評定工具（WinSAT）會判斷 WEI。 當您執行 WinSAT 工具時，它會在電腦上產生一個正式的. 評估 XML 檔，在%\\windir\\%\\效能資料目錄中。 這個 XML 檔案包含下列兩個分數，對於判斷編碼與解碼功能而言是特別重要的：

  - VideoEncodeScore 表示電腦的軟體影片編碼功能。

  - GraphicsScore 值代表電腦的硬體加速編碼功能。

下列三個表格會根據其支援的硬體加速，說明不同電腦類型的最大編碼與解碼功能。 針對640x360 及更高版本的解析度，支援的畫面播放速率上限為30個畫面/秒（fps）。 針對低於640x360 的解析度，支援的畫面播放速率上限為 15 fps。

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>不含 DXVA 且沒有硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析度</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 （640x360 at 僅限接收案例的15fps）</p></td>
<td><p>1核與 VideoEncodeScore ≥4。0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2核與 VideoEncodeScore ≥4。5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2核與 VideoEncodeScore ≥4。5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4核與 VideoEncodeScore ≥4。5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4核與 VideoEncodeScore ≥7。3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4核與 VideoEncodeScore ≥7。3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>有 DXVA 但沒有硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析度</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1核與 VideoEncodeScore ≥3。0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2核與 VideoEncodeScore ≥4。5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2核與 VideoEncodeScore ≥6。0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4核與 VideoEncodeScore ≥6。7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4核與 VideoEncodeScore ≥8。2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Windows 7 上的 WinSAT 得分限制為最大值7.9。 因此，只有在 Windows 8 或 Windows 8.1 上才能取得沒有硬體加速編碼器之電腦的編碼功能，其中最大的 WinSAT 分數為9.9。



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>含 DXVA 及含英特爾高質圖形硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析度</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>所有第二和第三代英特爾高質圖形</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第二和第三代英特爾高質圖形及 GraphicsScore ≥5。0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>行動裝置影片功能

下表說明支援行動裝置的最大視頻功能。 如需行動裝置支援的詳細資訊，請參閱[在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。


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
<th>功能</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H-p 編碼最大解析度</p></td>
<td><p>採用</p></td>
<td><p>QVGA： iPhone 4S</p>
<p>VGA： iPhone 5</p>
<p>720p： iPhone 5S 及更新版本</p></td>
<td><p>VGA： iPad 2 及更新版本/iPad 迷你1及更新版本</p>
<p>720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本</p></td>
<td><p>最多 VGA （視裝置模型而定）</p></td>
</tr>
<tr class="even">
<td><p>H-p 解碼最大解析度</p></td>
<td><p>採用</p></td>
<td><p>QVGA： iPhone 4S</p>
<p>VGA： iPhone 5</p>
<p>720p： iPhone 5S 及更新版本</p></td>
<td><p>VGA： iPad 2 及更新版本/iPad 迷你1及更新版本</p>
<p>720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本</p></td>
<td><p>最多 VGA （視裝置模型而定）</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

