---
title: Lync Server 2013： Lync 用戶端影片需求
description: Lync Server 2013： Lync 用戶端影片需求。
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
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570479"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013 的 lync 用戶端影片需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-01-29_

本節說明 Lync 2013 影片通話的影片硬體支援，並說明如何判斷各種電腦、平板電腦及行動裝置設定的預期影片品質。

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows 桌面和平板電腦影片需求和功能

Lync 2013 針對根據 H-p/MPEG-4 第10部分的先進視頻編碼標準，引入影片編碼和解碼的硬體加速。 此功能可讓具有較低 CPU 時脈速度的電腦編碼和解碼較高解析度的影片。 影片硬體需求會因電腦設定和影片解析度的需要而異。

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
<td><p>使用 DirectX 影片加速 (DXVA) 硬體加速的 .H 解碼</p></td>
<td><ul>
<li><p>圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</p></li>
<li><p>必須安裝最新的圖形卡驅動程式。</p></li>
</ul>
<div>

> [!NOTE]  
> 如需有關解碼模式的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> 。


</div></td>
</tr>
<tr class="even">
<td><p>硬體加速的 H-p 編碼：晶片組需求</p></td>
<td><p>下列為支援的 Intel 硬體加速視頻編碼方案：</p>
<ul>
<li><p>第二和第三代 Intel HD Graphics 2000、2500、3000及4000晶片組 (或更新版本) 整合的硬體視頻編碼器。 需要安裝 Intel HD Graphics 驅動程式15.28.9.2884 或最新的驅動程式，其中包含下列各項：</p>
<ul>
<li><p>顯示驅動程式9.17.10.2884 或最新的驅動程式</p></li>
<li><p>硬體媒體基礎轉換 (HMFT) 版本3.12.10.31 或最新的 HMFT</p></li>
</ul></li>
</ul>
<p>以下是支援的 AMD 硬體加速視頻編碼方案 (需要 Lync Server 2013) CU1 更新：</p>
<ul>
<li><p>AMD Video 編解碼器引擎，可在許多獨立的圖形卡中，以及 AMD A Series 加速處理器的整合式加速處理單位。 9.12.0.0 或更新版本必須安裝 AMD Video 編解碼器引擎驅動程式。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>硬體加速的 H-p 編碼：攝像頭需求</p></td>
<td><p>帶有整合的 H-p 硬體編碼器的 USB 影片相機，其符合 USB Video 類別 (UVC) 規格版本1.5。</p>
<div>

> [!NOTE]  
> Lync 2013 支援具有 Windows 8 或 Windows 8.1 的 UVC 1.5 攝像頭，這包括支援 UVC 1.5。 由於 Windows 7 不包含支援 UVC 1.5，所以 Lync 2013 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝像頭。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>決定 H-p 影片的編碼和解碼功能

一般來說，有四個主要因素會決定特定電腦設定的最大編碼和解碼功能：

  - 使用 DXVA 支援硬體加速解碼

  - 硬體加速編碼支援

  - 實體核心數目

  - Windows 經驗索引 (WEI) 

Windows 系統評定工具 (WinSAT) 會決定 WEI。 當您執行 WinSAT 工具時，它會在% windir% \\ 效能的 \\ WinSAT 資料目錄中產生電腦上的正規評估 XML 檔 \\ 。 此 XML 檔包含下列兩個分數，尤其是決定編碼和解碼功能的特別重要性：

  - VideoEncodeScore 指出電腦的軟體型影片功能。

  - GraphicsScore 值表示電腦的硬體加速編碼功能。

下列三個表格針對不同的電腦類型，根據其所支援的硬體加速度，說明其編碼和解碼功能的上限。 針對640x360 及更高版本，支援的框架速率上限為每秒30個畫面 (fps) 。 對於低於640x360 的解析度，支援的最大畫面播放速率為 15 fps。

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>沒有 DXVA 且不含硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 at 15fps 僅限接收案例) </p></td>
<td><p>1核心和 VideoEncodeScore ≧4。0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2核心和 VideoEncodeScore ≧4。5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2核心和 VideoEncodeScore ≧4。5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4核心和 VideoEncodeScore ≧4。5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4核心和 VideoEncodeScore ≧7。3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4核心和 VideoEncodeScore ≧7。3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>具有 DXVA 但不含硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1核心和 VideoEncodeScore ≧3。0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2核心和 VideoEncodeScore ≧4。5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2核心和 VideoEncodeScore ≧6。0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4核心和 VideoEncodeScore ≧6。7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4核心和 VideoEncodeScore ≧8。2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Windows 7 上的 WinSAT 分數限制為最大值7.9。 因此，沒有硬體加速編碼器的電腦編碼功能只能在 Windows 8 或 Windows 8.1 （最大的 WinSAT 分數為9.9）上完成。



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>具有 DXVA 且具有英特爾 HD 圖形硬體加速編碼器的電腦

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>支援的編碼器解析</th>
<th>支援的解碼器解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>所有第二個和第三代的 Intel HD 顯卡</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>第二和第三代 Intel HD Graphics 和 GraphicsScore ≧5。0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>行動裝置影片功能

下表說明支援的行動裝置的最大視頻功能。 如需行動裝置支援的詳細資訊，請參閱 [在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。


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
<th>Iphone</th>
<th>Ipad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>最高解析度的264編碼</p></td>
<td><p>Vga</p></td>
<td><p>QVGA： iPhone 4S</p>
<p>VGA： iPhone 5</p>
<p>720p： iPhone 5S 及更新版本</p></td>
<td><p>VGA： iPad 2 和更新版本/iPad 迷你1和更新版本</p>
<p>720p： iPad Air/iPad 迷你 2/iPad Pro 和更新版本</p></td>
<td><p>取決於裝置模型，最多 VGA</p></td>
</tr>
<tr class="even">
<td><p>-264 解碼最大解析度</p></td>
<td><p>Vga</p></td>
<td><p>QVGA： iPhone 4S</p>
<p>VGA： iPhone 5</p>
<p>720p： iPhone 5S 及更新版本</p></td>
<td><p>VGA： iPad 2 和更新版本/iPad 迷你1和更新版本</p>
<p>720p： iPad Air/iPad 迷你 2/iPad Pro 和更新版本</p></td>
<td><p>取決於裝置模型，最多 VGA</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

