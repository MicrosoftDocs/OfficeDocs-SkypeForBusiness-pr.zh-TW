---
title: Lync Server 2013：編輯網路設定圖表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="e969f-102">在 Lync Server 2013 中編輯網路設定圖表</span><span class="sxs-lookup"><span data-stu-id="e969f-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e969f-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e969f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e969f-104">在 Lync Server 2013 中，設計工具的大部分工作都是由定義 IP 位址的專案，以及網狀圖表專案的完整功能變數名稱（Fqdn）。</span><span class="sxs-lookup"><span data-stu-id="e969f-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="e969f-105">在此頁面上輸入的資訊會納入至 [規劃工具] 中所含的報告及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="e969f-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="e969f-106">![規劃工具網狀圖](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "規劃工具網狀圖")</span><span class="sxs-lookup"><span data-stu-id="e969f-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="e969f-107">規劃工具會建立含 IP 位址和 Fqdn 預設文字的網狀圖表。</span><span class="sxs-lookup"><span data-stu-id="e969f-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="e969f-108">若要編輯 network 圖表及輸入值：</span><span class="sxs-lookup"><span data-stu-id="e969f-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="e969f-109">選擇要開始使用的網路區段。</span><span class="sxs-lookup"><span data-stu-id="e969f-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="e969f-110">例如，按兩下文字 [ **access1.contoso.com**]。</span><span class="sxs-lookup"><span data-stu-id="e969f-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="e969f-111">在開啟的對話方塊中，輸入 [伺服器 access1.contoso.com] 的實際 FQDN，以及實際的 IP 位址（取代131.107.155.3）。</span><span class="sxs-lookup"><span data-stu-id="e969f-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="e969f-112">按一下 **[確定]** 儲存專案。</span><span class="sxs-lookup"><span data-stu-id="e969f-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="e969f-113">繼續編輯 IP 位址和 Fqdn，提供硬體負載平衡器的虛擬 IP 位址或網域名稱系統（DNS）的伺服器專案在池中的伺服器負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e969f-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="e969f-114">規劃工具有一個實用的功能，就是它可以逐漸指派 IP 位址和伺服器主機名稱的範圍，而不需要設計者在池中編輯每個獨立的伺服器。</span><span class="sxs-lookup"><span data-stu-id="e969f-114">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool.</span></span> <span data-ttu-id="e969f-115">例如：</span><span class="sxs-lookup"><span data-stu-id="e969f-115">For example:</span></span>

1.  <span data-ttu-id="e969f-116">按兩下共端的前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="e969f-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="e969f-117">對話方塊開啟時，請選取 [**您想要將 IPs 和 FQDN 作為此群集中所有等價伺服器的起始點嗎？**]。</span><span class="sxs-lookup"><span data-stu-id="e969f-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="e969f-118">例如，第一個伺服器的起始值是 fe0101.contoso.com，IP 位址是192.168.21.122。</span><span class="sxs-lookup"><span data-stu-id="e969f-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="e969f-119">在 [**前端伺服器 FQDN**] 中輸入**Fe0.contoso.com** ，在**前端伺服器 IP 位址**中輸入**192.168.21.131** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e969f-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="e969f-120">[自動遞增值] 功能會將池中的所有伺服器更新為 fe01 到 fe06，並將所有 IP 位址從192.168.21.131 移至136。</span><span class="sxs-lookup"><span data-stu-id="e969f-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="e969f-121">完成所有編輯之後，請完成下列步驟以儲存拓朴：</span><span class="sxs-lookup"><span data-stu-id="e969f-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="e969f-122">若要儲存規劃工具設計，請**按一下 [** 檔案]，然後按一下 [**儲存拓撲**] 或 [**另存拓撲為**]。</span><span class="sxs-lookup"><span data-stu-id="e969f-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="e969f-123">如果出現 [**儲存規劃工具**] 對話方塊，請在 [**檔案名**] 中輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e969f-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="e969f-124">請參閱</span><span class="sxs-lookup"><span data-stu-id="e969f-124">See Also</span></span>


[<span data-ttu-id="e969f-125">在 Lync Server 2013 中編輯設計</span><span class="sxs-lookup"><span data-stu-id="e969f-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

