---
title: Lync Server 2013： Lync 用戶端影片需求
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
ms.openlocfilehash: 883242824a6dfc45dbae923736a7a88bc1784d62
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506060"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="d54f2-102">Lync Server 2013 的 lync 用戶端影片需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-102">Lync client video requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d54f2-103">_**主題上次修改日期：** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="d54f2-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="d54f2-104">本節說明 Lync 2013 影片通話的影片硬體支援，並說明如何判斷各種電腦、平板電腦及行動裝置設定的預期影片品質。</span><span class="sxs-lookup"><span data-stu-id="d54f2-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="d54f2-105">Windows 桌面和平板電腦影片需求和功能</span><span class="sxs-lookup"><span data-stu-id="d54f2-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="d54f2-106">Lync 2013 針對根據 H-p/MPEG-4 第10部分的先進視頻編碼標準，引入影片編碼和解碼的硬體加速。</span><span class="sxs-lookup"><span data-stu-id="d54f2-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="d54f2-107">此功能可讓具有較低 CPU 時脈速度的電腦編碼和解碼較高解析度的影片。</span><span class="sxs-lookup"><span data-stu-id="d54f2-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="d54f2-108">影片硬體需求會因電腦設定和影片解析度的需要而異。</span><span class="sxs-lookup"><span data-stu-id="d54f2-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="d54f2-109">影片硬體需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d54f2-110">功能</span><span class="sxs-lookup"><span data-stu-id="d54f2-110">Feature</span></span></th>
<th><span data-ttu-id="d54f2-111">需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-112">使用 DirectX 影片加速 (DXVA) 硬體加速的 .H 解碼</span><span class="sxs-lookup"><span data-stu-id="d54f2-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d54f2-113">圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</span><span class="sxs-lookup"><span data-stu-id="d54f2-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="d54f2-114">必須安裝最新的圖形卡驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d54f2-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="d54f2-115">如需有關解碼模式的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> 。</span><span class="sxs-lookup"><span data-stu-id="d54f2-115">For details about decoding modes, see <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-116">硬體加速的 H-p 編碼：晶片組需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="d54f2-117">下列為支援的 Intel 硬體加速視頻編碼方案：</span><span class="sxs-lookup"><span data-stu-id="d54f2-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="d54f2-118">第二和第三代 Intel HD Graphics 2000、2500、3000及4000晶片組 (或更新版本) 整合的硬體視頻編碼器。</span><span class="sxs-lookup"><span data-stu-id="d54f2-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="d54f2-119">需要安裝 Intel HD Graphics 驅動程式15.28.9.2884 或最新的驅動程式，其中包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="d54f2-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="d54f2-120">顯示驅動程式9.17.10.2884 或最新的驅動程式</span><span class="sxs-lookup"><span data-stu-id="d54f2-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="d54f2-121">硬體媒體基礎轉換 (HMFT) 版本3.12.10.31 或最新的 HMFT</span><span class="sxs-lookup"><span data-stu-id="d54f2-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="d54f2-122">以下是支援的 AMD 硬體加速視頻編碼方案 (需要 Lync Server 2013) CU1 更新：</span><span class="sxs-lookup"><span data-stu-id="d54f2-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="d54f2-123">AMD Video 編解碼器引擎，可在許多獨立的圖形卡中，以及 AMD A Series 加速處理器的整合式加速處理單位。</span><span class="sxs-lookup"><span data-stu-id="d54f2-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="d54f2-124">9.12.0.0 或更新版本必須安裝 AMD Video 編解碼器引擎驅動程式。</span><span class="sxs-lookup"><span data-stu-id="d54f2-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-125">硬體加速的 H-p 編碼：攝像頭需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="d54f2-126">帶有整合的 H-p 硬體編碼器的 USB 影片相機，其符合 USB Video 類別 (UVC) 規格版本1.5。</span><span class="sxs-lookup"><span data-stu-id="d54f2-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="d54f2-127">Lync 2013 支援具有 Windows 8 或 Windows 8.1 的 UVC 1.5 攝像頭，這包括支援 UVC 1.5。</span><span class="sxs-lookup"><span data-stu-id="d54f2-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="d54f2-128">由於 Windows 7 不包含支援 UVC 1.5，所以 Lync 2013 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝像頭。</span><span class="sxs-lookup"><span data-stu-id="d54f2-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="d54f2-129">決定 H-p 影片的編碼和解碼功能</span><span class="sxs-lookup"><span data-stu-id="d54f2-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="d54f2-130">一般來說，有四個主要因素會決定特定電腦設定的最大編碼和解碼功能：</span><span class="sxs-lookup"><span data-stu-id="d54f2-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="d54f2-131">使用 DXVA 支援硬體加速解碼</span><span class="sxs-lookup"><span data-stu-id="d54f2-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="d54f2-132">硬體加速編碼支援</span><span class="sxs-lookup"><span data-stu-id="d54f2-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="d54f2-133">實體核心數目</span><span class="sxs-lookup"><span data-stu-id="d54f2-133">Number of physical cores</span></span>

  - <span data-ttu-id="d54f2-134">Windows 經驗索引 (WEI) </span><span class="sxs-lookup"><span data-stu-id="d54f2-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="d54f2-135">Windows 系統評定工具 (WinSAT) 會決定 WEI。</span><span class="sxs-lookup"><span data-stu-id="d54f2-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="d54f2-136">當您執行 WinSAT 工具時，它會在% windir% \\ 效能的 \\ WinSAT 資料目錄中產生電腦上的正規評估 XML 檔 \\ 。</span><span class="sxs-lookup"><span data-stu-id="d54f2-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="d54f2-137">此 XML 檔包含下列兩個分數，尤其是決定編碼和解碼功能的特別重要性：</span><span class="sxs-lookup"><span data-stu-id="d54f2-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="d54f2-138">VideoEncodeScore 指出電腦的軟體型影片功能。</span><span class="sxs-lookup"><span data-stu-id="d54f2-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="d54f2-139">GraphicsScore 值表示電腦的硬體加速編碼功能。</span><span class="sxs-lookup"><span data-stu-id="d54f2-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="d54f2-140">下列三個表格針對不同的電腦類型，根據其所支援的硬體加速度，說明其編碼和解碼功能的上限。</span><span class="sxs-lookup"><span data-stu-id="d54f2-140">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="d54f2-141">針對640x360 及更高版本，支援的框架速率上限為每秒30個畫面 (fps) 。</span><span class="sxs-lookup"><span data-stu-id="d54f2-141">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="d54f2-142">對於低於640x360 的解析度，支援的最大畫面播放速率為 15 fps。</span><span class="sxs-lookup"><span data-stu-id="d54f2-142">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="d54f2-143">沒有 DXVA 且不含硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="d54f2-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d54f2-144">支援的編碼器解析</span><span class="sxs-lookup"><span data-stu-id="d54f2-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-145">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="d54f2-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-146">需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-147">424x240</span><span class="sxs-lookup"><span data-stu-id="d54f2-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="d54f2-148">424x240 (640x360 at 15fps 僅限接收案例) </span><span class="sxs-lookup"><span data-stu-id="d54f2-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="d54f2-149">1核心和 VideoEncodeScore ≧4。0</span><span class="sxs-lookup"><span data-stu-id="d54f2-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-150">640x360</span><span class="sxs-lookup"><span data-stu-id="d54f2-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="d54f2-151">640x360</span><span class="sxs-lookup"><span data-stu-id="d54f2-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="d54f2-152">2核心和 VideoEncodeScore ≧4。5</span><span class="sxs-lookup"><span data-stu-id="d54f2-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-153">640x360</span><span class="sxs-lookup"><span data-stu-id="d54f2-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="d54f2-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-155">2核心和 VideoEncodeScore ≧4。5</span><span class="sxs-lookup"><span data-stu-id="d54f2-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-156">640x360</span><span class="sxs-lookup"><span data-stu-id="d54f2-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="d54f2-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-158">4核心和 VideoEncodeScore ≧4。5</span><span class="sxs-lookup"><span data-stu-id="d54f2-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-161">4核心和 VideoEncodeScore ≧7。3</span><span class="sxs-lookup"><span data-stu-id="d54f2-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-164">4核心和 VideoEncodeScore ≧7。3</span><span class="sxs-lookup"><span data-stu-id="d54f2-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-167">不適用</span><span class="sxs-lookup"><span data-stu-id="d54f2-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="d54f2-168">具有 DXVA 但不含硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="d54f2-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d54f2-169">支援的編碼器解析</span><span class="sxs-lookup"><span data-stu-id="d54f2-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-170">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="d54f2-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-171">需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-172">424x240</span><span class="sxs-lookup"><span data-stu-id="d54f2-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="d54f2-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-174">1核心和 VideoEncodeScore ≧3。0</span><span class="sxs-lookup"><span data-stu-id="d54f2-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-175">640x360</span><span class="sxs-lookup"><span data-stu-id="d54f2-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="d54f2-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-177">2核心和 VideoEncodeScore ≧4。5</span><span class="sxs-lookup"><span data-stu-id="d54f2-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-178">960x540</span><span class="sxs-lookup"><span data-stu-id="d54f2-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="d54f2-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-180">2核心和 VideoEncodeScore ≧6。0</span><span class="sxs-lookup"><span data-stu-id="d54f2-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-183">4核心和 VideoEncodeScore ≧6。7</span><span class="sxs-lookup"><span data-stu-id="d54f2-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-186">4核心和 VideoEncodeScore ≧8。2</span><span class="sxs-lookup"><span data-stu-id="d54f2-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="d54f2-187">Windows 7 上的 WinSAT 分數限制為最大值7.9。</span><span class="sxs-lookup"><span data-stu-id="d54f2-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="d54f2-188">因此，沒有硬體加速編碼器的電腦編碼功能只能在 Windows 8 或 Windows 8.1 （最大的 WinSAT 分數為9.9）上完成。</span><span class="sxs-lookup"><span data-stu-id="d54f2-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="d54f2-189">具有 DXVA 且具有英特爾 HD 圖形硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="d54f2-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d54f2-190">支援的編碼器解析</span><span class="sxs-lookup"><span data-stu-id="d54f2-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-191">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="d54f2-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="d54f2-192">需求</span><span class="sxs-lookup"><span data-stu-id="d54f2-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="d54f2-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="d54f2-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-195">所有第二個和第三代的 Intel HD 顯卡</span><span class="sxs-lookup"><span data-stu-id="d54f2-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="d54f2-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="d54f2-198">第二和第三代 Intel HD Graphics 和 GraphicsScore ≧5。0</span><span class="sxs-lookup"><span data-stu-id="d54f2-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="d54f2-199">行動裝置影片功能</span><span class="sxs-lookup"><span data-stu-id="d54f2-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="d54f2-200">下表說明支援的行動裝置的最大視頻功能。</span><span class="sxs-lookup"><span data-stu-id="d54f2-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="d54f2-201">如需行動裝置支援的詳細資訊，請參閱 [在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="d54f2-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="d54f2-202">功能</span><span class="sxs-lookup"><span data-stu-id="d54f2-202">Feature</span></span></th>
