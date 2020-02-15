---
title: Lync Server 2013： 編輯設計
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7607fb2f31107e3368fa52167dc5015eb1b71f15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="38a9d-102">編輯 Lync Server 2013 中的設計</span><span class="sxs-lookup"><span data-stu-id="38a9d-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38a9d-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="38a9d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="38a9d-104">完成後的初始採訪問題，您可以編輯網站的 IP 位址與完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="38a9d-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="38a9d-105">若要這麼做，請在 **[全域拓撲]** 頁面上，連按兩下您要編輯的網站。</span><span class="sxs-lookup"><span data-stu-id="38a9d-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="38a9d-106">規劃工具會顯示選取的站台的站台拓撲。</span><span class="sxs-lookup"><span data-stu-id="38a9d-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="38a9d-107">在網站頁面的底部有四個索引標籤：</span><span class="sxs-lookup"><span data-stu-id="38a9d-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="38a9d-108">![規劃工具站台拓撲](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "規劃工具站台拓撲")</span><span class="sxs-lookup"><span data-stu-id="38a9d-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="38a9d-109">站台拓撲 – 目前顯示頁面具有如同建議的可見拓撲概觀。</span><span class="sxs-lookup"><span data-stu-id="38a9d-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="38a9d-110">Edge 網狀圖 – [Edge 網狀圖] 頁面上是工作的設計工具其中沒有大部分的規劃工具中。</span><span class="sxs-lookup"><span data-stu-id="38a9d-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="38a9d-111">圖表顯示建議的 Lync Server 2013 拓撲的網路組態，使用可編輯的項目 ip 位址和 Fqdn 伺服器、 集區]，並同時硬體和網域名稱系統 (DNS) 負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="38a9d-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="38a9d-112">Edge Admin 報表 – [Edge Admin 報表] 總共包含四份報表：</span><span class="sxs-lookup"><span data-stu-id="38a9d-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="38a9d-113">![Edge 管理員報告頁面](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge 管理員報告頁面")</span><span class="sxs-lookup"><span data-stu-id="38a9d-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="38a9d-114">摘要報表 – Edge 網路組態設定的一般報表。</span><span class="sxs-lookup"><span data-stu-id="38a9d-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="38a9d-115">如果您編輯的值在拓樸 TCP/IP **Edge 網狀圖**] 頁面上的 FQDN 值會用於實際部署中，會在這裡表示那些位址和名稱。</span><span class="sxs-lookup"><span data-stu-id="38a9d-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="38a9d-116">否則，會顯示預設文字。</span><span class="sxs-lookup"><span data-stu-id="38a9d-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="38a9d-117">憑證報表 – 憑證報表會列出拓撲所需憑證的主體名稱和主體替代名稱。</span><span class="sxs-lookup"><span data-stu-id="38a9d-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="38a9d-118">防火牆報表 – 防火牆報表會列出在基礎結構中設定周邊防火牆所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="38a9d-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="38a9d-119">這包括 IP 位址 （預設或編輯的值）、 伺服器角色、 來源 IP 和連接埠、 目的地 IP 和連接埠、 傳輸通訊協定、 應用程式的通訊協定，以及相關的附註。</span><span class="sxs-lookup"><span data-stu-id="38a9d-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="38a9d-120">DNS 報告 – DNS 報告列出 DNS 項目，您必須建立的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="38a9d-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="38a9d-121">包含正常運作所需的記錄類型、FQDN、IP 位址和註解。</span><span class="sxs-lookup"><span data-stu-id="38a9d-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="38a9d-122">網站摘要 – 網站摘要呈現您藉由回答初始採訪問題，或填寫**設計站台**內的值所做的選擇的概觀。</span><span class="sxs-lookup"><span data-stu-id="38a9d-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="38a9d-123">容量的資訊也會顯示。</span><span class="sxs-lookup"><span data-stu-id="38a9d-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38a9d-124">[網站摘要] 頁面上的資訊是針對各項設計所自訂的，無法包含此處詳述的所有區段或資訊。</span><span class="sxs-lookup"><span data-stu-id="38a9d-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="38a9d-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38a9d-125">See Also</span></span>


[<span data-ttu-id="38a9d-126">編輯 Lync Server 2013 中的網路組態圖</span><span class="sxs-lookup"><span data-stu-id="38a9d-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

