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
ms.openlocfilehash: 1e4a8e99c50bc62565ed597e65cef73a6aaddd08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="6de75-102">Lync Server 2013 的 Lync 用戶端視訊需求</span><span class="sxs-lookup"><span data-stu-id="6de75-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6de75-103">_**主題上次修改日期：** 2016年-01-29_</span><span class="sxs-lookup"><span data-stu-id="6de75-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="6de75-104">本節說明 Lync 2013 視訊撥號的視訊硬體支援，並說明如何判斷預期的視訊品質的各種電腦、 平板電腦及行動裝置設定。</span><span class="sxs-lookup"><span data-stu-id="6de75-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="6de75-105">Windows 桌上型電腦和平板電腦視訊的需求和功能</span><span class="sxs-lookup"><span data-stu-id="6de75-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="6de75-106">Lync 2013 引進硬體加速的視訊編碼和解碼根據 H.264/mpeg-4 組件 10 進階視訊編碼標準。</span><span class="sxs-lookup"><span data-stu-id="6de75-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="6de75-107">這項功能可讓具有較低的 CPU 時脈速度，來編碼和解碼高解析度的視訊的電腦。</span><span class="sxs-lookup"><span data-stu-id="6de75-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="6de75-108">視訊硬體需求而異 「 電腦設定和視訊解析度原本。</span><span class="sxs-lookup"><span data-stu-id="6de75-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="6de75-109">視訊硬體需求</span><span class="sxs-lookup"><span data-stu-id="6de75-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de75-110">功能</span><span class="sxs-lookup"><span data-stu-id="6de75-110">Feature</span></span></th>
<th><span data-ttu-id="6de75-111">需求</span><span class="sxs-lookup"><span data-stu-id="6de75-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de75-112">硬體加速 H.264 解碼使用 DirectX 視訊加速 (DXVA)</span><span class="sxs-lookup"><span data-stu-id="6de75-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="6de75-113">圖形卡必須支援 DirectX 9.0，而且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</span><span class="sxs-lookup"><span data-stu-id="6de75-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="6de75-114">必須安裝最新的圖形卡驅動程式。</span><span class="sxs-lookup"><span data-stu-id="6de75-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="6de75-115">如需關於解碼模式的詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>。</span><span class="sxs-lookup"><span data-stu-id="6de75-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-116">硬體加速的 H.264 編碼： 晶片組需求</span><span class="sxs-lookup"><span data-stu-id="6de75-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="6de75-117">支援下列 Intel 硬體加速的視訊編碼解決方案：</span><span class="sxs-lookup"><span data-stu-id="6de75-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de75-118">第二個和第三代 Intel HD Graphics 2000、 2500、 3000 及 4000 晶片組 （或更新版本） 與整合的硬體視訊編碼器。</span><span class="sxs-lookup"><span data-stu-id="6de75-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="6de75-119">是需要安裝的 Intel HD Graphics 驅動程式 15.28.9.2884 或最新驅動程式包含下列：</span><span class="sxs-lookup"><span data-stu-id="6de75-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="6de75-120">顯示驅動程式 9.17.10.2884 或最新的驅動程式</span><span class="sxs-lookup"><span data-stu-id="6de75-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="6de75-121">硬體媒體 foundation 轉換 (HMFT) 版本 3.12.10.31 或最新的 HMFT</span><span class="sxs-lookup"><span data-stu-id="6de75-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="6de75-122">下列的 AMD 硬體支援加速的視訊編碼解決方案 （需要 CU1 更新 Lync Server 2013）：</span><span class="sxs-lookup"><span data-stu-id="6de75-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="6de75-123">AMD 視訊轉碼器引擎，也就是可在多個不連續的圖形卡和整合式加速處理的 AMD 的數列加速處理器的單位。</span><span class="sxs-lookup"><span data-stu-id="6de75-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="6de75-124">AMD 視訊轉碼器引擎驅動程式 9.12.0.0 或更高版本必須安裝。</span><span class="sxs-lookup"><span data-stu-id="6de75-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-125">硬體加速的 H.264 編碼： 相機需求</span><span class="sxs-lookup"><span data-stu-id="6de75-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="6de75-126">符合到 USB 視訊類別 (UVC) 規格版本 1.5 的整合式 H.264 硬體編碼器的 USB 攝影機。</span><span class="sxs-lookup"><span data-stu-id="6de75-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6de75-127">Lync 2013 支援與 Windows 8 或 Windows 8.1，包含支援 UVC 1.5 UVC 1.5 相機。</span><span class="sxs-lookup"><span data-stu-id="6de75-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="6de75-128">Windows 7 不會納入 UVC 1.5 的支援，因為 Lync 2013 會視為一般相機 UVC 1.5 相機與不支援的編碼方式的硬體。</span><span class="sxs-lookup"><span data-stu-id="6de75-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="6de75-129">判斷 H.264 視訊編碼與解碼功能</span><span class="sxs-lookup"><span data-stu-id="6de75-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="6de75-130">一般而言，有四個主要因素可判斷編碼與解碼功能的特定電腦設定最大值：</span><span class="sxs-lookup"><span data-stu-id="6de75-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="6de75-131">支援硬體加速解碼使用 DXVA</span><span class="sxs-lookup"><span data-stu-id="6de75-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="6de75-132">支援硬體加速編碼</span><span class="sxs-lookup"><span data-stu-id="6de75-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="6de75-133">實際核心數</span><span class="sxs-lookup"><span data-stu-id="6de75-133">Number of physical cores</span></span>

  - <span data-ttu-id="6de75-134">Windows 體驗指數 (WEI)</span><span class="sxs-lookup"><span data-stu-id="6de75-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="6de75-135">Windows 系統評估工具 (WinSAT) 會決定 WEI。</span><span class="sxs-lookup"><span data-stu-id="6de75-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="6de75-136">當您執行 WinSAT 工具時，它就會產生 Formal.Assessment XML 文件的電腦上 %exchangeinstallpath%windir %\\效能\\WinSAT\\資料存放區目錄。</span><span class="sxs-lookup"><span data-stu-id="6de75-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="6de75-137">此 XML 檔案包含下列兩個分數屬於特定重要性判斷編碼與解碼功能：</span><span class="sxs-lookup"><span data-stu-id="6de75-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="6de75-138">VideoEncodeScore 表示軟體為主的視訊編碼功能的電腦。</span><span class="sxs-lookup"><span data-stu-id="6de75-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="6de75-139">GraphicsScore 值表示硬體加速編碼功能的電腦。</span><span class="sxs-lookup"><span data-stu-id="6de75-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="6de75-140">下列三個表格說明編碼與解碼功能根據它們支援哪些硬體加速的不同的電腦類型的最大值。</span><span class="sxs-lookup"><span data-stu-id="6de75-140">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="6de75-141">為 640 x 360 和更高解析度，最多支援的畫面播放速率是 30 每秒畫面數 (fps)。</span><span class="sxs-lookup"><span data-stu-id="6de75-141">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="6de75-142">For 解析度低於 640 x 360，最多支援的畫面播放速率是 15 fps。</span><span class="sxs-lookup"><span data-stu-id="6de75-142">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="6de75-143">電腦不含 DXVA 且不含硬體加速編碼器</span><span class="sxs-lookup"><span data-stu-id="6de75-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de75-144">可使用編碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-145">可使用解碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-146">需求</span><span class="sxs-lookup"><span data-stu-id="6de75-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de75-147">424 x 240</span><span class="sxs-lookup"><span data-stu-id="6de75-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="6de75-148">424 x 240 （640 x 360，15 fps，如接收僅案例）</span><span class="sxs-lookup"><span data-stu-id="6de75-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="6de75-149">1 核心且 VideoEncodeScore ≥ 4.0</span><span class="sxs-lookup"><span data-stu-id="6de75-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-150">640 x 360</span><span class="sxs-lookup"><span data-stu-id="6de75-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="6de75-151">640 x 360</span><span class="sxs-lookup"><span data-stu-id="6de75-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="6de75-152">2 核心且 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6de75-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-153">640 x 360</span><span class="sxs-lookup"><span data-stu-id="6de75-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="6de75-154">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-155">2 核心且 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6de75-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-156">640 x 360</span><span class="sxs-lookup"><span data-stu-id="6de75-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="6de75-157">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-158">4 核心且 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6de75-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-159">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-160">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-161">4 核心且 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6de75-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-162">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-163">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-164">4 核心且 VideoEncodeScore ≥ 7.3</span><span class="sxs-lookup"><span data-stu-id="6de75-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-165">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-166">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-167">不適用</span><span class="sxs-lookup"><span data-stu-id="6de75-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="6de75-168">電腦含 DXVA 但不含硬體加速編碼器</span><span class="sxs-lookup"><span data-stu-id="6de75-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de75-169">可使用編碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-170">可使用解碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-171">需求</span><span class="sxs-lookup"><span data-stu-id="6de75-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de75-172">424 x 240</span><span class="sxs-lookup"><span data-stu-id="6de75-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="6de75-173">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-174">1 核心且 VideoEncodeScore ≥ 3.0</span><span class="sxs-lookup"><span data-stu-id="6de75-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-175">640 x 360</span><span class="sxs-lookup"><span data-stu-id="6de75-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="6de75-176">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-177">2 核心且 VideoEncodeScore ≥ 4.5</span><span class="sxs-lookup"><span data-stu-id="6de75-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-178">高 960 x 540</span><span class="sxs-lookup"><span data-stu-id="6de75-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="6de75-179">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-180">2 核心且 VideoEncodeScore ≥ 6.0</span><span class="sxs-lookup"><span data-stu-id="6de75-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-181">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-182">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-183">4 核心且 VideoEncodeScore ≥ 6.7</span><span class="sxs-lookup"><span data-stu-id="6de75-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6de75-184">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-185">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-186">4 核心且 VideoEncodeScore ≥ 8.2</span><span class="sxs-lookup"><span data-stu-id="6de75-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6de75-187">在 Windows 7 上的 WinSAT 分數僅限於 7.9 的最大值。</span><span class="sxs-lookup"><span data-stu-id="6de75-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="6de75-188">因此，不含硬體加速編碼器的電腦的編碼功能只可在 Windows 8 或 Windows 8.1，其中的最大 WinSAT 分數是 9.9 達成。</span><span class="sxs-lookup"><span data-stu-id="6de75-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="6de75-189">電腦含 DXVA 且含 Intel HD Graphics 硬體加速編碼器</span><span class="sxs-lookup"><span data-stu-id="6de75-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6de75-190">可使用編碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-191">可使用解碼器的解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="6de75-192">需求</span><span class="sxs-lookup"><span data-stu-id="6de75-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de75-193">1280 x 720</span><span class="sxs-lookup"><span data-stu-id="6de75-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="6de75-194">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-195">所有第 2 個和第 3 層代 Intel HD Graphics</span><span class="sxs-lookup"><span data-stu-id="6de75-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-196">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-197">1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="6de75-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="6de75-198">第 2 個和第 3 代 Intel HD Graphics 且 GraphicsScore ≥ 5.0</span><span class="sxs-lookup"><span data-stu-id="6de75-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="6de75-199">行動裝置視訊功能</span><span class="sxs-lookup"><span data-stu-id="6de75-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="6de75-200">下表說明支援的行動裝置的最大視訊功能。</span><span class="sxs-lookup"><span data-stu-id="6de75-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="6de75-201">如需有關行動裝置支援，請參閱[Planning for Lync Server 2013 中的行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="6de75-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="6de75-202">功能</span><span class="sxs-lookup"><span data-stu-id="6de75-202">Feature</span></span></th>
