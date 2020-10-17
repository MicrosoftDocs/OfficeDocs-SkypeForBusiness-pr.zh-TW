---
title: Lync Server 2013：媒體質量診斷報告
description: Lync Server 2013：媒體質量診斷報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e346d0f9b8997158cb926ad830d5477950e846d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548209"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="23408-103">Lync Server 2013 中的媒體質量診斷報告</span><span class="sxs-lookup"><span data-stu-id="23408-103">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23408-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="23408-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="23408-105">媒體質量診斷報告提供有關通話品質的資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="23408-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="23408-106">本章節內容</span><span class="sxs-lookup"><span data-stu-id="23408-106">In This Section</span></span>

  - <span data-ttu-id="23408-107">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)     中的媒體質量摘要報告提供不同端點類型的整體品質資料，包括企業語音對等通話、Enterprise Voice 會議通話，以及至少在公用交換電話網路 (PSTN) 上的通話。</span><span class="sxs-lookup"><span data-stu-id="23408-107">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="23408-108">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     中的媒體質量比較報告會比較不同音訊通話類型的通話品質值 (例如，透過無線網路撥打的通話，以及透過有線連線) 進行的通話。</span><span class="sxs-lookup"><span data-stu-id="23408-108">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="23408-109">[Lync server 2013](lync-server-2013-server-performance-report.md)     中的伺服器效能報告列出最有問題的伺服器，其依據是效能、封包遺失和抖動等這類重要品質度量值的度量。</span><span class="sxs-lookup"><span data-stu-id="23408-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="23408-110">[Lync Server 2013](lync-server-2013-location-report.md)     中的位置報告提供網路位置清單，以及在每個地點所發生之通話的媒體質量摘要。</span><span class="sxs-lookup"><span data-stu-id="23408-110">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="23408-111">針對此報告的目的，位置是以 IP 子網為基礎。</span><span class="sxs-lookup"><span data-stu-id="23408-111">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="23408-112">[Lync Server 2013](lync-server-2013-device-report.md)     中的裝置報表提供用於 Enterprise Voice 通話的裝置摘要，包括裝置通話的平均媒體質量。</span><span class="sxs-lookup"><span data-stu-id="23408-112">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="23408-113">[Lync Server 2013](lync-server-2013-call-list-report.md)     中的通話清單報告提供組織內撥打或接收電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="23408-113">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="23408-114">[Lync Server 2013](lync-server-2013-call-detail-report.md)     中的詳細通話報告提供組織內撥打或接聽電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="23408-114">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="23408-115">[Lync server 2013 中的伺服器媒體質量趨勢報告](lync-server-2013-server-media-quality-trend-report.md)    提供一種方式，讓您以圖形方式比較最多5台伺服器的經驗品質計量，例如通話量、通話百分比、封包遺失和抖動。</span><span class="sxs-lookup"><span data-stu-id="23408-115">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="23408-116">[Lync Server 2013 中的媒體質量計量散佈報告](lync-server-2013-media-quality-metrics-distribution-report.md)    會提供圖表，顯示品質品質度量（如抖動或封包遺失）的散佈價值。</span><span class="sxs-lookup"><span data-stu-id="23408-116">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="23408-117">[Lync Server 2013](lync-server-2013-location-trend-report.md)     中的位置趨勢報告提供網路位置的呼叫品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="23408-117">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

