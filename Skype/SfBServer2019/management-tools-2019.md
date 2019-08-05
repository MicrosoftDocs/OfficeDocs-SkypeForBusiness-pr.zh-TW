---
title: 商務用 Skype Server 2019 管理工具
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: '摘要: 瞭解商務用 Skype Server 2019 中的服務管理工具。'
ms.openlocfilehash: c666d76a232d64bb81892be96e64da1d544fe9cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193814"
---
# <a name="skype-for-business-server-2019-management-tools"></a><span data-ttu-id="07bdb-103">商務用 Skype Server 2019 管理工具</span><span class="sxs-lookup"><span data-stu-id="07bdb-103">Skype for Business Server 2019 Management Tools</span></span>
 
<span data-ttu-id="07bdb-104">**摘要:** 瞭解商務用 Skype Server 2019 中的服務管理工具。</span><span class="sxs-lookup"><span data-stu-id="07bdb-104">**Summary:** Learn about the service management tools in Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="07bdb-105">商務用 Skype Server 2019 提供可支援企業級共同作業需求的立即訊息 (IM)、目前狀態、會議和電話方案。</span><span class="sxs-lookup"><span data-stu-id="07bdb-105">Skype for Business Server 2019 offers instant messaging (IM), presence, conferencing, and telephony solutions that support enterprise-level collaboration requirements.</span></span> <span data-ttu-id="07bdb-106">管理這些服務的工具既靈活又強大。</span><span class="sxs-lookup"><span data-stu-id="07bdb-106">The tools to manage these services are both flexible and powerful.</span></span>
  
## <a name="skype-for-business-server-2019-tools"></a><span data-ttu-id="07bdb-107">商務用 Skype Server 2019 工具</span><span class="sxs-lookup"><span data-stu-id="07bdb-107">Skype for Business Server 2019 Tools</span></span>

||<span data-ttu-id="07bdb-108">**內容**</span><span class="sxs-lookup"><span data-stu-id="07bdb-108">**Content**</span></span>|<span data-ttu-id="07bdb-109">**說明**</span><span class="sxs-lookup"><span data-stu-id="07bdb-109">**Description**</span></span>|
|:-----|:-----|:-----|
|![儀表板圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="07bdb-111">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="07bdb-111">Call Quality Dashboard</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |<span data-ttu-id="07bdb-112">通話品質儀表板 (CQD) 是一種網頁入口網站, 可根據商務用 Skype 環境中的經驗品質 (QoE) 資料, 快速建立及組織報表。</span><span class="sxs-lookup"><span data-stu-id="07bdb-112">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data from your Skype for Business environment.</span></span> <span data-ttu-id="07bdb-113">CQD 會部署一個 SSAS 立方體來匯總 QoEMetrics 資料庫中的資料, 讓使用者可以建立及修改報告, 並即時查看更新。</span><span class="sxs-lookup"><span data-stu-id="07bdb-113">The CQD deploys a SSAS cube to aggregate the data in the QoEMetrics database, which enables users to create and modify reports and see them update in real-time.</span></span> <span data-ttu-id="07bdb-114">此外, CQD 會公開 web Api, 讓使用者以程式設計方式存取要在自訂儀表板中使用的多維資料集資料。</span><span class="sxs-lookup"><span data-stu-id="07bdb-114">Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>  <br/> |
|![KHI 圖示](../SfbServer/media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[<span data-ttu-id="07bdb-116">KHI 資源</span><span class="sxs-lookup"><span data-stu-id="07bdb-116">KHI Resources</span></span>](https://www.microsoft.com/download/details.aspx?id=57519) <br/> |<span data-ttu-id="07bdb-117">主要的健康情況指標 (KHI) 是效能計數器, 其中包含可影響使用者體驗之問題的建議閾值。</span><span class="sxs-lookup"><span data-stu-id="07bdb-117">Key Health Indicators (KHI) are Performance Counters with recommended thresholds aimed at revealing problems that can impact the user experience.</span></span> <span data-ttu-id="07bdb-118">KHI 指南概述了維護正常部署所需執行的操作程式與修正步驟, 並包含用來設定 KHI 資料收集程式的範例 PowerShell 腳本, 以及可分析 KHI 效能資料的分析與定義活頁簿。</span><span class="sxs-lookup"><span data-stu-id="07bdb-118">The KHI Guide outlines the operational process and remediation steps to maintain a healthy deployment, and includes a sample PowerShell script used to configure KHI Data Collectors and an Analysis and Definitions Workbook which can analyze KHI performance data.</span></span>  <br/> |
|![儀表板圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="07bdb-120">商務用 Skype Server 2015 的統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="07bdb-120">Statistics Manager for Skype for Business Server 2015</span></span>](../SfbServer/management-tools/statistics-manager/statistics-manager.md) <br/> |<span data-ttu-id="07bdb-121">StatsMan 是一種儀表板解決方案, 可即時地在整個基礎結構中同時查看 KHI 計算及圖形效能計數器。</span><span class="sxs-lookup"><span data-stu-id="07bdb-121">StatsMan is a dashboard solution for viewing KHI calculations in real-time as well as graphed performance counters aggregated across your infrastructure.</span></span> <span data-ttu-id="07bdb-122">儀表板可以用來找出持續的效能問題、查看規劃的變更對您的環境的結果、追蹤中斷的解決方式等等。</span><span class="sxs-lookup"><span data-stu-id="07bdb-122">The dashboard can be used to pinpoint ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="07bdb-123">從盒中開始, 它是從 KHI 資源設定 KHI 閾值, 而且可以根據您的部署的獨特需求加以自訂。</span><span class="sxs-lookup"><span data-stu-id="07bdb-123">Out of the box, it is configured with KHI thresholds from the KHI Resources, and can be customized to suit your deployment's unique needs.</span></span>  <br/> |
|![SCOM 圖示](../SfbServer/media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[<span data-ttu-id="07bdb-125">使用 SCOM 管理套件管理商務用 Skype Server 2019</span><span class="sxs-lookup"><span data-stu-id="07bdb-125">Manage Skype for Business Server 2019 using SCOM Management pack</span></span>](tools/scom-management-pack-use-2019.md) <br/> |<span data-ttu-id="07bdb-126">透過使用商務用 Skype Server 2019 管理套件, 您可以預先找出並解決可能的問題。</span><span class="sxs-lookup"><span data-stu-id="07bdb-126">By using Skype for Business Server 2019 Management Packs, you can identify and address potential issues proactively.</span></span> <span data-ttu-id="07bdb-127">如此一來, 商務用 Skype Server 2019 管理套件延伸了 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="07bdb-127">In this way, the Skype for Business Server 2019 Management Packs extend the capabilities of System Center Operations Manager.</span></span>  <br/> |
|![儀表板圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="07bdb-129">商務用 Skype Server 容量規劃計算機</span><span class="sxs-lookup"><span data-stu-id="07bdb-129">Skype for Business Server Capacity Planning Calculator</span></span>](../SfbServer/management-tools/capacity-planning-calculator.md) <br/> |<span data-ttu-id="07bdb-130">商務用 Skype Server 2015/2019 容量規劃計算機可協助您為組織的需求建立拓撲模型。</span><span class="sxs-lookup"><span data-stu-id="07bdb-130">The Skype for Business Server 2015/2019 Capacity Planning Calculator helps you model a topology for your organization's needs.</span></span>  <br/> |
||
