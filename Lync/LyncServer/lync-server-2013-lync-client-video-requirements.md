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

# <a name="lync-client-video-requirements-for-lync-server-2013"></a><span data-ttu-id="9f8ff-102">Lync Server 2013 的 lync 用戶端視頻需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-102">Lync client video requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f8ff-103">_**主題上次修改日期：** 2016-01-29_</span><span class="sxs-lookup"><span data-stu-id="9f8ff-103">_**Topic Last Modified:** 2016-01-29_</span></span>

<span data-ttu-id="9f8ff-104">本節說明 Lync 2013 視頻通話的視頻硬體支援，並說明如何判斷各種電腦、平板電腦和行動裝置設定的預期視頻品質。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-104">This section describes video hardware support for Lync 2013 video calls and describes how to determine the expected video quality for various computer, tablet, and mobile device configurations.</span></span>

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a><span data-ttu-id="9f8ff-105">Windows 桌面和平板電腦影片需求與功能</span><span class="sxs-lookup"><span data-stu-id="9f8ff-105">Windows Desktop and Tablet Video Requirements and Capabilities</span></span>

<span data-ttu-id="9f8ff-106">Lync 2013 會針對視頻編碼與解碼提供硬體加速，並根據 H-p/MPEG-4 個第10部分高級視頻編碼標準來進行。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-106">Lync 2013 introduces hardware acceleration for video encoding and decoding based on the H.264/MPEG-4 Part 10 Advanced Video Coding standard.</span></span> <span data-ttu-id="9f8ff-107">此功能可讓使用較低 CPU 時脈速度的電腦來編碼及解碼較高的解析度影片。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-107">This feature allows computers with lower CPU clock speeds to encode and decode higher resolution video.</span></span> <span data-ttu-id="9f8ff-108">根據電腦設定與視頻解析度的不同，視頻硬體需求會有所不同。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-108">Video hardware requirements vary depending on the computer configuration and the video resolution wanted.</span></span>

<div>

## <a name="video-hardware-requirements"></a><span data-ttu-id="9f8ff-109">影片硬體需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-109">Video Hardware Requirements</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f8ff-110">功能</span><span class="sxs-lookup"><span data-stu-id="9f8ff-110">Feature</span></span></th>
<th><span data-ttu-id="9f8ff-111">需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-111">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-112">使用 DirectX Video 加速進行硬體加速的264解碼（DXVA）</span><span class="sxs-lookup"><span data-stu-id="9f8ff-112">Hardware accelerated H.264 decoding using DirectX Video Acceleration (DXVA)</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="9f8ff-113">圖形卡必須支援 DirectX 9.0，且必須公開 DXVA2_ModeH264_VLD_NoFGT 解碼模式。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-113">Graphics card must support DirectX 9.0 and must expose the DXVA2_ModeH264_VLD_NoFGT decoding mode.</span></span></p></li>
<li><p><span data-ttu-id="9f8ff-114">必須安裝最新的圖形卡驅動程式。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-114">The latest graphics card driver must be installed.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="9f8ff-115">如需解碼模式的詳細資訊<A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>，請參閱。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-115">For details about decoding modes, see <A href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</A>.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-116">硬體加速的264編碼：晶片需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-116">Hardware accelerated H.264 encoding: Chipset Requirements</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-117">支援下列 Intel 硬體加速視頻編碼解決方案：</span><span class="sxs-lookup"><span data-stu-id="9f8ff-117">The following Intel hardware accelerated video encoding solutions are supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f8ff-118">第二和第三代英特爾高質圖形2000、2500、3000和4000晶片組（或更新版本），集成硬體視頻編碼器。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-118">Second and third generation Intel HD Graphics 2000, 2500, 3000, and 4000 chipsets (or later versions) with integrated hardware video encoders.</span></span> <span data-ttu-id="9f8ff-119">必須安裝英特爾高質圖形驅動程式15.28.9.2884 或包含下列的最新驅動程式：</span><span class="sxs-lookup"><span data-stu-id="9f8ff-119">Installation of the Intel HD Graphics driver 15.28.9.2884 or the latest driver containing the following is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="9f8ff-120">顯示驅動程式9.17.10.2884 或最新的驅動程式</span><span class="sxs-lookup"><span data-stu-id="9f8ff-120">Display driver 9.17.10.2884 or the latest driver</span></span></p></li>
<li><p><span data-ttu-id="9f8ff-121">硬體媒體基礎轉換（HMFT）版本3.12.10.31 或最新 HMFT</span><span class="sxs-lookup"><span data-stu-id="9f8ff-121">Hardware media foundation transform (HMFT) version 3.12.10.31 or the latest HMFT</span></span></p></li>
</ul></li>
</ul>
<p><span data-ttu-id="9f8ff-122">支援下列 AMD 硬體加速視頻編碼解決方案（需要 Lync Server 2013 的 CU1 更新）：</span><span class="sxs-lookup"><span data-stu-id="9f8ff-122">The following AMD hardware accelerated video encoding solutions are supported (requires CU1 Updates for Lync Server 2013):</span></span></p>
<ul>
<li><p><span data-ttu-id="9f8ff-123">在幾個獨立的圖形卡中，以及 AMD A 系列加速處理器的整合式加速處理單元中提供的 AMD Video 編解碼器引擎。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-123">AMD Video Codec Engine, which is available in several discrete graphics cards and in integrated accelerated processing units of AMD A-Series Accelerated Processors.</span></span> <span data-ttu-id="9f8ff-124">必須安裝 AMD Video 編解碼器引擎驅動程式9.12.0.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-124">The AMD Video Codec Engine driver 9.12.0.0 or higher must be installed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-125">硬體加速的264編碼：相機需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-125">Hardware accelerated H.264 encoding: Camera Requirements</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-126">含集成式 H-p 硬體編碼器的 USB 攝影機，符合 USB Video Class （UVC）規格版本1.5。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-126">USB video cameras with integrated H.264 hardware encoder that conforms to the USB Video Class (UVC) specification version 1.5.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="9f8ff-127">Lync 2013 支援 Windows 8 或 Windows 8.1 的 UVC 1.5 攝影機，包括支援 UVC 1.5。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-127">Lync 2013 supports UVC 1.5 cameras with Windows 8 or Windows 8.1, which includes support for UVC 1.5.</span></span> <span data-ttu-id="9f8ff-128">因為 Windows 7 不包括 UVC 1.5 的支援，所以 Lync 2013 會將 UVC 1.5 相機視為不含硬體編碼支援的一般攝影機。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-128">Because Windows 7 does not include support for UVC 1.5, Lync 2013 treats UVC 1.5 cameras as regular cameras with no hardware encoding support.</span></span>


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a><span data-ttu-id="9f8ff-129">決定 H-p 的視頻編碼與解碼功能</span><span class="sxs-lookup"><span data-stu-id="9f8ff-129">Determining H.264 Video Encoding and Decoding Capabilities</span></span>