<th><span data-ttu-id="6de75-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="6de75-203">Windows Phone</span></span></th>
<th><span data-ttu-id="6de75-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="6de75-204">iPhone</span></span></th>
<th><span data-ttu-id="6de75-205">iPad</span><span class="sxs-lookup"><span data-stu-id="6de75-205">iPad</span></span></th>
<th><span data-ttu-id="6de75-206">Android</span><span class="sxs-lookup"><span data-stu-id="6de75-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6de75-207">H.264 編碼最大解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6de75-208">VGA</span><span class="sxs-lookup"><span data-stu-id="6de75-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="6de75-209">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6de75-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6de75-210">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6de75-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6de75-211">720 p: iPhone 5S 和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6de75-212">VGA: iPad 2 和更新版本/iPad 浮動 1 和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6de75-213">720 p: iPad 空調/iPad 迷你 2/iPad 專業版和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6de75-214">最多 VGA 根據裝置型號</span><span class="sxs-lookup"><span data-stu-id="6de75-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6de75-215">H.264 解碼最大解析度</span><span class="sxs-lookup"><span data-stu-id="6de75-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="6de75-216">VGA</span><span class="sxs-lookup"><span data-stu-id="6de75-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="6de75-217">QVGA: iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="6de75-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="6de75-218">VGA: iPhone 5</span><span class="sxs-lookup"><span data-stu-id="6de75-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="6de75-219">720 p: iPhone 5S 和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="6de75-220">VGA: iPad 2 和更新版本/iPad 浮動 1 和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="6de75-221">720 p: iPad 空調/iPad 迷你 2/iPad 專業版和更新版本</span><span class="sxs-lookup"><span data-stu-id="6de75-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="6de75-222">最多 VGA 根據裝置型號</span><span class="sxs-lookup"><span data-stu-id="6de75-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

