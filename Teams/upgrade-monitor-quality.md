---
title: 使用者體驗品質|Microsoft Teams |QoS |通話品質
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 系統管理員可以瞭解監控系統品質及使用方式所需的工作Microsoft Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808993"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="76e65-103">體驗品質的審查指南</span><span class="sxs-lookup"><span data-stu-id="76e65-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="76e65-104">![強調升級歷程中卓越營運階段的圖表](media/upgrade-banner-op-excellence.png "升級旅程的階段，強調營運優化階段")</span><span class="sxs-lookup"><span data-stu-id="76e65-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="76e65-105">本文是升級過程中營運優化階段的一部分，一旦完成從 商務用 Skype 升級至 Teams。</span><span class="sxs-lookup"><span data-stu-id="76e65-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="76e65-106">改善及監控通話品質</span><span class="sxs-lookup"><span data-stu-id="76e65-106">Improve and monitor call quality</span></span>

<span data-ttu-id="76e65-107">[改善及](monitor-call-quality-qos.md)監控Teams包括一組活動，評估及提供對改善使用者體驗影響最大之關鍵地區的補救指引，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="76e65-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="76e65-108">![在審查期間要檢查的重要區域圖例。](media/plan-my-service-management-image2.png "在體驗品質檢閱期間要檢查的重要區域：音訊、可靠性及使用者問卷結果。")</span><span class="sxs-lookup"><span data-stu-id="76e65-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="76e65-109">您可以持續評估及補救指南所述區域，以降低其潛在性，對使用者體驗造成負面影響。</span><span class="sxs-lookup"><span data-stu-id="76e65-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="76e65-110">部署中遇到的大多數使用者體驗問題可以分成下列類別：</span><span class="sxs-lookup"><span data-stu-id="76e65-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="76e65-111">不完整的防火牆或 Proxy 組</span><span class="sxs-lookup"><span data-stu-id="76e65-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="76e65-112">低Wi-Fi覆蓋</span><span class="sxs-lookup"><span data-stu-id="76e65-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="76e65-113">頻寬不足</span><span class="sxs-lookup"><span data-stu-id="76e65-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="76e65-114">Vpn</span><span class="sxs-lookup"><span data-stu-id="76e65-114">VPN</span></span>

- <span data-ttu-id="76e65-115">使用非初始化或內建的音訊裝置</span><span class="sxs-lookup"><span data-stu-id="76e65-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="76e65-116">有問題的子網或網路裝置</span><span class="sxs-lookup"><span data-stu-id="76e65-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="76e65-117">改善及監控[Teams](monitor-call-quality-qos.md)通話品質中提供的指導，著重于使用通話品質儀表板 (CQD) Online 做為報告及調查所述每個區域的主要工具，並著重于音訊，以最大化採用和影響。</span><span class="sxs-lookup"><span data-stu-id="76e65-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="76e65-118">對網路進行的任何優化以改善音訊體驗，也會直接轉換成改善視像和桌面共用。</span><span class="sxs-lookup"><span data-stu-id="76e65-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="76e65-119">我們強烈建議您及早提名品質優等獎得主。</span><span class="sxs-lookup"><span data-stu-id="76e65-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="76e65-120">被提名後，他們應開始熟悉改善及監控通話品質中的內容[，Teams。](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="76e65-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