<th><span data-ttu-id="d54f2-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="d54f2-203">Windows Phone</span></span></th>
<th><span data-ttu-id="d54f2-204">Iphone</span><span class="sxs-lookup"><span data-stu-id="d54f2-204">iPhone</span></span></th>
<th><span data-ttu-id="d54f2-205">Ipad</span><span class="sxs-lookup"><span data-stu-id="d54f2-205">iPad</span></span></th>
<th><span data-ttu-id="d54f2-206">Android</span><span class="sxs-lookup"><span data-stu-id="d54f2-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d54f2-207">最高解析度的264編碼</span><span class="sxs-lookup"><span data-stu-id="d54f2-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="d54f2-208">Vga</span><span class="sxs-lookup"><span data-stu-id="d54f2-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="d54f2-209">QVGA： iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="d54f2-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="d54f2-210">VGA： iPhone 5</span><span class="sxs-lookup"><span data-stu-id="d54f2-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="d54f2-211">720p： iPhone 5S 及更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="d54f2-212">VGA： iPad 2 和更新版本/iPad 迷你1和更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="d54f2-213">720p： iPad Air/iPad 迷你 2/iPad Pro 和更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="d54f2-214">取決於裝置模型，最多 VGA</span><span class="sxs-lookup"><span data-stu-id="d54f2-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d54f2-215">-264 解碼最大解析度</span><span class="sxs-lookup"><span data-stu-id="d54f2-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="d54f2-216">Vga</span><span class="sxs-lookup"><span data-stu-id="d54f2-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="d54f2-217">QVGA： iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="d54f2-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="d54f2-218">VGA： iPhone 5</span><span class="sxs-lookup"><span data-stu-id="d54f2-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="d54f2-219">720p： iPhone 5S 及更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="d54f2-220">VGA： iPad 2 和更新版本/iPad 迷你1和更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="d54f2-221">720p： iPad Air/iPad 迷你 2/iPad Pro 和更新版本</span><span class="sxs-lookup"><span data-stu-id="d54f2-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="d54f2-222">取決於裝置模型，最多 VGA</span><span class="sxs-lookup"><span data-stu-id="d54f2-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

