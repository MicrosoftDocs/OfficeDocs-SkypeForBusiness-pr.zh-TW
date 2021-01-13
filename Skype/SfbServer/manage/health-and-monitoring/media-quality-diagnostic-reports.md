---
title: 商務用 Skype Server 中的媒體質量診斷報告
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: 摘要：瞭解商務用 Skype Server 中的媒體質量診斷報告。
ms.openlocfilehash: a00084605941af80435dd5da73efbfea89a6272f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827833"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="46c6e-103">商務用 Skype Server 中的媒體質量診斷報告</span><span class="sxs-lookup"><span data-stu-id="46c6e-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="46c6e-104">**摘要：** 深入瞭解商務用 Skype Server 中的媒體質量診斷報告。</span><span class="sxs-lookup"><span data-stu-id="46c6e-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="46c6e-105">媒體質量診斷報告提供有關通話品質的資訊，以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="46c6e-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="46c6e-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="46c6e-106">In this section</span></span>

- <span data-ttu-id="46c6e-107">[商務用 Skype Server 中的媒體質量摘要報告](summary.md) 提供不同端點類型的整體品質資料，包括企業語音對等通話、Enterprise Voice 會議通話，以及至少在公用交換電話網路 (PSTN) 上的通話。</span><span class="sxs-lookup"><span data-stu-id="46c6e-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="46c6e-108">[商務用 Skype Server 中的媒體質量比較報告](comparison.md) 會比較不同音訊通話類型的通話品質值 (例如，透過無線網路撥打的通話，以及透過有線連線) 進行的通話。</span><span class="sxs-lookup"><span data-stu-id="46c6e-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="46c6e-109">[商務用 Skype server 中的伺服器效能報告](server-performance.md) 列出最有問題的伺服器，其依據是效能、封包遺失和抖動等這類重要品質度量值的度量。</span><span class="sxs-lookup"><span data-stu-id="46c6e-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="46c6e-110">[商務用 Skype Server 中的位置報告](location-report.md) 提供網路位置清單，以及在每個地點所發生之通話的媒體質量摘要。</span><span class="sxs-lookup"><span data-stu-id="46c6e-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="46c6e-111">針對此報告的目的，位置是以 IP 子網為基礎。</span><span class="sxs-lookup"><span data-stu-id="46c6e-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="46c6e-112">[商務用 Skype Server 中的裝置報表](device-report.md) 提供用於 Enterprise Voice 通話的裝置摘要，包括裝置通話的平均媒體質量。</span><span class="sxs-lookup"><span data-stu-id="46c6e-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="46c6e-113">[商務用 Skype Server 中的通話清單報告](call-list-report-0.md) 提供組織內撥打或接收電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="46c6e-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="46c6e-114">[商務用 Skype Server 中的詳細通話報告](call-detail-report.md) 提供組織內撥打或接聽電話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="46c6e-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="46c6e-115">[商務用 Skype server 中的伺服器媒體質量趨勢報告](server-media-quality-trend-report.md) 提供一種方式，讓您可以以圖形方式，在經驗品質度量（如通話量、通話百分比、封包遺失及抖動）上，以圖形方式比較五台伺服器。</span><span class="sxs-lookup"><span data-stu-id="46c6e-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="46c6e-116">[商務用 Skype Server 中的媒體質量計量散佈報告](media-quality-metrics-distribution-report.md) 會提供圖表，顯示品質品質度量（如抖動或封包遺失）的散佈價值。</span><span class="sxs-lookup"><span data-stu-id="46c6e-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="46c6e-117">[商務用 Skype Server 中的位置趨勢報告](location-trend-report.md) 提供網路位置的呼叫品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="46c6e-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