<span data-ttu-id="9f8ff-130">一般來說，以下四個主要因素決定了特定電腦設定的最大編碼與解碼功能：</span><span class="sxs-lookup"><span data-stu-id="9f8ff-130">Generally, there are four major factors that determine the maximum encoding and decoding capability of a particular computer configuration:</span></span>

  - <span data-ttu-id="9f8ff-131">支援使用 DXVA 進行硬體加速解碼</span><span class="sxs-lookup"><span data-stu-id="9f8ff-131">Support for hardware accelerated decoding by using DXVA</span></span>

  - <span data-ttu-id="9f8ff-132">硬體加速編碼支援</span><span class="sxs-lookup"><span data-stu-id="9f8ff-132">Support for hardware accelerated encoding</span></span>

  - <span data-ttu-id="9f8ff-133">物理內核數</span><span class="sxs-lookup"><span data-stu-id="9f8ff-133">Number of physical cores</span></span>

  - <span data-ttu-id="9f8ff-134">Windows 體驗索引（WEI）</span><span class="sxs-lookup"><span data-stu-id="9f8ff-134">Windows Experience Index (WEI)</span></span>

<span data-ttu-id="9f8ff-135">Windows 系統評定工具（WinSAT）會判斷 WEI。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-135">The Windows System Assessment Tool (WinSAT) determines the WEI.</span></span> <span data-ttu-id="9f8ff-136">當您執行 WinSAT 工具時，它會在電腦上產生一個正式的. 評估 XML 檔，在%\\windir\\%\\效能資料目錄中。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-136">When you run the WinSAT tool, it generates a Formal.Assessment XML document on the computer in the %windir%\\Performance\\WinSAT\\DataStore directory.</span></span> <span data-ttu-id="9f8ff-137">這個 XML 檔案包含下列兩個分數，對於判斷編碼與解碼功能而言是特別重要的：</span><span class="sxs-lookup"><span data-stu-id="9f8ff-137">This XML file contains the following two scores that are of particular importance for determining encoding and decoding capabilities:</span></span>

  - <span data-ttu-id="9f8ff-138">VideoEncodeScore 表示電腦的軟體影片編碼功能。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-138">The VideoEncodeScore indicates the software-based video encoding capability of the computer.</span></span>

  - <span data-ttu-id="9f8ff-139">GraphicsScore 值代表電腦的硬體加速編碼功能。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-139">The GraphicsScore value indicates the hardware accelerated encoding capability of the computer.</span></span>

