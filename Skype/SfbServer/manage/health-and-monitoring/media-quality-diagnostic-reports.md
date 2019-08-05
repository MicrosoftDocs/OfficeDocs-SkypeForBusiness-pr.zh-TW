---
title: 商務用 Skype Server 中的媒體質量診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
description: '摘要: 瞭解商務用 Skype Server 中的媒體質量診斷報告。'
ms.openlocfilehash: d4ea9c56406799a6a053092e7b8ca16f44505ce7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188797"
---
# <a name="media-quality-diagnostic-reports-in-skype-for-business-server"></a><span data-ttu-id="408ce-103">商務用 Skype Server 中的媒體質量診斷報告</span><span class="sxs-lookup"><span data-stu-id="408ce-103">Media Quality Diagnostic Reports in Skype for Business Server</span></span>
 
<span data-ttu-id="408ce-104">**摘要:** 瞭解商務用 Skype Server 中的媒體質量診斷報告。</span><span class="sxs-lookup"><span data-stu-id="408ce-104">**Summary:** Learn about the Media Quality Diagnostic Reports in Skype for Business Server.</span></span>
  
<span data-ttu-id="408ce-105">媒體質量診斷報告提供通話品質的相關資訊, 以及失敗通話的診斷與疑難排解資訊。</span><span class="sxs-lookup"><span data-stu-id="408ce-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="408ce-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="408ce-106">In this section</span></span>

- <span data-ttu-id="408ce-107">[商務用 Skype Server 中的媒體質量摘要報告](summary.md)提供不同端點類型的整體品質資料, 包括企業語音對等通話、企業語音會議通話, 以及在公用交換電話網絡 (PSTN) 中至少有部分的通話。</span><span class="sxs-lookup"><span data-stu-id="408ce-107">[Media Quality Summary Report in Skype for Business Server](summary.md) Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="408ce-108">[商務用 Skype Server 中的媒體質量比較報告](comparison.md)針對不同類型的音訊通話提供通話品質值的比較 (例如, 透過無線網路撥打, 以及透過有線連線進行通話)。</span><span class="sxs-lookup"><span data-stu-id="408ce-108">[Media Quality Comparison Report in Skype for Business Server](comparison.md) Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>
    
- <span data-ttu-id="408ce-109">[商務用 Skype server 中的伺服器效能報告](server-performance.md)根據此類重要品質度量單位 (例如降級、資料包遺失和抖動) 的度量, 列出已遇到最大問題的伺服器。</span><span class="sxs-lookup"><span data-stu-id="408ce-109">[Server Performance Report in Skype for Business Server](server-performance.md) Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="408ce-110">[商務用 Skype Server 中的位置報告](location-report.md)提供網路位置的清單, 以及每個位置上所發生之通話的媒體質量摘要。</span><span class="sxs-lookup"><span data-stu-id="408ce-110">[Location Report in Skype for Business Server](location-report.md) Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="408ce-111">針對此報告的用途, 位置是以 IP 子網為基礎。</span><span class="sxs-lookup"><span data-stu-id="408ce-111">For purposes of this report, locations are based on IP subnets.</span></span>
    
- <span data-ttu-id="408ce-112">[商務用 Skype Server 中的裝置報告](device-report.md)提供企業語音通話使用的裝置摘要, 包括依裝置通話的平均媒體質量。</span><span class="sxs-lookup"><span data-stu-id="408ce-112">[Device Report in Skype for Business Server](device-report.md) Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>
    
- <span data-ttu-id="408ce-113">[商務用 Skype Server 中的通話清單報告](call-list-report-0.md)提供貴組織內部撥打或接聽電話的相關詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="408ce-113">[Call List Report in Skype for Business Server](call-list-report-0.md) Provides detailed information about phone calls made or received within your organization.</span></span>
    
- <span data-ttu-id="408ce-114">[商務用 Skype Server 中的通話詳細資料包告](call-detail-report.md)提供在貴組織內撥打或接聽電話的相關詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="408ce-114">[Call Detail Report in Skype for Business Server](call-detail-report.md) Provides detailed information about phone calls made from or received within your organization.</span></span>
    
- <span data-ttu-id="408ce-115">[商務用 Skype server 中的伺服器媒體質量趨勢報告](server-media-quality-trend-report.md)提供一種方式, 讓您以圖形方式比較多達五台伺服器 (例如通話量、通話百分比差、資料包遺失和抖動等) 品質統計資料。</span><span class="sxs-lookup"><span data-stu-id="408ce-115">[Server Media Quality Trend Report in Skype for Business Server](server-media-quality-trend-report.md) Provides a way for you to graphically compare up to five servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>
    
- <span data-ttu-id="408ce-116">[商務用 Skype Server 中的媒體質量度量分佈報告](media-quality-metrics-distribution-report.md)提供圖形, 顯示經驗統計資料 (例如抖動或資料包遺失) 的分配值。</span><span class="sxs-lookup"><span data-stu-id="408ce-116">[The Media Quality Metrics Distribution Report in Skype for Business Server](media-quality-metrics-distribution-report.md) Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>
    
- <span data-ttu-id="408ce-117">[商務用 Skype Server 中的位置趨勢報告](location-trend-report.md)提供網路位置的通話品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="408ce-117">[Location Trend Report in Skype for Business Server](location-trend-report.md) Provides call quality trend information for network locations.</span></span>
    

