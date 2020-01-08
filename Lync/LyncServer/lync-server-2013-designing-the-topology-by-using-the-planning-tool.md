---
title: Lync Server 2013：使用規劃工具設計拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09cfa16103f4e6e2ebfa2327edbd330311753609
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="444ce-102">使用規劃工具設計 Lync Server 2013 的拓撲</span><span class="sxs-lookup"><span data-stu-id="444ce-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="444ce-103">_**主題上次修改日期：** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="444ce-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="444ce-104">Microsoft Lync Server 2013，[規劃工具] 是一個由嚮導驅動的工具，會詢問您所設計的 Lync Server 2013 拓朴問題。</span><span class="sxs-lookup"><span data-stu-id="444ce-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="444ce-105">規劃工具會使用所提供的資訊，結合拓撲設計和容量的最佳做法，以根據提供的答案呈現建議的拓撲。</span><span class="sxs-lookup"><span data-stu-id="444ce-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="444ce-106">您可以從 Microsoft 下載中心下載 [規劃] 工具（[http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)）。</span><span class="sxs-lookup"><span data-stu-id="444ce-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="444ce-107">最後，規劃工具的目標是減輕設計完整 Lync Server 2013 拓撲的潛在複雜性。</span><span class="sxs-lookup"><span data-stu-id="444ce-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="444ce-108">此工具也會在工具內提供規劃和部署檔的相關參照，只要網際網路連線可連線至 Microsoft TechNet 網站。</span><span class="sxs-lookup"><span data-stu-id="444ce-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="444ce-109">使用基礎結構的 TCP/IP 位址及完整功能變數名稱（Fqdn）自訂拓撲之後，規劃工具會提供一系列的報表，涵蓋網功能變數名稱稱系統（DNS）命名、防火牆規則、憑證等等。</span><span class="sxs-lookup"><span data-stu-id="444ce-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="444ce-110">規劃工具也提供將資訊匯出為兩種格式的功能：</span><span class="sxs-lookup"><span data-stu-id="444ce-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="444ce-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="444ce-111">Microsoft Excel</span></span>

  - <span data-ttu-id="444ce-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="444ce-112">Microsoft Visio</span></span>

<span data-ttu-id="444ce-113">下列主題將介紹及詳細說明規劃工具。</span><span class="sxs-lookup"><span data-stu-id="444ce-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="444ce-114">本節內容</span><span class="sxs-lookup"><span data-stu-id="444ce-114">In This Section</span></span>

  - [<span data-ttu-id="444ce-115">在 Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="444ce-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="444ce-116">在 Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="444ce-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="444ce-117">在 Lync Server 2013 中流覽規劃工具</span><span class="sxs-lookup"><span data-stu-id="444ce-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="444ce-118">建立 Lync Server 2013 的初始拓撲設計</span><span class="sxs-lookup"><span data-stu-id="444ce-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="444ce-119">在 Lync Server 2013 中檢閱管理員報告</span><span class="sxs-lookup"><span data-stu-id="444ce-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="444ce-120">請參閱</span><span class="sxs-lookup"><span data-stu-id="444ce-120">See Also</span></span>


[<span data-ttu-id="444ce-121">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ce-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="444ce-122">在 Lync Server 2013 中規劃前端伺服器、立即訊息及顯示狀態</span><span class="sxs-lookup"><span data-stu-id="444ce-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

