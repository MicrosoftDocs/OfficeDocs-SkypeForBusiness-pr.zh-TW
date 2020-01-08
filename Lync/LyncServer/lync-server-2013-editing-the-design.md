---
title: Lync Server 2013：編輯設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 601c313231a26341c3c4cf8a4897d11872dec9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="472c4-102">在 Lync Server 2013 中編輯設計</span><span class="sxs-lookup"><span data-stu-id="472c4-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="472c4-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="472c4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="472c4-104">完成最初的訪談問題之後，您可以編輯該網站的完整功能變數名稱（FQDN）和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="472c4-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="472c4-105">若要這樣做，請在 [**全域拓撲**] 頁面上，按兩下您要編輯的網站。</span><span class="sxs-lookup"><span data-stu-id="472c4-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="472c4-106">規劃工具會顯示所選網站的網站拓撲。</span><span class="sxs-lookup"><span data-stu-id="472c4-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="472c4-107">[網站] 頁面底部有四個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="472c4-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="472c4-108">![規劃工具網站拓撲](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "規劃工具網站拓撲")</span><span class="sxs-lookup"><span data-stu-id="472c4-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="472c4-109">網站拓撲：目前顯示的頁面，其中包含拓撲的視覺概況（如建議）。</span><span class="sxs-lookup"><span data-stu-id="472c4-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="472c4-110">[邊緣網狀圖] – [邊緣網狀圖] 頁面是設計工具在規劃工具中的大部分工作位置。</span><span class="sxs-lookup"><span data-stu-id="472c4-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="472c4-111">圖表會顯示建議的 Lync Server 2013 拓朴的網路設定，以及伺服器、池以及硬體和網域名稱系統（DNS）負載平衡器的可編輯專案。</span><span class="sxs-lookup"><span data-stu-id="472c4-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="472c4-112">Edge 管理報表-Edge 管理員報告總共包含四個報告：</span><span class="sxs-lookup"><span data-stu-id="472c4-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="472c4-113">![Edge 管理報表頁面](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "邊緣管理報表頁面")</span><span class="sxs-lookup"><span data-stu-id="472c4-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="472c4-114">摘要報告–邊緣網路設定的一般設定報告。</span><span class="sxs-lookup"><span data-stu-id="472c4-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="472c4-115">如果您將 [ **Edge 網狀圖**] 頁面上的值編輯為要在實際部署中使用的 [拓撲 tcp/ip] 和 [FQDN] 值，這些位址和名稱將會顯示在這裡。</span><span class="sxs-lookup"><span data-stu-id="472c4-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="472c4-116">否則，會出現預設文字。</span><span class="sxs-lookup"><span data-stu-id="472c4-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="472c4-117">[憑證報告] –憑證報告會列出拓朴所需之憑證的主體名稱和消費者名稱。</span><span class="sxs-lookup"><span data-stu-id="472c4-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="472c4-118">防火牆報告-防火牆報告會列出在基礎結構中設定週邊防火牆所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="472c4-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="472c4-119">這包括 IP 位址（預設或已編輯的值）、伺服器角色、來源 IP 和埠、目的地 IP 與埠、傳輸通訊協定、應用程式協定，以及相關的筆記。</span><span class="sxs-lookup"><span data-stu-id="472c4-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="472c4-120">DNS 報告– DNS 報告會列出您必須建立之 DNS 專案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="472c4-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="472c4-121">包括適當作業所需的記錄類型、FQDN、IP 位址和批註。</span><span class="sxs-lookup"><span data-stu-id="472c4-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="472c4-122">[網站摘要]： [網站摘要] 會顯示您在回答最初的面試問題或填入**設計網站**中的值時所做的選擇。</span><span class="sxs-lookup"><span data-stu-id="472c4-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="472c4-123">也會顯示容量資訊。</span><span class="sxs-lookup"><span data-stu-id="472c4-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="472c4-124">[網站摘要] 頁面上的資訊會針對每個設計進行自訂，並且可能不會包含所有章節或本文中的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="472c4-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="472c4-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="472c4-125">See Also</span></span>


[<span data-ttu-id="472c4-126">在 Lync Server 2013 中編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="472c4-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

