---
title: 使用者經驗品質 |Microsoft 團隊 |QoS |通話品質
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 監視 Microsoft 團隊品質與使用方式所需的工作與活動
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 69f36da55daf95da66fa87b90487dde447953f53
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837173"
---
<span data-ttu-id="38b60-103">![圖表醒目提示升級歷程的卓越運作階段](media/upgrade-banner-op-excellence.png "升級歷程階段，重點放在卓越運作階段")</span><span class="sxs-lookup"><span data-stu-id="38b60-103">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="38b60-104">本文是您升級歷程的卓越運作階段的一部分，在您完成從商務用 Skype 升級至團隊之後，就會立即開始。</span><span class="sxs-lookup"><span data-stu-id="38b60-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="38b60-105">體驗品質的審查指南</span><span class="sxs-lookup"><span data-stu-id="38b60-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="38b60-106">[[體驗品質檢查指南](https://aka.ms/qerguide)] 包含一組活動，可針對改善使用者體驗的重要區域評估並提供修正指導方針，如下所示。</span><span class="sxs-lookup"><span data-stu-id="38b60-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="38b60-107">![在審閱期間要檢查的主要區域圖例。](media/plan-my-service-management-image2.png "體驗品質檢查期間要檢查的主要區域：音訊、可靠性及使用者問卷結果。")</span><span class="sxs-lookup"><span data-stu-id="38b60-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="38b60-108">透過不斷評估並修正指南中所述的區域，您可以減少對使用者經驗造成負面影響的可能性。</span><span class="sxs-lookup"><span data-stu-id="38b60-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="38b60-109">在部署中遇到的大多數使用者體驗問題，都可以分為下列類別：</span><span class="sxs-lookup"><span data-stu-id="38b60-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="38b60-110">防火牆或 proxy 配置不完整</span><span class="sxs-lookup"><span data-stu-id="38b60-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="38b60-111">低 wi-fi 覆蓋範圍</span><span class="sxs-lookup"><span data-stu-id="38b60-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="38b60-112">頻寬不足</span><span class="sxs-lookup"><span data-stu-id="38b60-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="38b60-113">點對點</span><span class="sxs-lookup"><span data-stu-id="38b60-113">VPN</span></span>

- <span data-ttu-id="38b60-114">使用未優化或內建的音訊裝置</span><span class="sxs-lookup"><span data-stu-id="38b60-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="38b60-115">有問題的子網或網路裝置</span><span class="sxs-lookup"><span data-stu-id="38b60-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="38b60-116">體驗品質檢查指南中提供的指導方針主要是使用通話品質儀表板（CQD）作為主要工具來報告和調查所述的每一個區域，並將焦點放在音訊上以最大化採納與影響。</span><span class="sxs-lookup"><span data-stu-id="38b60-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="38b60-117">針對網路所做的任何優化，以改善音訊體驗，也會直接翻譯成影片和桌面共用的改良功能。</span><span class="sxs-lookup"><span data-stu-id="38b60-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="38b60-118">我們強烈建議您提前提名品質擁護者。</span><span class="sxs-lookup"><span data-stu-id="38b60-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="38b60-119">命名之後，他們應該開始熟悉[體驗品質檢查指南](https://aka.ms/qerguide)中的內容。</span><span class="sxs-lookup"><span data-stu-id="38b60-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