<span data-ttu-id="9f8ff-140">下列三個表格會根據其支援的硬體加速，說明不同電腦類型的最大編碼與解碼功能。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-140">The following three tables explain the maximum encoding and decoding capability for different PC types depending on what hardware acceleration they support.</span></span> <span data-ttu-id="9f8ff-141">針對640x360 及更高版本的解析度，支援的畫面播放速率上限為30個畫面/秒（fps）。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-141">For resolutions of 640x360 and higher, the maximum supported frame rate is 30 frames per second (fps).</span></span> <span data-ttu-id="9f8ff-142">針對低於640x360 的解析度，支援的畫面播放速率上限為 15 fps。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-142">For resolutions lower than 640x360, the maximum supported frame rate is 15 fps.</span></span>

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a><span data-ttu-id="9f8ff-143">不含 DXVA 且沒有硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="9f8ff-143">Computer Without DXVA And Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f8ff-144">支援的編碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-144">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-145">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-145">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-146">需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-146">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-147">424x240</span><span class="sxs-lookup"><span data-stu-id="9f8ff-147">424x240</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-148">424x240 （640x360 at 僅限接收案例的15fps）</span><span class="sxs-lookup"><span data-stu-id="9f8ff-148">424x240 (640x360 at 15fps for receive only scenarios)</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-149">1核與 VideoEncodeScore ≥4。0</span><span class="sxs-lookup"><span data-stu-id="9f8ff-149">1 Core and VideoEncodeScore ≥ 4.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-150">640x360</span><span class="sxs-lookup"><span data-stu-id="9f8ff-150">640x360</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-151">640x360</span><span class="sxs-lookup"><span data-stu-id="9f8ff-151">640x360</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-152">2核與 VideoEncodeScore ≥4。5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-152">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-153">640x360</span><span class="sxs-lookup"><span data-stu-id="9f8ff-153">640x360</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-154">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-154">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-155">2核與 VideoEncodeScore ≥4。5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-155">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-156">640x360</span><span class="sxs-lookup"><span data-stu-id="9f8ff-156">640x360</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-157">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-157">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-158">4核與 VideoEncodeScore ≥4。5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-158">4 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-159">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-159">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-160">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-160">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-161">4核與 VideoEncodeScore ≥7。3</span><span class="sxs-lookup"><span data-stu-id="9f8ff-161">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-162">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-162">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-163">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-163">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-164">4核與 VideoEncodeScore ≥7。3</span><span class="sxs-lookup"><span data-stu-id="9f8ff-164">4 Cores and VideoEncodeScore ≥ 7.3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-165">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-165">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-166">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-166">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-167">不適用</span><span class="sxs-lookup"><span data-stu-id="9f8ff-167">N/A</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a><span data-ttu-id="9f8ff-168">有 DXVA 但沒有硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="9f8ff-168">Computer With DXVA But Without Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f8ff-169">支援的編碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-169">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-170">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-170">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-171">需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-171">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-172">424x240</span><span class="sxs-lookup"><span data-stu-id="9f8ff-172">424x240</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-173">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-173">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-174">1核與 VideoEncodeScore ≥3。0</span><span class="sxs-lookup"><span data-stu-id="9f8ff-174">1 Core and VideoEncodeScore ≥ 3.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-175">640x360</span><span class="sxs-lookup"><span data-stu-id="9f8ff-175">640x360</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-176">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-176">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-177">2核與 VideoEncodeScore ≥4。5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-177">2 Cores and VideoEncodeScore ≥ 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-178">960x540</span><span class="sxs-lookup"><span data-stu-id="9f8ff-178">960x540</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-179">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-179">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-180">2核與 VideoEncodeScore ≥6。0</span><span class="sxs-lookup"><span data-stu-id="9f8ff-180">2 Cores and VideoEncodeScore ≥ 6.0</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-181">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-181">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-182">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-182">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-183">4核與 VideoEncodeScore ≥6。7</span><span class="sxs-lookup"><span data-stu-id="9f8ff-183">4 Cores and VideoEncodeScore ≥ 6.7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-184">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-184">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-185">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-185">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-186">4核與 VideoEncodeScore ≥8。2</span><span class="sxs-lookup"><span data-stu-id="9f8ff-186">4 Cores and VideoEncodeScore ≥ 8.2</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9f8ff-187">Windows 7 上的 WinSAT 得分限制為最大值7.9。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-187">The WinSAT score on Windows 7 is limited to a maximum of 7.9.</span></span> <span data-ttu-id="9f8ff-188">因此，只有在 Windows 8 或 Windows 8.1 上才能取得沒有硬體加速編碼器之電腦的編碼功能，其中最大的 WinSAT 分數為9.9。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-188">Therefore, the encoding capability for a computer without a hardware accelerated encoder can only be achieved on Windows 8 or Windows 8.1, where the maximum WinSAT score is 9.9.</span></span>



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a><span data-ttu-id="9f8ff-189">含 DXVA 及含英特爾高質圖形硬體加速編碼器的電腦</span><span class="sxs-lookup"><span data-stu-id="9f8ff-189">Computer With DXVA And With Intel HD Graphics Hardware Accelerated Encoder</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f8ff-190">支援的編碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-190">Capable Encoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-191">支援的解碼器解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-191">Capable Decoder Resolution</span></span></th>
<th><span data-ttu-id="9f8ff-192">需求</span><span class="sxs-lookup"><span data-stu-id="9f8ff-192">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-193">1280x720</span><span class="sxs-lookup"><span data-stu-id="9f8ff-193">1280x720</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-194">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-194">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-195">所有第二和第三代英特爾高質圖形</span><span class="sxs-lookup"><span data-stu-id="9f8ff-195">All 2nd and 3rd generation Intel HD Graphics</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-196">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-196">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-197">1920x1080</span><span class="sxs-lookup"><span data-stu-id="9f8ff-197">1920x1080</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-198">第二和第三代英特爾高質圖形及 GraphicsScore ≥5。0</span><span class="sxs-lookup"><span data-stu-id="9f8ff-198">2nd and 3rd generation Intel HD Graphics and GraphicsScore ≥ 5.0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a><span data-ttu-id="9f8ff-199">行動裝置影片功能</span><span class="sxs-lookup"><span data-stu-id="9f8ff-199">Mobile Device Video Capabilities</span></span>

