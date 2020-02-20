---
title: Skype for Business Server 2019 管理工具
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要： 了解服務管理工具，在 [Skype for Business Server 2019。
ms.openlocfilehash: 2369e6530525d7bfc56c23fab1db2869de688cc0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146276"
---
# <a name="skype-for-business-server-2019-management-tools"></a><span data-ttu-id="de9da-103">Skype for Business Server 2019 管理工具</span><span class="sxs-lookup"><span data-stu-id="de9da-103">Skype for Business Server 2019 Management Tools</span></span>
 
<span data-ttu-id="de9da-104">**摘要：** 了解服務管理工具，在 [Skype 商務 Server 2019。</span><span class="sxs-lookup"><span data-stu-id="de9da-104">**Summary:** Learn about the service management tools in Skype for Business Server 2019.</span></span>
  
<span data-ttu-id="de9da-105">Skype 商務 Server 2019 提供立即訊息 (IM)、 目前狀態、 會議及電話語音解決方案，支援企業層級的共同作業需求。</span><span class="sxs-lookup"><span data-stu-id="de9da-105">Skype for Business Server 2019 offers instant messaging (IM), presence, conferencing, and telephony solutions that support enterprise-level collaboration requirements.</span></span> <span data-ttu-id="de9da-106">工具來管理這些服務非常有彈性，強大。</span><span class="sxs-lookup"><span data-stu-id="de9da-106">The tools to manage these services are both flexible and powerful.</span></span>
  
## <a name="skype-for-business-server-2019-tools"></a><span data-ttu-id="de9da-107">Skype for Business Server 2019 工具</span><span class="sxs-lookup"><span data-stu-id="de9da-107">Skype for Business Server 2019 Tools</span></span>

||<span data-ttu-id="de9da-108">**內容**</span><span class="sxs-lookup"><span data-stu-id="de9da-108">**Content**</span></span>|<span data-ttu-id="de9da-109">**描述**</span><span class="sxs-lookup"><span data-stu-id="de9da-109">**Description**</span></span>|
|:-----|:-----|:-----|
|![儀表板] 圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="de9da-111">通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="de9da-111">Call Quality Dashboard</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534842) <br/> |<span data-ttu-id="de9da-112">通話品質儀表板 (CQD) 是用於快速地建立入口網站及組織報告以從您的 Skype 商務環境的經驗品質 (QoE) 資料為基礎。</span><span class="sxs-lookup"><span data-stu-id="de9da-112">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data from your Skype for Business environment.</span></span> <span data-ttu-id="de9da-113">CQD 部署 SSAS cube 彙總 QoEMetrics 資料庫，可讓使用者建立及修改報告中的資料，並查看即時更新。</span><span class="sxs-lookup"><span data-stu-id="de9da-113">The CQD deploys a SSAS cube to aggregate the data in the QoEMetrics database, which enables users to create and modify reports and see them update in real-time.</span></span> <span data-ttu-id="de9da-114">此外，CQD 會公開 web Api，讓使用者能夠以程式設計方式存取使用自訂的儀表板中的 cube 資料。</span><span class="sxs-lookup"><span data-stu-id="de9da-114">Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>  <br/> |
|![KHI 圖示](../SfbServer/media/8759b767-b689-4a95-94a5-5b27c5688688.png)|[<span data-ttu-id="de9da-116">KHI 資源</span><span class="sxs-lookup"><span data-stu-id="de9da-116">KHI Resources</span></span>](https://www.microsoft.com/download/details.aspx?id=57519) <br/> |<span data-ttu-id="de9da-117">索引鍵健康情況指標 (KHI) 是效能計數器與目標在於透露的問題，可能會影響使用者經驗的建議臨界值。</span><span class="sxs-lookup"><span data-stu-id="de9da-117">Key Health Indicators (KHI) are Performance Counters with recommended thresholds aimed at revealing problems that can impact the user experience.</span></span> <span data-ttu-id="de9da-118">KHI 快顯功能表概述的操作的程序與修復步驟，才能維護狀況良好的部署，並包含範例 PowerShell 指令碼用來設定 KHI 資料收集器分析和定義活頁簿可以分析 KHI 效能資料。</span><span class="sxs-lookup"><span data-stu-id="de9da-118">The KHI Guide outlines the operational process and remediation steps to maintain a healthy deployment, and includes a sample PowerShell script used to configure KHI Data Collectors and an Analysis and Definitions Workbook which can analyze KHI performance data.</span></span>  <br/> |
|![儀表板] 圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="de9da-120">Skype 商務 Server 2015 的統計資料管理員</span><span class="sxs-lookup"><span data-stu-id="de9da-120">Statistics Manager for Skype for Business Server 2015</span></span>](../SfbServer/management-tools/statistics-manager/statistics-manager.md) <br/> |<span data-ttu-id="de9da-121">StatsMan 是針對彙總整個基礎結構的即時為圖形的效能計數器中檢視 KHI 計算的儀表板解決方案。</span><span class="sxs-lookup"><span data-stu-id="de9da-121">StatsMan is a dashboard solution for viewing KHI calculations in real-time as well as graphed performance counters aggregated across your infrastructure.</span></span> <span data-ttu-id="de9da-122">儀表板可以用來找出進行中的效能問題，檢視您的環境的計劃變更的結果，追蹤解析度的中斷，以及執行更多功能。</span><span class="sxs-lookup"><span data-stu-id="de9da-122">The dashboard can be used to pinpoint ongoing performance issues, view the results of a planned change to your environment, track resolution of outages, and much more.</span></span> <span data-ttu-id="de9da-123">現成可用，它以從 KHI 資源，KHI 閾值設定，可以進行自訂以符合您的部署獨特的需求。</span><span class="sxs-lookup"><span data-stu-id="de9da-123">Out of the box, it is configured with KHI thresholds from the KHI Resources, and can be customized to suit your deployment's unique needs.</span></span>  <br/> |
|![SCOM 圖示](../SfbServer/media/3a7601cb-dd2f-4606-8a3b-07c7abdc091a.png)|[<span data-ttu-id="de9da-125">管理 Skype for Business Server 2019 使用 SCOM 管理組件</span><span class="sxs-lookup"><span data-stu-id="de9da-125">Manage Skype for Business Server 2019 using SCOM Management pack</span></span>](tools/scom-management-pack-use-2019.md) <br/> |<span data-ttu-id="de9da-126">藉由使用 Skype for Business Server 2019 管理組件，您可以找出並主動解決潛在的問題。</span><span class="sxs-lookup"><span data-stu-id="de9da-126">By using Skype for Business Server 2019 Management Packs, you can identify and address potential issues proactively.</span></span> <span data-ttu-id="de9da-127">如此一來，Skype for Business Server 2019 管理組件會擴充功能的 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="de9da-127">In this way, the Skype for Business Server 2019 Management Packs extend the capabilities of System Center Operations Manager.</span></span>  <br/> |
|![儀表板] 圖示](../SfbServer/media/144fef0b-3ff0-4298-8b03-978bda9e923b.png)|[<span data-ttu-id="de9da-129">Skype for Business 伺服器容量規劃小算盤</span><span class="sxs-lookup"><span data-stu-id="de9da-129">Skype for Business Server Capacity Planning Calculator</span></span>](../SfbServer/management-tools/capacity-planning-calculator.md) <br/> |<span data-ttu-id="de9da-130">Skype for Business Server 2015/2019年容量規劃計算器可協助您建立您的組織需求的拓撲的模型。</span><span class="sxs-lookup"><span data-stu-id="de9da-130">The Skype for Business Server 2015/2019 Capacity Planning Calculator helps you model a topology for your organization's needs.</span></span>  <br/> |
||
