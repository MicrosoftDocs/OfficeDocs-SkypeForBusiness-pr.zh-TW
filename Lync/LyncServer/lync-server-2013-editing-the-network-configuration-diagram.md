---
title: Lync Server 2013： 編輯網路組態圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f23e1ca036690f7f48071c46db6769b75424fe1e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136310"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="eecb4-102">編輯 Lync Server 2013 中的網路組態圖</span><span class="sxs-lookup"><span data-stu-id="eecb4-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eecb4-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="eecb4-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="eecb4-104">大部分的工作設計工具會在 Lync Server 2013 中，、 規劃工具包含定義的 IP 位址的項目，以及完整的網域名稱 (Fqdn) 的網狀圖上的項目。</span><span class="sxs-lookup"><span data-stu-id="eecb4-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="eecb4-105">在此頁面輸入的資訊會攜帶入報告和規劃工具中包含的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="eecb4-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="eecb4-106">![規劃工具的網路圖表](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "規劃工具的網路圖表")</span><span class="sxs-lookup"><span data-stu-id="eecb4-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="eecb4-107">規劃工具建立網狀圖與 IP 位址和 Fqdn 的預設文字。</span><span class="sxs-lookup"><span data-stu-id="eecb4-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="eecb4-108">若要編輯網路圖和輸入值：</span><span class="sxs-lookup"><span data-stu-id="eecb4-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="eecb4-109">選擇要開始處理的網路區段。</span><span class="sxs-lookup"><span data-stu-id="eecb4-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="eecb4-110">例如，連按兩下文字]，[ **access1.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="eecb4-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="eecb4-111">在開啟 [對話方塊] 方塊中，輸入的實際 FQDN 伺服器 access1.contoso.com 和實際的 IP 位址，取代 131.107.155.3。</span><span class="sxs-lookup"><span data-stu-id="eecb4-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="eecb4-112">按一下 **[確定]** 儲存項目。</span><span class="sxs-lookup"><span data-stu-id="eecb4-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="eecb4-113">繼續編輯 IP 位址和 FQDN，提供各硬體負載平衡器的虛擬 IP 位址，或集區中各伺服器的網域名稱系統 (DNS) 負載平衡的伺服器項目。</span><span class="sxs-lookup"><span data-stu-id="eecb4-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="eecb4-p103">規劃工具的一項實用功能在於可以漸進地指派 IP 位址範圍和伺服器主機名稱，而不需要設計師分別編輯集區中的每部伺服器。例如：</span><span class="sxs-lookup"><span data-stu-id="eecb4-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="eecb4-116">按兩下集區化的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="eecb4-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="eecb4-117">當對話方塊開啟時，選取 **[您要使用 IP 和 FQDN 作為此叢集中所有同等級伺服器的起點嗎?]**。</span><span class="sxs-lookup"><span data-stu-id="eecb4-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="eecb4-118">例如，第一部伺服器的起始值為 fe0101.contoso.com 和 192.168.21.122 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="eecb4-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="eecb4-119">輸入**fe0.contoso.com**中**前端伺服器 FQDN**、 在**前端伺服器 IP 位址**] 中輸入**192.168.21.131** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="eecb4-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="eecb4-120">自動增量功能從 192.168.21.131 136 來更新為 fe01 至 fe06，並將所有的 IP 位址集區中的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="eecb4-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="eecb4-121">您已完成所有的編輯之後，儲存拓撲，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="eecb4-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="eecb4-122">要儲存的規劃工具設計，按一下 [**檔案**]，然後按一下 [**儲存拓樸**] 或 [**另存拓撲**。</span><span class="sxs-lookup"><span data-stu-id="eecb4-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="eecb4-123">如果出現 **[另存規劃工具]** 對話方塊，請在 **[檔案名稱]** 中輸入檔案的名稱，然後按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="eecb4-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="eecb4-124">另請參閱</span><span class="sxs-lookup"><span data-stu-id="eecb4-124">See Also</span></span>


[<span data-ttu-id="eecb4-125">編輯 Lync Server 2013 中的設計</span><span class="sxs-lookup"><span data-stu-id="eecb4-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

