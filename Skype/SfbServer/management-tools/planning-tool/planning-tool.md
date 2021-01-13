---
title: 商務用 Skype Server 2015 規劃工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
description: 使用商務用 Skype Server 2015 規劃工具的指導方針。
ms.openlocfilehash: aef46fac65ba1d5651cada81bc79cfc21021bf54
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832383"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="fa690-103">商務用 Skype Server 2015 規劃工具</span><span class="sxs-lookup"><span data-stu-id="fa690-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="fa690-104">使用商務用 Skype Server 2015 規劃工具的指導方針。</span><span class="sxs-lookup"><span data-stu-id="fa690-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="fa690-105">商務用 Skype Server 2015 規劃工具是一個嚮導導向的類似面試工具，它會詢問有關您所設計之商務用 Skype Server 2015 拓撲的問題。</span><span class="sxs-lookup"><span data-stu-id="fa690-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="fa690-106">規劃工具會使用所提供的資訊，結合拓撲設計和容量的慣用慣例，根據提供的答案呈現建議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="fa690-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="fa690-107">您可以從 [商務用 Skype Server 2015 規劃工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)下載規劃工具。</span><span class="sxs-lookup"><span data-stu-id="fa690-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="fa690-108">最後，規劃工具的目標是減輕設計完整商務用 Skype Server 2015 拓撲的潛在複雜性。</span><span class="sxs-lookup"><span data-stu-id="fa690-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="fa690-109">工具也會提供工具內規劃和部署檔的上下文參考，但前提是網際網路連線可以連接至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="fa690-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="fa690-110">在使用基礎結構的 TCP/IP 位址和完整功能變數名稱（ () Fqdn）自訂拓撲之後，規劃工具可提供一系列涵蓋網域名稱系統的報告 (DNS) 命名、防火牆規則、憑證等等。</span><span class="sxs-lookup"><span data-stu-id="fa690-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="fa690-111">使用此工具是規劃實施的第一步。</span><span class="sxs-lookup"><span data-stu-id="fa690-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="fa690-112">下一步是在 [商務用 Skype server 2015 容量計算機](https://www.microsoft.com/download/details.aspx?id=51196)中輸入網站資訊，並視需要調整，然後使用 [商務用 Skype Server 2015 壓力和效能工具](https://www.microsoft.com/download/details.aspx?id=50367) 來模擬及驗證實施是否可滿足您的需求。</span><span class="sxs-lookup"><span data-stu-id="fa690-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="fa690-113">規劃工具也提供以兩種格式匯出資訊的功能：</span><span class="sxs-lookup"><span data-stu-id="fa690-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="fa690-114">Microsoft Excel ( .xml 試算表) </span><span class="sxs-lookup"><span data-stu-id="fa690-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="fa690-115">Microsoft Visio ( vdx) </span><span class="sxs-lookup"><span data-stu-id="fa690-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="fa690-116">下列主題將介紹及詳細說明規劃工具。</span><span class="sxs-lookup"><span data-stu-id="fa690-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="fa690-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="fa690-117">In this section</span></span>

- [<span data-ttu-id="fa690-118">在商務用 Skype Server 2015 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="fa690-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="fa690-119">選用軟體</span><span class="sxs-lookup"><span data-stu-id="fa690-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="fa690-120">在商務用 Skype Server 2015 中流覽規劃工具</span><span class="sxs-lookup"><span data-stu-id="fa690-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="fa690-121">為商務用 Skype Server 2015 建立初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="fa690-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="fa690-122">在商務用 Skype Server 2015 中編輯拓撲</span><span class="sxs-lookup"><span data-stu-id="fa690-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="fa690-123">編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="fa690-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="fa690-124">在商務用 Skype Server 2015 中複查管理員報告</span><span class="sxs-lookup"><span data-stu-id="fa690-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="fa690-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fa690-125">See also</span></span>

[<span data-ttu-id="fa690-126">安裝商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="fa690-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="fa690-127">在商務用 Skype Server 2015 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="fa690-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
