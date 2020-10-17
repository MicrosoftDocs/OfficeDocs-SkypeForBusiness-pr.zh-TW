---
title: Lync Server 2013：使用規劃工具設計拓撲
description: Lync Server 2013：使用規劃工具設計拓撲。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcc10d09d7b8b815e2b4924d06c10de23c14236b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542589"
---
# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="dd11f-103">使用規劃工具設計 Lync Server 2013 的拓撲</span><span class="sxs-lookup"><span data-stu-id="dd11f-103">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd11f-104">_**主題上次修改日期：** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="dd11f-104">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="dd11f-105">Microsoft Lync Server 2013，規劃工具是一個嚮導導向的工具，它會詢問有關您所設計之 Lync Server 2013 拓撲的問題。</span><span class="sxs-lookup"><span data-stu-id="dd11f-105">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="dd11f-106">規劃工具會使用所提供的資訊，結合拓撲設計和容量的慣用慣例，根據提供的答案呈現建議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dd11f-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="dd11f-107">您可以從 Microsoft 下載中心 () 下載規劃工具 [https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725) 。</span><span class="sxs-lookup"><span data-stu-id="dd11f-107">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="dd11f-108">最後，規劃工具的目標是減輕設計完整 Lync Server 2013 拓撲的潛在複雜性。</span><span class="sxs-lookup"><span data-stu-id="dd11f-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="dd11f-109">此工具也會提供其規劃與部署文件的關聯式參考，只要有網際網路連線可連接至 Microsoft TechNet 網站即可。</span><span class="sxs-lookup"><span data-stu-id="dd11f-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="dd11f-110">在使用基礎結構的 TCP/IP 位址和完整功能變數名稱（ () Fqdn）自訂拓撲之後，規劃工具可提供一系列涵蓋網域名稱系統的報告 (DNS) 命名、防火牆規則、憑證等等。</span><span class="sxs-lookup"><span data-stu-id="dd11f-110">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="dd11f-111">規劃工具也提供以兩種格式匯出資訊的功能：</span><span class="sxs-lookup"><span data-stu-id="dd11f-111">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="dd11f-112">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="dd11f-112">Microsoft Excel</span></span>

  - <span data-ttu-id="dd11f-113">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="dd11f-113">Microsoft Visio</span></span>

<span data-ttu-id="dd11f-114">下列主題將介紹及詳細說明規劃工具。</span><span class="sxs-lookup"><span data-stu-id="dd11f-114">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd11f-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="dd11f-115">In This Section</span></span>

  - [<span data-ttu-id="dd11f-116">在 Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="dd11f-116">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="dd11f-117">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="dd11f-117">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="dd11f-118">流覽 Lync Server 2013 中的規劃工具</span><span class="sxs-lookup"><span data-stu-id="dd11f-118">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="dd11f-119">建立 Lync Server 2013 的初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="dd11f-119">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="dd11f-120">在 Lync Server 2013 中審閱管理員報告</span><span class="sxs-lookup"><span data-stu-id="dd11f-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd11f-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dd11f-121">See Also</span></span>


[<span data-ttu-id="dd11f-122">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd11f-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="dd11f-123">在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態</span><span class="sxs-lookup"><span data-stu-id="dd11f-123">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

