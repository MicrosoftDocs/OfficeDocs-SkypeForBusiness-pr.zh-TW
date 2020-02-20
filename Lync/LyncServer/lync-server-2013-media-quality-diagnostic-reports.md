---
title: Lync Server 2013： 媒體品質診斷報告
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
ms.openlocfilehash: c1fd162b0b9c90fd1a266b6bf4213ef804f35f50
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="abbac-102">Lync Server 2013 中的媒體品質診斷報告</span><span class="sxs-lookup"><span data-stu-id="abbac-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abbac-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="abbac-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="abbac-104">媒體品質診斷報告提供有關通話品質]，以及通話失敗的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="abbac-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abbac-105">本章節內容</span><span class="sxs-lookup"><span data-stu-id="abbac-105">In This Section</span></span>

  - <span data-ttu-id="abbac-106">[Lync Server 2013 中的媒體品質摘要報告](lync-server-2013-media-quality-summary-report.md)   提供整體品質資料，對於各種端點類型，包括 Enterprise Voice 對等通話、 Enterprise Voice 會議通話，以及通話，至少部分，公用交換電話網路 (PSTN)。</span><span class="sxs-lookup"><span data-stu-id="abbac-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="abbac-107">[Lync Server 2013 中的媒體品質比較報告](lync-server-2013-media-quality-comparison-report.md)   不同類型的音訊通話 （例如，撥打透過無線網路和有線連線之間進行的呼叫比較） 提供的通話比較品質值。</span><span class="sxs-lookup"><span data-stu-id="abbac-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="abbac-108">[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)   列出經歷最多問題，這種主要的品質指標為效能下降、 封包遺失及抖動等等的伺服器。</span><span class="sxs-lookup"><span data-stu-id="abbac-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="abbac-109">[Lync Server 2013 中的位置報告](lync-server-2013-location-report.md)   提供的網路位置和每個位置進行通話的媒體品質摘要清單。</span><span class="sxs-lookup"><span data-stu-id="abbac-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="abbac-110">基於此報告的詳細資訊，位置是以 IP 子網路為基礎。</span><span class="sxs-lookup"><span data-stu-id="abbac-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="abbac-111">[Lync Server 2013 中的裝置報告](lync-server-2013-device-report.md)   提供企業語音通話及它所用的裝置摘要包含裝置之通話的平均媒體品質。</span><span class="sxs-lookup"><span data-stu-id="abbac-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="abbac-112">[Lync Server 2013 中通話清單報告](lync-server-2013-call-list-report.md)   提供電話所撥打或接聽組織內的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="abbac-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="abbac-113">[Lync Server 2013 中的呼叫詳細資料報告](lync-server-2013-call-detail-report.md)   提供電話撥出或接聽組織內的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="abbac-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="abbac-114">[在 [Lync Server 2013 伺服器媒體品質趨勢報告](lync-server-2013-server-media-quality-trend-report.md)   可讓您以圖形方式比較最多 5 個伺服器上的經驗品質計量，例如通話數量、 收訊不良通話百分比、 封包遺失及抖動。</span><span class="sxs-lookup"><span data-stu-id="abbac-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="abbac-115">[Lync Server 2013 中的媒體品質計量散佈報告](lync-server-2013-media-quality-metrics-distribution-report.md)   提供圖表，顯示為經驗品質評量，例如抖動或封包遺失的通訊值。</span><span class="sxs-lookup"><span data-stu-id="abbac-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="abbac-116">[Lync Server 2013 中的位置趨勢報告](lync-server-2013-location-trend-report.md)   提供通話品質趨勢資訊的網路位置。</span><span class="sxs-lookup"><span data-stu-id="abbac-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

