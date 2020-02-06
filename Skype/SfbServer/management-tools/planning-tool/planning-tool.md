---
title: 使用規劃工具設計 Lync Server 2013 的拓撲
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
description: 使用商務用 Skype Server 2015 規劃工具的指導方針。
ms.openlocfilehash: a1125224405cf739e4afab045dab8360a18756d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816302"
---
# <a name="skype-for-business-server-2015-planning-tool"></a><span data-ttu-id="93331-103">使用規劃工具設計 Lync Server 2013 的拓撲</span><span class="sxs-lookup"><span data-stu-id="93331-103">Skype for Business Server 2015 Planning Tool</span></span>
 
<span data-ttu-id="93331-104">使用商務用 Skype Server 2015 規劃工具的指導方針。</span><span class="sxs-lookup"><span data-stu-id="93331-104">Guidance on using the Skype for Business Server 2015 Planning Tool.</span></span>
  
<span data-ttu-id="93331-105">商務用 Skype Server 2015 規劃工具是一個由嚮導驅動的工具，該工具會詢問您所設計的商務用 Skype Server 2015 拓朴的相關問題。</span><span class="sxs-lookup"><span data-stu-id="93331-105">The Skype for Business Server 2015 Planning Tool is a wizard driven, interview-like tool that asks questions about the Skype for Business Server 2015 topology that you are designing.</span></span> <span data-ttu-id="93331-106">規劃工具會使用所提供的資訊，結合拓撲設計和容量的最佳做法，以根據提供的答案呈現建議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="93331-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="93331-107">您可以從[商務用 Skype Server 2015 規劃工具](https://go.microsoft.com/fwlink/p/?LinkID=282725)下載規劃工具。</span><span class="sxs-lookup"><span data-stu-id="93331-107">You can download the Planning Tool from the [Skype for Business Server 2015 Planning Tool](https://go.microsoft.com/fwlink/p/?LinkID=282725).</span></span>
  
<span data-ttu-id="93331-108">最後，規劃工具的目標是減輕設計完整的商務用 Skype Server 2015 拓朴的潛在複雜性。</span><span class="sxs-lookup"><span data-stu-id="93331-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="93331-109">此工具也會在工具內提供規劃與部署檔的相關參照，只要網際網路連線可連線至 Microsoft 網站。</span><span class="sxs-lookup"><span data-stu-id="93331-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft  website.</span></span>
  
<span data-ttu-id="93331-110">使用基礎結構的 TCP/IP 位址及完整功能變數名稱（Fqdn）自訂拓撲之後，規劃工具會提供一系列的報表，涵蓋網功能變數名稱稱系統（DNS）命名、防火牆規則、憑證等等。</span><span class="sxs-lookup"><span data-stu-id="93331-110">After customizing the topology with the infrastructure's TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span> 
  
<span data-ttu-id="93331-111">使用這個工具是規劃實施的第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="93331-111">Using this tool is the first step in planning your implementation.</span></span> <span data-ttu-id="93331-112">下一個步驟是將您的網站資訊輸入到商務用[Skype server 2015 容量計算機](https://www.microsoft.com/en-us/download/details.aspx?id=51196)，視需要調整，然後使用[商務用 Skype Server 2015 的壓力與效能工具](https://www.microsoft.com/en-us/download/details.aspx?id=50367)來模擬並驗證實現是否能滿足您的需求。</span><span class="sxs-lookup"><span data-stu-id="93331-112">The next step would be to input your site information specifics into the [Skype for Business Server 2015 Capacity Calculator](https://www.microsoft.com/en-us/download/details.aspx?id=51196), adjust as needed, then use the [Skype for Business Server 2015 Stress and Performance Tool](https://www.microsoft.com/en-us/download/details.aspx?id=50367) to simulate and verify the implementation will serve your needs.</span></span>
  
<span data-ttu-id="93331-113">規劃工具也提供將資訊匯出為兩種格式的功能：</span><span class="sxs-lookup"><span data-stu-id="93331-113">The Planning Tool also provides the ability to export information in two formats:</span></span>
  
- <span data-ttu-id="93331-114">Microsoft Excel （.xml 試算表）</span><span class="sxs-lookup"><span data-stu-id="93331-114">Microsoft Excel (.xml spreadsheet)</span></span>
    
- <span data-ttu-id="93331-115">Microsoft Visio （vdx）</span><span class="sxs-lookup"><span data-stu-id="93331-115">Microsoft Visio (.vdx)</span></span>
    
<span data-ttu-id="93331-116">下列主題將介紹及詳細說明規劃工具。</span><span class="sxs-lookup"><span data-stu-id="93331-116">The following topics introduce and detail the Planning Tool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="93331-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="93331-117">In this section</span></span>

- [<span data-ttu-id="93331-118">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="93331-118">Install the Planning Tool in Skype for Business Server 2015</span></span>](install.md)
    
- [<span data-ttu-id="93331-119">選用軟體</span><span class="sxs-lookup"><span data-stu-id="93331-119">Optional Software</span></span>](install.md#Optional_Software)
    
- [<span data-ttu-id="93331-120">在 Lync Server 2013 中瀏覽規劃工具</span><span class="sxs-lookup"><span data-stu-id="93331-120">Navigate the Planning Tool in Skype for Business Server 2015</span></span>](navigate.md)
    
- [<span data-ttu-id="93331-121">針對 Lync Server 2013  建立初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="93331-121">Create the initial topology design for Skype for Business Server 2015</span></span>](create-the-initial-design.md)
    
- [<span data-ttu-id="93331-122">在商務用 Skype Server 2015 中編輯拓撲</span><span class="sxs-lookup"><span data-stu-id="93331-122">Edit the topology in Skype for Business Server 2015</span></span>](edit-the-topology.md)
    
- [<span data-ttu-id="93331-123">編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="93331-123">Edit the network configuration diagram</span></span>](edit-the-topology.md#Edit_Network_diagram)
    
- [<span data-ttu-id="93331-124">在商務用 Skype Server 2015 中查看系統管理員報告</span><span class="sxs-lookup"><span data-stu-id="93331-124">Review the Administrator Reports in Skype for Business Server 2015</span></span>](review-the-administrator-reports.md)
    
## <a name="see-also"></a><span data-ttu-id="93331-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="93331-125">See also</span></span>

[<span data-ttu-id="93331-126">安裝商務用 Skype Server 2015</span><span class="sxs-lookup"><span data-stu-id="93331-126">Install Skype for Business Server 2015</span></span>](../../deploy/install/install.md)
  
[<span data-ttu-id="93331-127">在商務用 Skype Server 2015 中規劃立即訊息和目前狀態</span><span class="sxs-lookup"><span data-stu-id="93331-127">Plan for instant messaging and presence in Skype for Business Server 2015</span></span>](../../plan-your-deployment/instant-messaging-and-presence.md)
