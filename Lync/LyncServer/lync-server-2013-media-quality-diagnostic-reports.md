---
title: Lync Server 2013：媒體質量診斷報告
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
ms.openlocfilehash: 1f7db75e8f4e6e7d8b8a36d0e5ba614ac89c22e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="09796-102">Lync Server 2013 中的媒體質量診斷報告</span><span class="sxs-lookup"><span data-stu-id="09796-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09796-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="09796-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="09796-104">媒體質量診斷報告提供通話品質的相關資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="09796-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09796-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="09796-105">In This Section</span></span>

  - <span data-ttu-id="09796-106">[Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   中的 [媒體質量摘要] 報告提供不同端點類型的整體品質資料，包括企業語音對等通話、企業語音會議通話，以及在公用交換電話網絡（PSTN）中至少有部分的通話。</span><span class="sxs-lookup"><span data-stu-id="09796-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="09796-107">[Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   中的媒體質量比較報告，可比較不同類型音訊通話的通話品質值（例如，透過無線網路撥打，以及透過有線連線進行通話）。</span><span class="sxs-lookup"><span data-stu-id="09796-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="09796-108">[Lync server 2013](lync-server-2013-server-performance-report.md)   中的 [伺服器效能報告] 會根據這些重要品質度量單位的度量、資料包遺失和抖動，列出已遇到最大問題的伺服器。</span><span class="sxs-lookup"><span data-stu-id="09796-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="09796-109">[Lync Server 2013](lync-server-2013-location-report.md)   中的 [位置] 報告，提供網路位置的清單，以及每個位置所發生之通話的媒體質量摘要。</span><span class="sxs-lookup"><span data-stu-id="09796-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="09796-110">針對此報告的用途，位置是以 IP 子網為基礎。</span><span class="sxs-lookup"><span data-stu-id="09796-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="09796-111">[Lync Server 2013](lync-server-2013-device-report.md)   中的 [裝置報表] 提供企業語音通話所使用裝置的摘要，並包括依裝置通話的平均媒體質量。</span><span class="sxs-lookup"><span data-stu-id="09796-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="09796-112">[Lync Server 2013](lync-server-2013-call-list-report.md)   中的通話清單報告，提供在貴組織內撥打或接聽電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="09796-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="09796-113">[Lync Server 2013](lync-server-2013-call-detail-report.md)   中的 [通話詳細資料] 報告，提供在貴組織內撥打或接聽電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="09796-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="09796-114">[Lync server 2013](lync-server-2013-server-media-quality-trend-report.md)   中的 [伺服器媒體質量趨勢] 報告，可讓您以圖形方式比較多達5台伺服器，包括通話量、通話百分比差、資料包遺失和抖動等品質統計資料。</span><span class="sxs-lookup"><span data-stu-id="09796-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="09796-115">[Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   中的媒體質量度量分佈報告提供的圖形會顯示經驗統計資料（例如抖動或資料包遺失）的分配值。</span><span class="sxs-lookup"><span data-stu-id="09796-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="09796-116">[Lync Server 2013](lync-server-2013-location-trend-report.md)   中的 [位置趨勢] 報告，提供網路位置的通話品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="09796-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

