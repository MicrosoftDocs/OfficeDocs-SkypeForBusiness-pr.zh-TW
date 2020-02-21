---
title: Lync Server 2013： 使用規劃工具設計拓撲
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
ms.openlocfilehash: 1c519e6b89051dd2034c528a817a34afb9044f1e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="ab1e9-102">使用規劃工具設計 Lync Server 2013 的拓撲</span><span class="sxs-lookup"><span data-stu-id="ab1e9-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab1e9-103">_**上次修改主題：** 2013年-03-04_</span><span class="sxs-lookup"><span data-stu-id="ab1e9-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="ab1e9-104">Microsoft Lync Server 2013、 規劃工具是的精靈驅動，詢問您所設計的 Lync Server 2013 拓撲的相關問題的採訪類似的工具。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="ab1e9-105">提供資訊，請規劃工具使用搭配慣用的拓撲設計和容量，以呈現提供的答案為基礎的建議的拓撲的作法。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="ab1e9-106">您可以從 Microsoft 下載中心下載規劃工具 ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725))。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-106">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="ab1e9-107">最後，規劃工具的目標是為了簡化潛在的設計完整的 Lync Server 2013 拓撲複雜性。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="ab1e9-108">此工具也會提供其規劃與部署文件的關聯式參考，只要有網際網路連線可連接至 Microsoft TechNet 網站即可。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="ab1e9-109">自訂之後的拓撲的基礎結構的 TCP/IP 位址與完整的網域名稱 (Fqdn)，規劃工具會提供一系列的涵蓋網域名稱系統 (DNS) 命名、 防火牆規則、 憑證、 等等的報告。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="ab1e9-110">規劃工具也提供匯出資訊兩種格式的能力：</span><span class="sxs-lookup"><span data-stu-id="ab1e9-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="ab1e9-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="ab1e9-111">Microsoft Excel</span></span>

  - <span data-ttu-id="ab1e9-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="ab1e9-112">Microsoft Visio</span></span>

<span data-ttu-id="ab1e9-113">下列主題介紹，詳細規劃工具。</span><span class="sxs-lookup"><span data-stu-id="ab1e9-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ab1e9-114">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ab1e9-114">In This Section</span></span>

  - [<span data-ttu-id="ab1e9-115">Lync Server 2013 中安裝規劃工具</span><span class="sxs-lookup"><span data-stu-id="ab1e9-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="ab1e9-116">Lync Server 2013 中安裝選用軟體</span><span class="sxs-lookup"><span data-stu-id="ab1e9-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="ab1e9-117">瀏覽 Lync Server 2013 中的規劃工具</span><span class="sxs-lookup"><span data-stu-id="ab1e9-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="ab1e9-118">建立初始拓撲設計的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab1e9-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="ab1e9-119">檢閱 Lync Server 2013 中的系統管理員報告</span><span class="sxs-lookup"><span data-stu-id="ab1e9-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ab1e9-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ab1e9-120">See Also</span></span>


[<span data-ttu-id="ab1e9-121">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab1e9-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="ab1e9-122">規劃前端伺服器、 立即訊息和 Lync Server 2013 中的目前狀態</span><span class="sxs-lookup"><span data-stu-id="ab1e9-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

