---
title: Skype for Business Server 2015 規劃工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 使用 Skype for Business Server 2015 規劃工具的指南。
ms.openlocfilehash: 8eec7865b74640cf6dfe4f5a5122f4c7091cc5ae
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050095"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="909a4-103">Skype for Business Server 2015 規劃工具</span><span class="sxs-lookup"><span data-stu-id="909a4-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="909a4-104">使用 Skype for Business Server 2015 規劃工具的指南。</span><span class="sxs-lookup"><span data-stu-id="909a4-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="909a4-105">Skype for Business Server 2015 規劃工具是驅動，精靈會詢問有關問題用 Skype Server 2015 拓撲您所設計的採訪類似的工具。</span><span class="sxs-lookup"><span data-stu-id="909a4-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="909a4-106">提供資訊，請規劃工具使用搭配慣用的拓撲設計和容量，以呈現提供的答案為基礎的建議的拓撲的作法。</span><span class="sxs-lookup"><span data-stu-id="909a4-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="909a4-107">您可以從[Skype for Business Server 2015 規劃工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)下載規劃工具。</span><span class="sxs-lookup"><span data-stu-id="909a4-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="909a4-108">最後，規劃工具的目標是為了簡化潛在的設計完成用 Skype Server 2015 拓撲複雜性。</span><span class="sxs-lookup"><span data-stu-id="909a4-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="909a4-109">假設沒有可用連線到 Microsoft 網站的網際網路連線工具也可讓內工具]，規劃及部署 > 文件的內容相關式參考。</span><span class="sxs-lookup"><span data-stu-id="909a4-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="909a4-110">自訂之後的拓撲的基礎結構的 TCP/IP 位址與完整的網域名稱 (Fqdn)，規劃工具會提供一系列的涵蓋網域名稱系統 (DNS) 命名、 防火牆規則、 憑證、 等等的報告。</span><span class="sxs-lookup"><span data-stu-id="909a4-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="909a4-111">使用此工具是第一個步驟中規劃實作。</span><span class="sxs-lookup"><span data-stu-id="909a4-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="909a4-112">下一步就是到[Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196)輸入您網站的資訊細節，請視需要調整，然後使用[Skype for Business Server 2015 壓力及效能工具](https://www.microsoft.com/download/details.aspx?id=50367)來模擬，並確認實作會提供您的需求。</span><span class="sxs-lookup"><span data-stu-id="909a4-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="909a4-113">規劃工具也提供匯出資訊兩種格式的能力：</span><span class="sxs-lookup"><span data-stu-id="909a4-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="909a4-114">Microsoft Excel （.xml 試算表）</span><span class="sxs-lookup"><span data-stu-id="909a4-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="909a4-115">Microsoft Visio (.vdx)</span><span class="sxs-lookup"><span data-stu-id="909a4-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="909a4-116">下列主題介紹，詳細規劃工具。</span><span class="sxs-lookup"><span data-stu-id="909a4-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="909a4-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="909a4-117">In this section</span></span>

- [<span data-ttu-id="909a4-118">安裝規劃工具在 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="909a4-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="909a4-119">選用軟體</span><span class="sxs-lookup"><span data-stu-id="909a4-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="909a4-120">瀏覽商務 Server 2015 Skype 的規劃工具</span><span class="sxs-lookup"><span data-stu-id="909a4-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="909a4-121">建立初始拓撲設計用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="909a4-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="909a4-122">編輯商務 Server 2015 Skype 中的拓撲</span><span class="sxs-lookup"><span data-stu-id="909a4-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="909a4-123">編輯網路組態圖</span><span class="sxs-lookup"><span data-stu-id="909a4-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="909a4-124">檢閱管理員報告 skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="909a4-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="909a4-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="909a4-125">See also</span></span>

[<span data-ttu-id="909a4-126">安裝 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="909a4-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="909a4-127">規劃的立即訊息和目前狀態用 skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="909a4-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
