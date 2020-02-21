---
title: 'Lync Server 2013: Lync 用戶端視訊需求'
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
ms.openlocfilehash: c15eb698babcce1cd104dd7206c037b95d402992
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Lync Server 2013 的 Lync 用戶端視訊需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-01-29_

本節說明 Lync 2013 視訊撥號的視訊硬體支援，並說明如何判斷預期的視訊品質的各種電腦、 平板電腦及行動裝置設定。

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Windows 桌上型電腦和平板電腦視訊的需求和功能

Lync 2013 引進硬體加速的視訊編碼和解碼根據 H.264/mpeg-4 組件 10 進階視訊編碼標準。 這項功能可讓具有較低的 CPU 時脈速度，來編碼和解碼高解析度的視訊的電腦。 視訊硬體需求而異 「 電腦設定和視訊解析度原本。

<div>

## <a name="video-hardware-requirements"></a>視訊硬體需求


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
<td><p>硬體加速 H.264 解碼使用 DirectX 視訊加速 (DXVA)</p></td>
<td><ul>
<li><p>圖形卡必須支援 DirectX 9.0，而且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</p></li>
<li><p>必須安裝最新的圖形卡驅動程式。</p></li>
</ul>
<div>

> [!NOTE]  
> 如需關於解碼模式的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>。


</div></td>
</tr>
<tr class="even">
<td><p>硬體加速的 H.264 編碼： 晶片組需求</p></td>
<td><p>支援下列 Intel 硬體加速的視訊編碼解決方案：</p>
<ul>
<li><p>第二個和第三代 Intel HD Graphics 2000、 2500、 3000 及 4000 晶片組 （或更新版本） 與整合的硬體視訊編碼器。 是需要安裝的 Intel HD Graphics 驅動程式 15.28.9.2884 或最新驅動程式包含下列：</p>
<ul>
<li><p>顯示驅動程式 9.17.10.2884 或最新的驅動程式</p></li>
<li><p>硬體媒體 foundation 轉換 (HMFT) 版本 3.12.10.31 或最新的 HMFT</p></li>
</ul></li>
</ul>
<p>下列的 AMD 硬體支援加速的視訊編碼解決方案 （需要 CU1 更新 Lync Server 2013）：</p>
<ul>
<li><p>AMD 視訊轉碼器引擎，也就是可在多個不連續的圖形卡和整合式加速處理的 AMD 的數列加速處理器的單位。 AMD 視訊轉碼器引擎驅動程式 9.12.0.0 或更高版本必須安裝。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>硬體加速的 H.264 編碼： 相機需求</p></td>
<td><p>符合到 USB 視訊類別 (UVC) 規格版本 1.5 的整合式 H.264 硬體編碼器的 USB 攝影機。</p>
<div>

> [!NOTE]  
> Lync 2013 支援與 Windows 8 或 Windows 8.1，包含支援 UVC 1.5 UVC 1.5 相機。 Windows 7 不會納入 UVC 1.5 的支援，因為 Lync 2013 會視為一般相機 UVC 1.5 相機與不支援的編碼方式的硬體。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>判斷 H.264 視訊編碼與解碼功能

一般而言，有四個主要因素可判斷編碼與解碼功能的特定電腦設定最大值：

  - 支援硬體加速解碼使用 DXVA

  - 支援硬體加速編碼

  - 實際核心數

  - Windows 體驗指數 (WEI)

Windows 系統評估工具 (WinSAT) 會決定 WEI。 當您執行 WinSAT 工具時，它就會產生 Formal.Assessment XML 文件的電腦上 %exchangeinstallpath%windir %\\效能\\WinSAT\\資料存放區目錄。 此 XML 檔案包含下列兩個分數屬於特定重要性判斷編碼與解碼功能：

  - VideoEncodeScore 表示軟體為主的視訊編碼功能的電腦。

  - GraphicsScore 值表示硬體加速編碼功能的電腦。

下列三個表格說明編碼與解碼功能根據它們支援哪些硬體加速的不同的電腦類型的最大值。 為 640 x 360 和更高解析度，最多支援的畫面播放速率是 30 每秒畫面數 (fps)。 For 解析度低於 640 x 360，最多支援的畫面播放速率是 15 fps。

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>電腦不含 DXVA 且不含硬體加速編碼器

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可使用編碼器的解析度</th>
<th>可使用解碼器的解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>424 x 240 （640 x 360，15 fps，如接收僅案例）</p></td>
<td><p>1 核心且 VideoEncodeScore ≥ 4.0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 核心且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1280 x 720</p></td>
<td><p>2 核心且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 核心且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1280 x 720</p></td>
<td><p>4 核心且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 核心且 VideoEncodeScore ≥ 7.3</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>不適用</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>電腦含 DXVA 但不含硬體加速編碼器

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可使用編碼器的解析度</th>
<th>可使用解碼器的解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>1920 x 1080</p></td>
<td><p>1 核心且 VideoEncodeScore ≥ 3.0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 核心且 VideoEncodeScore ≥ 4.5</p></td>
</tr>
<tr class="odd">
<td><p>高 960 x 540</p></td>
<td><p>1920 x 1080</p></td>
<td><p>2 核心且 VideoEncodeScore ≥ 6.0</p></td>
</tr>
<tr class="even">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 核心且 VideoEncodeScore ≥ 6.7</p></td>
</tr>
<tr class="odd">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>4 核心且 VideoEncodeScore ≥ 8.2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 在 Windows 7 上的 WinSAT 分數僅限於 7.9 的最大值。 因此，不含硬體加速編碼器的電腦的編碼功能只可在 Windows 8 或 Windows 8.1，其中的最大 WinSAT 分數是 9.9 達成。



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>電腦含 DXVA 且含 Intel HD Graphics 硬體加速編碼器

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>可使用編碼器的解析度</th>
<th>可使用解碼器的解析度</th>
<th>需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280 x 720</p></td>
<td><p>1920 x 1080</p></td>
<td><p>所有第 2 個和第 3 層代 Intel HD Graphics</p></td>
</tr>
<tr class="even">
<td><p>1920 x 1080</p></td>
<td><p>1920 x 1080</p></td>
<td><p>第 2 個和第 3 代 Intel HD Graphics 且 GraphicsScore ≥ 5.0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>行動裝置視訊功能

下表說明支援的行動裝置的最大視訊功能。 如需有關行動裝置支援，請參閱[Planning for Lync Server 2013 中的行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。


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
<td><p>H.264 編碼最大解析度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720 p: iPhone 5S 和更新版本</p></td>
<td><p>VGA: iPad 2 和更新版本/iPad 浮動 1 和更新版本</p>
<p>720 p: iPad 空調/iPad 迷你 2/iPad 專業版和更新版本</p></td>
<td><p>最多 VGA 根據裝置型號</p></td>
</tr>
<tr class="even">
<td><p>H.264 解碼最大解析度</p></td>
<td><p>VGA</p></td>
<td><p>QVGA: iPhone 4S</p>
<p>VGA: iPhone 5</p>
<p>720 p: iPhone 5S 和更新版本</p></td>
<td><p>VGA: iPad 2 和更新版本/iPad 浮動 1 和更新版本</p>
<p>720 p: iPad 空調/iPad 迷你 2/iPad 專業版和更新版本</p></td>
<td><p>最多 VGA 根據裝置型號</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