<span data-ttu-id="9f8ff-200">下表說明支援行動裝置的最大視頻功能。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-200">The following table describes the maximum video capabilities for supported mobile devices.</span></span> <span data-ttu-id="9f8ff-201">如需行動裝置支援的詳細資訊，請參閱[在 Lync Server 2013 中規劃行動用戶端](lync-server-2013-planning-for-mobile-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="9f8ff-201">For more information about mobile device support, see [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).</span></span>


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
<th><span data-ttu-id="9f8ff-202">功能</span><span class="sxs-lookup"><span data-stu-id="9f8ff-202">Feature</span></span></th>
<th><span data-ttu-id="9f8ff-203">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="9f8ff-203">Windows Phone</span></span></th>
<th><span data-ttu-id="9f8ff-204">iPhone</span><span class="sxs-lookup"><span data-stu-id="9f8ff-204">iPhone</span></span></th>
<th><span data-ttu-id="9f8ff-205">iPad</span><span class="sxs-lookup"><span data-stu-id="9f8ff-205">iPad</span></span></th>
<th><span data-ttu-id="9f8ff-206">Android</span><span class="sxs-lookup"><span data-stu-id="9f8ff-206">Android</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f8ff-207">H-p 編碼最大解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-207">H.264 encoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-208">採用</span><span class="sxs-lookup"><span data-stu-id="9f8ff-208">VGA</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-209">QVGA： iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="9f8ff-209">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="9f8ff-210">VGA： iPhone 5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-210">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="9f8ff-211">720p： iPhone 5S 及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-211">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-212">VGA： iPad 2 及更新版本/iPad 迷你1及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-212">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="9f8ff-213">720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-213">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-214">最多 VGA （視裝置模型而定）</span><span class="sxs-lookup"><span data-stu-id="9f8ff-214">Up to VGA depending on device model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f8ff-215">H-p 解碼最大解析度</span><span class="sxs-lookup"><span data-stu-id="9f8ff-215">H.264 decoding maximum resolution</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-216">採用</span><span class="sxs-lookup"><span data-stu-id="9f8ff-216">VGA</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-217">QVGA： iPhone 4S</span><span class="sxs-lookup"><span data-stu-id="9f8ff-217">QVGA: iPhone 4S</span></span></p>
<p><span data-ttu-id="9f8ff-218">VGA： iPhone 5</span><span class="sxs-lookup"><span data-stu-id="9f8ff-218">VGA: iPhone 5</span></span></p>
<p><span data-ttu-id="9f8ff-219">720p： iPhone 5S 及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-219">720p: iPhone 5S and later</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-220">VGA： iPad 2 及更新版本/iPad 迷你1及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-220">VGA: iPad 2 and later/iPad mini 1 and later</span></span></p>
<p><span data-ttu-id="9f8ff-221">720p： iPad Air/iPad 迷你 2/iPad Pro 及更新版本</span><span class="sxs-lookup"><span data-stu-id="9f8ff-221">720p: iPad Air/iPad mini 2/iPad Pro and later</span></span></p></td>
<td><p><span data-ttu-id="9f8ff-222">最多 VGA （視裝置模型而定）</span><span class="sxs-lookup"><span data-stu-id="9f8ff-222">Up to VGA depending on device model</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

